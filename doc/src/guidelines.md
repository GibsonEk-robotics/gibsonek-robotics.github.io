# Code guidelines

## Naming (Variables, Functions, Files)

**General Naming**  
The name should be conscience and the function/purpose should be discernible from the name. Avoid single letters, misspellings, and unclear names.  

Good: ```rotationDegreesYAxis```   
Bad: ```yr, thetaY, rotDeg```

**Symbols** 

Do not start a name with a number and avoid the use of symbols. 

Good: ```motorControl2ndTest```  
Bad: ```2ndTestMotorControl, motorControl-2ndTest,etc.``` 

**Libraries**  
End the name of a library file with ‘Lib’ 

Good: ```compassMovementLib```  
Bad: ```compassMovement```

**camelCase**

Use camelCase for naming variables, files, functions etc. With camelCase you don't capitalize the first word but the first letter of every subsequent word is capitalized.

Good: ```compassMovementLib ``` 
Bad: ```compassmovementlib```  
Bad: ```CompassMovementLib```  
Bad: ```Compassmovementlib```

Using uniformed capitalization makes code more readable by everyone/

## Commit Guidelines

Limit commits to a single purpose. 

Detail the changes you made and issues solved in your commit messages. 

Good: ```Fixed rotation issue with rollRotationLib. Was rolling the wrong direction on the z-axis, now outputs correct direction.``` 

Bad: ```“Fixed roll”, “Changed code”, “The Voices”```

## General Code Guidelines

All code in the main.py file must be inside a Try Except to prevent damage to the robot. 

**Nav**

Any function that uses the nav variabel (ie. interacts directly with the robot) must have nav as the first argument. 

Good: ```python
robotForward(**nav**, speed, direction, time)
```  
Bad: ```python
robotForward(speed, **nav**, direction, time)
```

**Pull Requests**

Code will be reviewed before added to main program

**Orientation** 

You must go through a brief orientation before making changes. 

