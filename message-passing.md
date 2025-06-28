# Message passing in object oriented programming

there are 2 ways to write a software  program - procedure oriented and resource oriented

## procedure oriented

calculateArea(shape arg)
 - (shape? square) arg * arg
 - (shape? circle) pi * arg * arg

## resource oriented

Square
- findArea
- findPerimeter

if we wanted to add a new shape in procedure oriented program, we will modify calculateArea method which contains logic for all other shapes 
- this is inherently risky leading to bugs

in resource oriented approach, we create a new shape and implement the findArea method 
- thereby the change is localized to just that shape leading to a robust software where the previously tested parts remain unchanged

