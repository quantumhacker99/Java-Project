In this simulation, we have a set of stationary objects (obstacles) and a set of moving objects (actors). Actor objects move around
autonomously from a start position to a destination position. In the process, they compute a path such that they will not intersect with obstacles or other actors.
The animation involves recomputing the position of each actor at each time step, and displaying
the objects in their current position. For collision detection, we use orthogonally aligned rectangular bounding boxes, the smallest rectangle that contains the points of the object. These bounding boxes (BBox) are defined by
their corners with the min and max coordinates. Two objects collide if their BBox’es touch or
overlap.
Hence, for animation, each actor computes its next position (given a timestep and its destination position). If this new position will not collide with any other object, it moves to that position. If not, it computes a different (non-colliding) position and moves there. If no such position exists, it stays in its current position until it can move the destination location of the actor can be changed anytime.
