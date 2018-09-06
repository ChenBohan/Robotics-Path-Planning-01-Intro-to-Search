# Robotics-Path-Planning-01-Intro-to-Search
Udacity Self-Driving Car Engineer Nanodegree: Search. 

## A Star

Uses a heuristic to find a path.

## Dynamic Programming

Finds an entire policy that has a plan for every location.

```python
        for x in range(len(grid)):
            for y in range(len(grid[0])):
                if goal[0] == x and goal[1] == y:
                    if value[x][y] > 0:
                        value[x][y] = 0
                        change = True

                elif grid[x][y] == 0:
                    for a in range(len(delta)):
                        x2 = x + delta[a][0]
                        y2 = y + delta[a][1]

                        if x2 >= 0 and x2 < len(grid) and y2 >= 0 and y2 < len(grid[0]) and grid[x2][y2] == 0:
                            v2 = value[x2][y2] + cost

                            if v2 < value[x][y]:
                                change = True
                                value[x][y] = v2
```

For each grid:
1. Check if it is the goal.
2. Go through the 3 different actions.
3. If we arrived at a valid grid cell, we update the value if it is better.


