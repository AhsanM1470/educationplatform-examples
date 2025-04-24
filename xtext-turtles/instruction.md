# Turtles Language Activity
In this activity you will be updating the Turtles language to support loop statements. Loop statements can be used to repeat sections of the code a specified number of times.

- The Xtext grammar panel defines various **rules** for the language. ```Statement``` is one of these and it defines a statement as either being a MoveStatement or a TurnStatement. <!-- {pointed: panel-xtext} -->
- First, add the line ```| LoopStatement``` to the rule so that a Statement can now also be a LoopStatement. <!-- {pointed: panel-xtext} -->
- Next, we need to define what a LoopStatement is. Define the rule in the grammar as so ```LoopStatement: 'repeat' times=INT 'times' '{' statemenets+=Statement '}';```.  <!-- {pointed: panel-xtext} -->
- Click the green button on the grammar panel to generate the editor. If you check out your console, your editor should have been successfully generated.  <!-- {pointed: panel-console, spotlighted: panel-xtext} -->

## Conclusion
Well done! You have successfully added loops to the language!
