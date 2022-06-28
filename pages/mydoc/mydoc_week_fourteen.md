---
title: Week Fourteen
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
Example Input
        Node initialNode = new Node(2, 1);
        Node finalNode = new Node(2, 5);
        int rows = 6;
        int cols = 7;
        AStar aStar = new AStar(rows, cols, initialNode, finalNode);
        int[][] blocksArray = new int[][]{{1, 3}, {2, 3}, {3, 3}};
        aStar.setBlocks(blocksArray);
        List<Node> path = aStar.findPath();
        for (Node node : path) {
            System.out.println(node);
        }

Output:
Node [row=2, col=1]
Node [row=1, col=2]
Node [row=0, col=3]
Node [row=1, col=4]
Node [row=2, col=5]
```