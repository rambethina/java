---
title: Week Eleven
sidebar: mydoc_sidebar
permalink: mydoc_week_twelve.html
folder: mydoc
---

## Event based program
* [Event based program](https://rambethina.github.io/java/mydoc_week_eleven.html#event-based-program)

## In class Exercise

Use switch case for above program

```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.hardware.DcMotor;
import com.qualcomm.robotcore.util.ElapsedTime;

@Autonomous(name = "TwoWheelRegModeSMSwithCase", group = "RegularOpMode")
public class TwoWheelRegModeSMSwithCase extends OpMode {

    DcMotor leftMotor;
    DcMotor rightMotor;

    ElapsedTime elapsedTime;
    State currentState = State.FORWARD;

    enum State {
        FORWARD,
        BACKWARD
    }

    @Override
    public void init() {
        leftMotor = hardwareMap.dcMotor.get("left_motor");
        rightMotor = hardwareMap.dcMotor.get("right_motor");
        leftMotor.setDirection(DcMotor.Direction.REVERSE);
    }

    public void start() {
        this.elapsedTime = new ElapsedTime();
        elapsedTime.reset();
    }

    @Override
    public void loop() {
        double time = elapsedTime.milliseconds();
        System.out.println(time);

//        if(currentState == State.FORWARD) {
//            leftMotor.setPower(1);
//            rightMotor.setPower(1);
//            if(time > 1000) {
//                elapsedTime.reset();
//                currentState = State.BACKWARD;
//            }
//        } else if (currentState == State.BACKWARD) {
//            leftMotor.setPower(-1);
//            rightMotor.setPower(-1);
//            if(time > 1000) {
//                elapsedTime.reset();
//                currentState = State.FORWARD;
//            }
//        }

        switch (currentState) {
            case BACKWARD: {
                leftMotor.setPower(-1);
                rightMotor.setPower(-1);
                if (time > 1000) {
                    elapsedTime.reset();
                    currentState = State.FORWARD;
                }
                break;
            }
            case FORWARD: {
                leftMotor.setPower(1);
                rightMotor.setPower(1);
                if (time > 1000) {
                    elapsedTime.reset();
                    currentState = State.BACKWARD;
                }
            }
        }
    }
}

```


## Encoders
Encoders are sensors that track “counts” or “ticks,” which are values that represent a certain amount of a rotation, Using encoders is a better way to measure distance than time, due to frcition etc.
* [API](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html)
* [Modes](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.RunMode.html)

```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.DcMotor;

@Autonomous(name = "SampleEncoders", group = "Sample")
public class SampleEncoders extends LinearOpMode {

    DcMotor leftMotor;
    DcMotor rightMotor;

    @Override
    public void runOpMode() throws InterruptedException {
        leftMotor = hardwareMap.dcMotor.get("left_motor");
        rightMotor = hardwareMap.dcMotor.get("right_motor");

        telemetry.addData("Press Start to Continue","");
        telemetry.update();

        waitForStart();

        leftMotor.setDirection(DcMotor.Direction.REVERSE);

        telemetry.addData("Mode", "waiting");
        telemetry.update();

        // wait for start button.
        leftMotor.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);
        rightMotor.setMode(DcMotor.RunMode.STOP_AND_RESET_ENCODER);

        leftMotor.setTargetPosition(2000);
        rightMotor.setTargetPosition(2000);

        leftMotor.setMode(DcMotor.RunMode.RUN_TO_POSITION);
        rightMotor.setMode(DcMotor.RunMode.RUN_TO_POSITION);

        waitForStart();

        leftMotor.setPower(0.25);
        rightMotor.setPower(0.25);

        while(opModeIsActive() && leftMotor.isBusy()){
            telemetry.addData("encoder-fwd-left", leftMotor.getCurrentPosition() + "  busy=" + leftMotor.isBusy());
            telemetry.addData("encoder-fwd-right", rightMotor.getCurrentPosition() + "  busy=" + rightMotor.isBusy());
            telemetry.update();
            idle();
        }

        leftMotor.setPower(0.0);
        rightMotor.setPower(0.0);

        sleep(1000);

        leftMotor.setTargetPosition(0);
        rightMotor.setTargetPosition(0);

        leftMotor.setPower(0.25);
        rightMotor.setPower(0.25);

        while(opModeIsActive() && leftMotor.isBusy()){
            telemetry.addData("encoder-fwd-left", leftMotor.getCurrentPosition() + "  busy=" + leftMotor.isBusy());
            telemetry.addData("encoder-fwd-right", rightMotor.getCurrentPosition() + "  busy=" + rightMotor.isBusy());
            telemetry.update();
            idle();
        }
    }
}
```

## In Class Exercises

Drive mechanum bot in a square

[Set motor power based on specifications.](https://learnroadrunner.com/drive-constants.html#samplemecanumdrive-motor-direction)

## Game pad controls & Servo

```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.Servo;

@Autonomous(name="SampleServo", group = "sample")
public class SampleServo extends LinearOpMode {
    Servo armServo;
    double startingArmPosition;
    double MIN_POSITION = 0;
    double MAX_POSITION = 1.0;
    @Override
    public void runOpMode() throws InterruptedException {

        armServo = hardwareMap.servo.get("back_servo");

        telemetry.addData("Mode", "waiting");
        telemetry.update();



        waitForStart();
        startingArmPosition = 0.5;

        while (opModeIsActive()) {

            // move arm down on A button if not already at lowest position.
            if (gamepad1.a && startingArmPosition > MIN_POSITION) startingArmPosition -= .001;

            // move arm up on B button if not already at the highest position.
            if (gamepad1.b && startingArmPosition < MAX_POSITION) startingArmPosition += .001;

            armServo.setPosition(startingArmPosition);
        }
    }

}
```

## Solution drive in a square

```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.DcMotor;

@Autonomous(name="SampleLinearOpModeSquareMec", group = "sample")
public class SampleLinearOpModeSquareMec extends LinearOpMode {

    DcMotor front_left_motor;
    DcMotor front_right_motor;
    DcMotor back_left_motor;
    DcMotor back_right_motor;

    // called when init button is  pressed.

    //    back_right_motor
//            front_right_motor
//    front_left_motor
//            back_left_motor
    @Override
    public void runOpMode() throws InterruptedException
    {
        front_left_motor = hardwareMap.dcMotor.get("front_left_motor");
        back_left_motor = hardwareMap.dcMotor.get("back_left_motor");
        front_right_motor = hardwareMap.dcMotor.get("front_right_motor");
        back_right_motor = hardwareMap.dcMotor.get("back_right_motor");

        front_left_motor.setDirection(DcMotor.Direction.REVERSE);
        back_left_motor.setDirection(DcMotor.Direction.REVERSE);

        telemetry.addData("Mode", "waiting");
        telemetry.update();

        // wait for start button.

        waitForStart();

        telemetry.addData("Mode", "running");
        telemetry.update();

        sleep(500);        // wait so that above telemetry is visible.

        // each iteration of this for loop will drive one side of the square.

        front_left_motor.setPower(0.25);
        front_right_motor.setPower(0.25);
        back_left_motor.setPower(0.25);
        back_right_motor.setPower(0.25);

        sleep(3000); // drive straight for 1 second.

        front_left_motor.setPower(0.0);
        front_right_motor.setPower(0.0);
        back_left_motor.setPower(0);
        back_right_motor.setPower(0);

        sleep(3000); // drive straight for 1 second.

        front_left_motor.setPower(0.25);
        front_right_motor.setPower(-0.25);
        back_left_motor.setPower(-0.25);
        back_right_motor.setPower(.25);

        sleep(3000);

        front_left_motor.setPower(0.0);
        front_right_motor.setPower(0.0);
        back_left_motor.setPower(0);
        back_right_motor.setPower(0);

        sleep(3000); // drive straight for 1 second.

        front_left_motor.setPower(-0.25);
        front_right_motor.setPower(-0.25);
        back_left_motor.setPower(-0.25);
        back_right_motor.setPower(-.25);

        sleep(3000);


        front_left_motor.setPower(0.0);
        front_right_motor.setPower(0.0);
        back_left_motor.setPower(0);
        back_right_motor.setPower(0);

        sleep(3000); // drive straight for 1 second.

        front_left_motor.setPower(-0.25);
        front_right_motor.setPower(0.25);
        back_left_motor.setPower(0.25);
        back_right_motor.setPower(-.25);

        sleep(3000);

        // make sure the motors are off.

        front_right_motor.setPower(0);
        back_left_motor.setPower(0);
        front_left_motor.setPower(0);
        back_right_motor.setPower(0);
    }
}
```






