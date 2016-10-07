# Simple Unit DSL

This project attempts to create a module that can handle a very simple domain specific language (DSL) 
for declaring/specifying instances of units based on Java JSR 363.

The DSL supports the following algebraic operations with Unit:
 
* divide: represented by the `/` character
* multiply: represented by the `*` character
* pow: represented by the `^` character
* root: represented by the `!` characters
* shift: represented by the `>>` characters

~~~~
<declaration> ::= <label>:<algebra>
<algebra> ::= "" | <function> 
<function> ::= <division>|<multiplication>|<power>|<root>|<shift>
<power> ::= <unit-symbol>^<integer>|<double>^(<double>|<integer>)
<multiplication> ::= <unit-symbol>*<unit-symbol>
<integer> ::= ["-"]<number>
<double> ::= ["-"]<number>.<number>
<number> ::= <digit> [ <number> ]
<digit> ::= 0|1|2|3|4|5|6|7|8|9
<unit-symbol> ::= any unit symbol recognised by SimpleUnitFormat.parse()

~~~~

All whitespace in the formula is stripped prior to processing.