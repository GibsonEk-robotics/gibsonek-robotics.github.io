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

## ScanRotationLib

NOT fire and forget. Makes the robot yaw for a specified amount of time, then pause for a specified amount of time. It will run through that loop a specified number of times before exiting. sensorsLogLib is built into the function. The parameters (nav, runtimes = 3, ScanDect = True, turnTime = 0.9, turnSpeed = 0.175 waitTime = 1) reliably made the robot turn 90 degrees to the right in 2024.

scanRotation defaults in order.

- nav has no default
- runtimes = 10 #The number of times that the robot runs through the rotate-pause loop before exiting
- ScanDect = True #The direction on the X-axis that the robot rotates. True is right, False is left.
- turnTime = 0.9 #The amount of time in seconds that the robot rotates for each loop
- turnSpeed = 0.175 #This sets the speed of the motors. The speed value is a percentage, where 0.00 = 0% and 1.00 = 100%.
- waitTime = 1 #The amount of time in seconds that the robot pauses with the motors off each loop.

  Here is an example of scanRotation in use:

  ```python
  import libraries.ScanRotationLib
  libraries.ScanRotationLib.scanRotation(nav, 10, True, 0.9, 0.175, 1)
  ```

## xMovementLib

Fire and forget. Makes the robot move horizontally.

horizontalMovement defaults in order:
- nav has no default
- horizontalDect = True #This controls the movement of the robot on the X axis. True is fowards and False is backwards.
- horizontalSpeed = 0 #This sets the speed of the motors. The speed value is a percentage, where 0.00 = 0% and 1.00 = 100%.

Here is an example of horizontalMovement in use:

```python
import libraries.HorizontalMovementLib
libraries.HorizontalMovementLib.horizontalMovement(nav, True, 0.5)
```

## zDepthLib

Fire and forget. Makes the robot move vertically.

verticalMovement defaults in order:
- verticalDect = True #This controls the Z axis. True is down, False is up.
- verticalSpeed = 0.2 #This sets the speed of the motors. The speed value is a percentage, where 0.00 = 0% and 1.00 = 100%.

Here is an example of verticalMovement in use:

```python
import libraries.verticalMovementLib
libraries.verticalMovementLib.verticalMovement(nav, True, 0.5)
```

## zHoverLib

Fire and forget. Same as vertical movement, but with a default motor speed calculated to maintain depth.

HoverMovement defaults in order:
- nav has no default
- hoverDect = True #This controls the movement of the robot on the Y axis. True is down and False is up. Because the robot is positively buoyant, this should be set to True.
- hoverSpeed = 0.15 #This sets the speed of the motors when holding. The speed value is a percentage, where 0.00 = 0% and 1.00 = 100%. 0.15 is the speed that currently maintains depth, but this will need to be changed if the robot's buoyancy changes.

```python
import libraries.hoverMovementLib
libraries.hoverMovementLib.hoverMovement(nav, True, 0.15)
```

## rollrotationLib

Fire and forget. Makes the robot roll. sensorsLog for 4.5 seconds will roll 2 times (720 degrees). Note that hover will have to be called again afterwards.

rollMovement defaults in order
- nav has no defaults
- rollDect = True #This now controls the X rotational axis. TRUE is right, FALSE is left.
- rollSpeed = 0.35 #This sets the speed of the motors. The speed value is a percentage, where 0.00 = 0% and 1.00 = 100%.

Here is an example of rollMovement in use:

```python
import libraries.rollMovementLib
libraries.rollMovementLib.rollMovement(nav, True, 0.35)
```

## yawRotationLib

Fire and forget. Makes the robot rotate horizontally.

rotationMovement defaults in order:
- nav has no defaults
- rotationSpeed = 0 #This sets the speed of the motors. The speed value is a percentage, where 0.00 = 0% and 1.00 = 100%.
- rotationDect = True #This controls the Z rotational axes. True is right, False is left.

```python
import libraries.yawRotationLib.rotationMovement
libraries.yawRotationLib.rotationMovement(nav, 0.3, True)
```

## sensorsLogLib

NOT fire and forget. Logs acceleration, gyroscope, and magnetic field on 3 axis. Use in place of time.sleep for fire and forget commands. Outputs to a .csv file.

sensorsLogLib defaults in order:
- nav has no defaults
- init?
- message has no defaults #A message written into the csv file. Describe what the robot is doing to help interpret the data
- sensorLogTime = 5.0 #Time in seconds sensors log for. Logs 10 times per second.

Here is an example of sensorsLog in use:

```python
import libraries.sensorsLogLib
libraries.sensorsLogLib.sensorsLog(nav, "message", 5)
```



