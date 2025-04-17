# Turtles Program Task
In this activity, you will be updating the Turtles language.

## Adding loops
The first thing we will do is add loops to the language.

- Statement is known as a **rule**. It says that a Statement is either a MoveStatement or a TurnStatement. <!-- {pointed: panel-xtext} -->
- Add the line ```| LoopStatement``` to the rule so that a Statement could now also be a LoopStatement.  <!-- {pointed: panel-xtext} -->
- Next we need to define what a LoopStatement rule is. Define the rule in the grammar as so ```LoopStatement: 'repeat' times=INT 'times' '{' statements+=Statement* '}';```  <!-- {pointed: panel-xtext} -->
- This addition means you can now make a Statement repeat multiple times.
- Click the green button on the grammar panel to run generate the editor. If you check out your console, your editor should have been generated successfully.  <!-- {pointed: panel-console, spotlighted: panel-xtext } -->

## Conclusion
Well done! You have successully added loops to the Turtles language!
