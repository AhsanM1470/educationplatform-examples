# Building Our First Textual Language
In this tutorial we will implement a small domain-specific language to model entities and properties similar to what you may know from Rails, Grails or Spring Roo.

## Write The Grammar
As you can see, the xtext panel already contains a simple Hello World grammar.

1. The first rule in a grammar is always used as the start rule. In this case it is the rule Model.\
   Replace this and the Greeting rule with the rule ```Domainmodel: (elements+=Type)*;```\
   It says that a Domainmodel contains an arbitrary number (*) of Types which are added (+=) to a feature called **elements**. <!-- {pointed: panel-xtext} -->
2. Add the following rule ```Type: DataType | Entity;```.\
   The rule _Type_ delegates to either the rule _DataType_ or (|) the rule _Entity_. <!-- {pointed: panel-xtext} -->
3. Next, add the rule ```DataType: 'datatype' name=ID;```.\
   The rule _DataType_ starts with a keyword 'datatype', followed by an identifier which is parsed by a rule called _ID_. The rule _ID_ is defined in the super grammar org.eclipse.xtext.common.Terminals and parses a single word, a.k.a identifier. You can navigate to the declaration by using _F3_ on the rule call. The value returned by the call to _ID_ is assigned (=) to the feature **name**. <!-- {pointed: panel-xtext} -->
4. Next, add the rule ```Entity :
    'entity' name=ID ('extends' superType=[Entity])? '{'
        (features+=Feature)*
    '}';```\
    The rule Entity again starts with the definition of a keyword followed by a name. Next up there is the **extends** clause which is parenthesized and optional (?). Since the feature named **superType** is a cross reference (note the square brackets), the parser rule _Entity_ is not called here, but only a single identifier (the _ID_-rule) is parsed. The actual _Entity_ to assign to the superType reference is resolved during the linking phase. Finally between curly braces there can be any number of _Features_, which invokes the next rule. <!-- {pointed: panel-xtext} -->
5. Last but not least, add the rule Feature as defined below:
   ```Feature: (many?='many')? name=ID ':' type=[Type];```\
   The keyword **many** shall be used to model a multi-valued feature in this DSL. The assignment operator (?=) implies that the feature **many** is of type _boolean_. You are already familiar with the other syntax elements in this parser rule. <!-- {pointed: panel-xtext} -->

This entities grammar already uses the most important concepts of Xtext’s grammar language. You have learned that keywords are written as string literals and a simple assignment uses a plain equal sign (=), whereas a multi-value assignment uses a plus-equals (+=). We have also seen the boolean assignment operator (?=). Furthermore the example contains syntax elements with different cardinalities (? = optional, * = any number, + = at least once) and demonstrates how cross-references can be declared. 

Please consult the (Grammar Language Reference)[https://eclipse.dev/Xtext/documentation/301_grammarlanguage.html] for more details.

## Generate Language Artifacts
Now that we have the grammar in place we need to execute the code generator that will derive the various language components. To do so, click on green button labelled "Generate Editor" <!-- {pointed: panel-xtext, highlighted: panel-console} -->
