---
title: Week Eleven
sidebar: mydoc_sidebar
permalink: mydoc_week_eleven.html
folder: mydoc
---

## Final project
* [Final Project](https://rambethina.github.io/java/mydoc_week_ten.html#final-project)
## Refresher Interface
* [Refresher](https://rambethina.github.io/java/mydoc_week_ten.html#interface)

## Abstract class
```
public abstract class Vehicle {

    public double distance(int time) {
        return getSpeedInMilesPerHour() * time;
    }

    abstract int getSpeedInMilesPerHour();
}
```

```
public class Bike extends Vehicle{
    @Override
    int getSpeedInMilesPerHour() {
        //
        return 8;
    }
}
```

```
public class Car extends Vehicle{
    @Override
    int getSpeedInMilesPerHour() {
        return 80;
    }
}
```

```
public class DistanceTravelledMain {

    public static void main(String[] args) {
        Vehicle car = new Car();
        double distance = car.distance(15);
        System.out.println("Distance car travels : "+ distance);

        Vehicle bike = new Bike();
        double bikeDistance = bike.distance(15);
        System.out.println("Distance bike travels : "+ bikeDistance);
    }
}

```

## Enum

```
public class EnumExample {

    public static void main(String[] args) {
        StateMachineStates currentState = StateMachineStates.BACKWARD;

        switch (currentState) {
            case BACKWARD:
                System.out.println("Drive backward");
                break;
            case FORWARD :
                System.out.println("Drive forward");
                break;
            default:
                System.out.println("Unknown");
        }
    }
}

```

```
public enum StateMachineStates {
    LEFT,
    RIGHT,
    BACKWARD,
    FORWARD
}
```


## Simulator
* We will be using a [simulator](https://github.com/Beta8397/virtual_robot), 
* Unzip/UnCompress and open in intelliJ
* File open and choose folder
* Make one change to the following file

```
<PROJECT_DIR>/Controllers/src/virtual_robot/src/config/Config.java
```

```
    public static final boolean USE_VIRTUAL_GAMEPAD = true;
```

## OpModes

* Linear
    * Sequential programming.
    * You call loop method.
* Regular
    * Predefined loop method is called regularly.
    * Event based programming. [State machines are based on Event based programming., I think threads need to be used in addtiona to event based programming](https://gm0.org/en/latest/docs/software/finite-state-machines.html)


## Simple example using linear OpMode
* Get used to initializations

```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.DcMotor;

@Autonomous(name="One", group = "LinearOpMode")
public class TwoWheelLinearOpMode extends LinearOpMode {

    DcMotor leftMotor;
    DcMotor rightMotor;
    @Override
    public void runOpMode() throws InterruptedException {

        leftMotor = hardwareMap.dcMotor.get("left_motor");
        rightMotor = hardwareMap.dcMotor.get("right_motor");
        leftMotor.setDirection(DcMotor.Direction.REVERSE);
        waitForStart();

        leftMotor.setPower(.25);
        rightMotor.setPower(.25);

        sleep(2000);
    }
}
```

## Linar OpModes example with while loop
```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.DcMotor;

@Autonomous(name="One", group = "LinearOpMode")
public class TwoWheelLinearOpMode extends LinearOpMode {

    DcMotor leftMotor;
    DcMotor rightMotor;
    @Override
    public void runOpMode() throws InterruptedException {

        leftMotor = hardwareMap.dcMotor.get("left_motor");
        rightMotor = hardwareMap.dcMotor.get("right_motor");
        leftMotor.setDirection(DcMotor.Direction.REVERSE);
        waitForStart();

        while(opModeIsActive()){
            System.out.println(getRuntime());
            leftMotor.setPower(1);
            rightMotor.setPower(1);
        }
    }
}
```
## RegularOpMode
* Regular
    * Predefined loop method is called regularly.
    * Event based programming. (State machine)

```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.hardware.DcMotor;

@Autonomous(name="two", group = "RegularOpMode")
public class TwoWheelRegularOpMode extends OpMode {

    DcMotor leftMotor;
    DcMotor rightMotor;


    @Override
    public void init() {
        leftMotor = hardwareMap.dcMotor.get("left_motor");
        rightMotor = hardwareMap.dcMotor.get("right_motor");
        leftMotor.setDirection(DcMotor.Direction.REVERSE);
    }

    @Override
    public void loop() {
        System.out.println(getRuntime());
        leftMotor.setPower(-1);
        rightMotor.setPower(-1);
    }
}
```

## Event based program

```
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.hardware.DcMotor;
import com.qualcomm.robotcore.util.ElapsedTime;

@Autonomous(name = "TwoWheelRegModeStateMachine", group = "RegularOpMode")
public class TwoWheelRegModeStateMachine extends OpMode {

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

        if(currentState == State.FORWARD) {
            leftMotor.setPower(1);
            rightMotor.setPower(1);
            if(time > 1000) {
                elapsedTime.reset();
                currentState = State.BACKWARD;
            }
        } else if (currentState == State.BACKWARD) {
            leftMotor.setPower(-1);
            rightMotor.setPower(-1);
            if(time > 1000) {
                elapsedTime.reset();
                currentState = State.FORWARD;
            }
        }
    }
}
```

## Exercise

Take above example and convert using a switch statement

## Additional Reference
* [Game0](https://gm0.org/en/latest/docs/software/using-the-sdk.html)