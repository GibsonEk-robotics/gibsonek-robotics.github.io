# Functions in libraries
Some simple functions for making movement and data collection simple using the bluerobotics_navigator library. This makes it easy to employ a "fire and forget" operation, while collecting sensor data along the way.

> **_NOTE:_**
> For every single function you ***MUST*** set the bluerobotics_navigator as the first parameter.
> The bluerobotics_navigator library should only be imported in the main code you're running

> **_NOTE:_**
> The motors will keep running until either one of the two conditions below are fulfilled:
> - The speed is set to 0
> - motors are reset 

## Motor Configuration
- Channel 1: Underside front right, Clockwise
- Channel 2: Underside front left, Clockwise
- Channel 3: Underside back right, Clockwise
- Channel 4: Underside back left, Counterclockwise
- Channel 5: Top front right, Clockwise
- Channel 6: Top front left, Counterclockwise
- Channel 7: Top back right, Counterclockwise
- Channel 8: Top back left, Clockwise

## xMovementLib

horizontalMovement defaults in order:
- nav has no default
- horizontalDect = True #This controls the movement of the robot on the X axis. True is fowards and False is backwards.
- horizontalSpeed = 0 #This sets the speed of the motors. The speed value is a percentile, where 0.00 = 0% and 1.00 = 100%.

Here is an example of horizontalMovement in use:

```python
import libraries.HorizontalMovementLib
libraries.HorizontalMovementLib.horizontalMovement(nav, horizontalDect = True, horizontalSpeed = 0.5)
```

## zDepthLib

verticalMovement is almost identical except for:
- verticalDect = True #This now controls the Z axis. True is down, False is up.
- verticalSpeed = 0.2 #This is basically the same as horizontal speed.

Here is an example of verticalMovement in use:

```python
import libraries.verticalMovementLib
libraries.verticalMovementLib.verticalMovement(nav, verticalDect = True, verticalSpeed = 0.5)
```

## zHoverLib

HoverMovement defaults in order (the speed is calibrated for hovering):
- nav has no default
- hoverDect = True #This controls the movement of the robot on the Y axis. True is down and False is up.
- hoverSpeed = 0.15 #This sets the speed of the motors when holding. The speed value is a percentile, where 0.00 = 0% and 1.00 = 100%.

```python
import libraries.hoverMovementLib
libraries.hoverMovementLib.hoverMovement(nav, hoverDect = True, hoverSpeed = 0.15)
```

## rollrotationLib

rollMovement defaults in order (a sleep value of 4.5 seconds consistently performs 2 rolls):
- nav has no defaults
- rollDect = True #This now controls the X rotational axis. TRUE is right, FALSE is left.
- rollSpeed = 0.35 #This sets the speed of the motors. The speed value is a percentile, where 0.00 = 0% and 1.00 = 100%.

Here is an example of rollMovement in use:

```python
import libraries.rollMovementLib
libraries.rollMovementLib.rollMotorMovement(nav, rollDect = True, rollSpeed = 0.35)
```

## yawRotationLib

rotationMovement defaults in order:
- nav has no defaults
- rotationSpeed = 0 #This is the same as setting the other speeds
- rotationDect = True #This controls the Z rotational axis. True is right, False is left.

## sensorsLogLib

Logs gyro and accelleration for an amount of time specified by sensorLogTime Loops 10 times per second, perfect substitute for time.sleep since this way you collect sensor data during that time. This also outputs nicely to a csv for easy analysis.

## sensorLogTime

The time in seconds that the sensors will log for. Default is 5 seconds.
