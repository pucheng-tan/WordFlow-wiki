Coding Convention
Milestone 3
## 2.2 Imports
Used to import packages and modules only, not for individual classes and functions. 
e.g   from x import y 

## 2.3 Packages
Modules should be imported using full pathname locations and correct package name.
e.g from doctor.who import jodie      where jodie is in doctor/who/jodie 

## 2.4 Exceptions
Assert should be used to ensure internal correctness not to enforce convention. Exceptions should be used with conditions.
e.g
if not port:
      raise ConnectionError(
          'Could not connect to service on port {minimum} or higher.')
    assert port >= minimum, (
        'Unexpected port {port} when minimum was {minimum}.')
    return port

## 2.5 Global Variables
Should be avoided but if needed should be declared at the module level by prepending an “_”. Constants should also be declared in all caps.
e.g  MAX_HOLY_HANDGRENADE_COUNT = 3.

## 2.6 Nested/Local/Inner Classes and Functions
Do not nest a function just to hide it from users of a module. Instead, prefix its name with an “_” at the module level so that it can still be accessed by tests. 

## 2.7 Comprehensions & Generator Expressions
Okay to use for simple cases. Try to fit in one line and avoid using multiple for loops.
e.g  result = [mapping_expr for value in iterable if filter_expr]

    result = [{'key': value} for value in iterable
          if a_long_filter_expression(value)]

## 2.8 Default Iterators and Operators
Use a default iterator for types that support them instead of methods that return lists. 
e.g  for key in adict: ...
      if key not in adict: ...
      if obj in alist: ...
      for line in afile: ...
      for k, v in adict.items(): …
Never use  dict.iter*()   unless nessesary.

## 2.9 Generators
Use “Yield” instead of “Returns” in the docstring for generator functions.

## 2.10 Lambda Functions
They are okay to be used for one liners and their code should be less than 80 chars otherwise it is better to create a regular nested function.

## 2.11 Conditional Expressions
Okay to use for simple cases. Each portion must fit on one line: true-expression, if-expression, else-expression. Use a complete if statement when things get more complicated.
e.g    x = 1 if cond else 2
    one_line = 'yes' if predicate(value) else 'no'

## 3.11 Files and Sockets
Explicitly close files and sockets when done with them. “With” statements are preferred for managing files.
e.g
with open("hello.txt") as hello_file:
    for line in hello_file:
        print(line)

## 3.12 TODO Comments
Used for code that is temporary, a short-term solution, or good-enough but not perfect.
e.g
# TODO(Abdul): Use a "*" here for string repetition.
# TODO(Sarah) Change this to use relations.

## 3.13 Imports formatting
Imports should be on separate lines except for typing imports.
e.g
import os
     import sys
     from typing import Mapping, Sequence

## 3.14 Statements
Generally one statement per line but you are allowed to put the results of a statement in the same line.
e.g
if foo: bar(foo)

## 3.15 Accessors
If the accessor function is trivial it is better to use public variables. If the accessor is non trivial, function calls starting with “get_” or “set_”.

## 3.16 Naming
Function names, variable names, and file names should be descriptive; eschew abbreviation. In particular, do not use abbreviations that are ambiguous or unfamiliar to readers outside your project, and do not abbreviate by deleting letters within a word. Caps for class names. Test functions should all begin with “test_”. 
e.g
module_name, package_name, ClassName, method_name, ExceptionName, function_name, GLOBAL_CONSTANT_NAME, global_var_name, instance_var_name, function_parameter_name

## 3.17 Main
If a file is meant to be used as an executable, its main functionality should be in a main() function, and your code should always check “if __name__ == '__main__'” before executing your main program, so that it is not executed when the module is imported.
if __name__ == '__main__':
    main()

## 3.18 Function length
Small and focused functions are prefered. If a function exceeds 40 lines consider breaking it up.

## 3.19 Type Annotations
In methods, only annotate self. 

?? 


* Be Consistent *
