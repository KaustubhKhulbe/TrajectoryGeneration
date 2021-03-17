# TrajectoryGeneration
This is created for the 2021 FRC challenge in which our robot were required to follow specific trajectories

Given robot parameters such as `mass`, `moment_of_inertia`, `motor_constants`, `gear_ratio`, etc. it can develop a drivetrain model
that uses linear approximations to accurately display the behaviour of the robot.

Using this information, it then, given a list of `waypoints` develops a path that currently optimizes `torque` and `curvature`. `torque`
is the torque the motors apply, which prevents the robot from stressing its motors and `curvature` is just to make the path smoother. More optimizers can be added,
but this was all that was needed for the challenge.

It solves the problem using `drake` and utilizes the non linear solver, which is a stochastic gradient descent algorithm. It outputs several useful graphs such as: 
velocity, angle, angular velocity, position, and left_motor voltage and right_motor voltage.

Eventually, this can be used with a state space algorithm using LQR to develop a gain matrix `K`, but this has not been implemented.
