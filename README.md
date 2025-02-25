PathFinder tool is a powerful and efficient pathfinding solution for Unity. It allows you to compute a path between two points in 3D space and bypassing obstacles.

`Features`
Grid-Based Pathfinding: The tool uses a grid-based method to find paths, guaranteeing deterministic and ~~not~~optimized movement.
Obstacle Avoidance: It uses raycasting for checking obstacles so that the path found is obstacle-free and clear.
Step Size: You are allowed to set the step size (grid size) to trade off between accuracy and speed.
A* Algorithm: The application uses the A*-like algorithm, a popular and efficient pathfinding algorithm, to determine the shortest route between two points.
3D Support: Processes 3D environments with ease.

`How to Use`
Begin the PathFinder:
Create an instance of the PathFinder class with the desired stepSize (grid resolution) as a parameter.
```cs
PathFinder pathFinder = new PathFinder(1.0f); // <--- 1.0f is the step size
```

Find a Path:
Call the FindPath method with the start position and target position as Vector3 parameters.
The function returns a list of Vector3 points along the path from start to end.
```cs
List<Vector3> path = pathFinder.FindPath(startPosition, targetPosition);
```

Follow the Path:
The path returned can be utilized to relocate objects, bots. Every position in the list is a step in the path.

`Some additional information`
Personalize Obstacle Detection: The tool uses `Physics.Raycast` to detect obstacles at grid points. You may rewrite the IsPathClear method to provide your own obstacle detection logic if required (like add layer in layermask).
Step Size: The stepSize parameter determines the grid resolution. Lower values give more accurate paths but can be slower to compute. Higher values are quicker but less accurate.
