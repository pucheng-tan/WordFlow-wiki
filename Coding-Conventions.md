Coding Convention
Milestone 3
# Style Guide and why we chose it
//TODO: we using google style guide at link, and having it implemented using yapf? pylint?
- a few paragraphs explaining your choice 
- hyperlinks to official documentation / more information
# High-level Guidelines
//TODO
- and some high level guidelines in your own words
# Examples
* some code examples showing your conventions / styles in action

//TODO

https://google.github.io/styleguide/pyguide.html#s3.4-indentation

# Lexical Conventions

## 2.2 Imports
Used to import packages and modules only, not for individual classes and functions. 
e.g   from x import y 

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

## 2.10 Lambda Functions
They are okay to be used for one liners and their code should be less than 80 chars otherwise it is better to create a regular nested function.

## 2.11 Conditional Expressions
Okay to use for simple cases. Each portion must fit on one line: true-expression, if-expression, else-expression. Use a complete if statement when things get more complicated.
e.g    x = 1 if cond else 2
    one_line = 'yes' if predicate(value) else 'no'

## 2.12 Default Argument Values
Default arguments values are allowed so along as the default value is not mutable.

| Yes: | No: |
| ------ | ------ |
| def function(users=None) | def function(users=[]) |

## 2.14 True/False Evaluations
All “empty” values are considered False. This applies to 0, None, [], {}, and ‘ ‘.

As a result, when making an if statement to test whether something is empty, use the “empty” value itself for an "implicit" False.

Never use == to check for False

| Yes: | No: |
| ------ | ------ |
| if not users: | if len(users) == 0: |
| if not flag: | if flag == False: |

Warnings:

If explicitly checking for a None value, use if foo is None or if foo is not None.

If the value is known to be an integer (not the result of len( )), the value may be compared against the integer 0.

# 3 Python Style Rules

## 3.1 Semicolons
Lines cannot end with a semicolon.
Do not put two statements on one line using a semicolon.

| No: | 
| ------ | 
| x = 5; | 
| x = 5; y = 6; |

## 3.2 Line length
Each line is at most 80 characters long. The following exceptions are
1. Long import statements.
2. URLs, pathnames, or long flags in comments.
3. Long string module level constants containing no whitespace that would be inconvenient to split across lines such as URLs or pathnames.

### 3.2.1 Breaking apart lines
Breaking apart a line with backslash continuation can only be done for with statements requiring three or more context managers. If the with statement only has two context managers and exceeds 80 characters, use a nested with statement.

Otherwise, use Python’s implicit joining with parentheses.

Yes:

x = (‘a string more ‘    

     ‘than 80 characters’) 

\# For more information visit:

\# www.thisisthelongesteuropeandomainnameallovertheworldandnowitismine_abcdefghijk.eu

No:

x = ‘a string more’\

    ‘than 80 characters’

\# For more information visit:

\# www.thisisthelongesteuropeandomainnameallo\

\# vertheworldandnowitismine_abcdefghijk.eu

## 3.3 Parentheses
You are allowed to use parentheses for tuples and when returning tuples, but it is not required.

Do not use parentheses in return statements except for tuples or implied line continuation.
Do not use parentheses for conditions in for loops and while loops except for tuples or implied line continuation.

## 3.4 Indentation
To indent code, use a tab set to a width of four spaces.
In the cases of implied line continuation, align with the opening delimiter.

Yes:

x = [6, 5,

     4, 3]

### 3.4.1 Trailing commas in sequences of items
If listing sequences, the first element must not be on the same line as the opening container token and the last item must not be on the same line as the closing container token.
The last item must have a comma at the end.

Yes:

x = [

    file_1,

    file_2,

    file_3,

]

## 3.5 Blank Lines
Put two blank lines between top-level functions whether they are function or class definitions. Put one blank line between method definitions and the class line and the first method.

Do not use a blank line after a def statement. Use your judgment when it comes to placing blank lines within functions and methods.

## 3.6 Whitespace
Whitespace is not allowed inside parentheses [], brackets, () or braces {}.
Whitespace is not allowed before a comma, semicolon, or colon. Whitespace must be placed after a comma, semicolon, or colon, unless it is the end of the line.
Whitespace is not allowed before open paren/bracket that starts an argument list, indexing or slicing.
Trailing white space is not allowed.

Place a single space on either side for assignment, comparisons, and Booleans. For arithmetic operators, use your own judgment.

When passing a keyword argument to a default parameter value, do not use spaces around = . Spaces must be used though if a type annotation is present as well.

| Yes: | No: |
| ------ | ------ |
|[] or () or {} | [ ] or ( ) or { } |
| user[1] or {music_record: label} | user[ 1 ] or { music_record : label } |
| word[1: 4] | word[1 : 4] |
| x = 4 or y >= 3 | x=4 or y>=3 |
| x = a/*b + c/*d | x = a /* b + c /* d | 
| some_function(x) | some_function (x) |
| some_function(a, b=False) | some_function(a, b = False) |
| some_function(x, y: float = 1.0) | some_function(x, y: float=1.0) 

Whitespace is not allowed to vertically align tokens.

Yes:

x = 1000

long_name = 2

## 3.10 Strings
Use single quotations for strings. When indicating quotations within strings use double quotes.

| Yes: | No: |
| ------ | ------ |
| x = 'Hello' | x = "Hello" |
| y = 'She says, "Hello."' | y = "She says, 'Hello.'" |

When accumulating a string in a loop, do not use + and += operators. Instead add each substring to a list and ‘ ‘.join the list when the loop has finished.

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

# Code Documentation Convention

## 3.8 Documentation
Every function must have a docstring.

The only exceptions are if all of following criteria is met:
1. The function is not externally visible.
2. The function is very short.
3. What the function does is obvious.

### Docstrings
To write a docstring, use the three double-quote format.

A one line summary at the top is necessary. It must end in either a period, question mark, or exclamation point.

If writing more, a blank line must follow the one line summary. The rest of the docstring which must be aligned at the same cursor position as the first quote of the first line.
The doc string should be worded in a descriptive style and not an imperative style.

If a method is overwriting a method, it is acceptable to write a simply docstring such as “””See base class.”””. A new docstring must be written if overridden method’s behaviour is substantially different or if there are additional details such as side effects.

Args: The parameters should be listed by name followed by a colon and then a space.

Returns: (or Yields: for generators) Description of the type being returned and the semantics.

It is not necessary if:
1. The function returns
2. The opening line of the docstring starts with Returns.
3. The opening sentence is enough to describe the return value.

Raises: Write all the exceptions relevant to the interface.

Yes: 

""" One line summary here. 

Rest of docstring here.

Args:

    arg1: description
    arg2: description

Returns:

    Description of return value.

Raises:

    exception 1: description
    exception 2: description
"""

### Classes
Classes should have a docstring in the same format as functions and methods except with Attributes replacing Args listing and describing only public attributes. The sections Returns and Raises are also removed.

### Block and Inline Comments

There are two cases:
1. If the operation is complicated, place the comment before the operation.
2. If the operation is non-obvious, place the comment on the same line.

Always capitalize the first letter of a comment. Use proper punctuation, punctuation, and grammar.
Always start a comment one space away from #.

For comments on the same line as the operation, start the comment two spaces away.

Never describe the code.

| Yes: | No: |
| ------ | ------ |
| x = x + 5\s\s# Adjust the border | x = x + 5\s#adjust the border |
|  | # Now, increment i by 1 |

* Be Consistent *
