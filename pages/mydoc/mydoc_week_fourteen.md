---
title: Week fourteen
sidebar: mydoc_sidebar
permalink: mydoc_week_fourteen.html
folder: mydoc
---

## Path Algorithms
* [Path finding algorithms](https://en.wikipedia.org/wiki/Pathfinding)
* Provide start and end points
* Provide blocks
* Run program to find path.

```
package com.ai;

public class Node {
    private int g;
    private int f;
    private int h;
    private int row;
    private int col;
    private boolean isBlock;
    private Node parent;

    public Node(int row, int col) {
        super();
        this.row = row;
        this.col = col;
    }

    public void calculateHeuristic(Node finalNode) {
        this.h = Math.abs(finalNode.getRow() - getRow()) + Math.abs(finalNode.getCol() - getCol());
    }

    public void setNodeData(Node currentNode, int cost) {
        int gCost = currentNode.getG() + cost;
        setParent(currentNode);
        setG(gCost);
        calculateFinalCost();
    }

    public boolean checkBetterPath(Node currentNode, int cost) {
        int gCost = currentNode.getG() + cost;
        if (gCost < getG()) {
            setNodeData(currentNode, cost);
            return true;
        }
        return false;
    }

    private void calculateFinalCost() {
        int finalCost = getG() + getH();
        setF(finalCost);
    }

    @Override
    public boolean equals(Object arg0) {
        Node other = (Node) arg0;
        return this.getRow() == other.getRow() && this.getCol() == other.getCol();
    }

    @Override
    public String toString() {
        return "Node [row=" + row + ", col=" + col + "]";
    }

    public int getH() {
        return h;
    }

    public void setH(int h) {
        this.h = h;
    }

    public int getG() {
        return g;
    }

    public void setG(int g) {
        this.g = g;
    }

    public int getF() {
        return f;
    }

    public void setF(int f) {
        this.f = f;
    }

    public Node getParent() {
        return parent;
    }

    public void setParent(Node parent) {
        this.parent = parent;
    }

    public boolean isBlock() {
        return isBlock;
    }

    public void setBlock(boolean isBlock) {
        this.isBlock = isBlock;
    }

    public int getRow() {
        return row;
    }

    public void setRow(int row) {
        this.row = row;
    }

    public int getCol() {
        return col;
    }

    public void setCol(int col) {
        this.col = col;
    }
}

```


## Road Runner
* [Road Runner](https://learnroadrunner.com/)
* Program your robot to navigate given a path.
* [Trajectory overview](https://learnroadrunner.com/trajectories.html#trajectories-overview)
* [Path continuity exception](https://learnroadrunner.com/trajectories.html#path-continuity-exception)
* [Markers](https://learnroadrunner.com/markers.html#types-of-markers)

## Road Runner and A Star
* [Sample Project](https://github.com/rambethina/SampleFTC.git)
* Download project, Run the following op modes 
* RoadRunnerSampleExamples - Simple road runner examples
* RoadRunnerSampleTwo - Integration with Road Runner and A Star
* RoadRunnerSampleMarkerOne - Using markers