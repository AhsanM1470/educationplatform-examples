# Building Our First Textual Language
In this tutorial we will implement a small domain-specific language...

## Write The Grammar
- The first rule in a grammar is always used as the start rule.
- Replace the Greeting rule with the rule Domainmodel: (elements+=Type)*; <!-- {pointed: panel-xtext} -->
- Add the rule Type: DataType | Entity; <!-- {pointed: panel-xtext} -->
- Next, add the rule DataType: 'datatype' name=ID; <!-- {pointed: panel-xtext} -->
- Explain the ID rule. <!-- {spotlighted: panel-xtext} -->
- Add Entity rule. <!-- {pointed: panel-xtext} -->
- Extend Entity with optional superType. <!-- {spotlighted: panel-xtext} -->
- Describe features block. <!-- {pointed: panel-xtext} -->
- Add the Feature rule. <!-- {pointed: panel-xtext} -->

- Finally, generate language artifacts by clicking the "Generate Editor" button. <!-- {pointed: panel-xtext, spotlighted: panel-console} -->
