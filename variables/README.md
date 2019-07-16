# Variables

### What is a variable?
A variable is a storage location in the memory of our computer. It has an identifier (in programming, usually a name), and a value in that location (either known or unknown).

Variables go through several phases, which are:

- Creation
- Initialization (assignment of a value during creation)
- Value changes (not mandatory)
- Access to memory (not mandatory)
- Deletion (to clear memory)

Now, each phase of the _life_ of the variable will be explained in detail.

## Creation and initialization

To create a variable in ALB, follow this structure:

`var :data_type identifier value ;`

- `var` stands for _variable_. Every variable **must** be created using the `var` reserved keyword.
- `:data_type` must be replaced for the desired data type for your variable (remember to write a colon (":") inmediately before the data type identifier).
Data types in ALB are the following: `:int` (integer, numeric), `:float` (floating-point number, numeric), `:hex` (hexadecimal, numeric), `:bin` (binary, numeric), `:oct` (octal, numeric), `:string` or `:str` (string (array of characters), non-numeric), and `:char` (character, non-numeric).
- The `identifier` must be replaced by the name desired by you to identify this variable.
- `value` is the value that you want the variable to be created and initialized with. If not specified, the variable will be initialized with a default value (only in numeric variables, and the default value is 0). Go to the default() function section in this README for further information and to numeric_variables.alb to see a practical example. **Non-numeric variables must be initialized manually**.

#### Example

`var :string hello "Hello, world!" ;`

Here, a variable (`var` is present) of type `:string` is being created under the identificator (name) `hello`, and it holds the value `"Hello, world!"`, which can be accessed later.

## Value changes

This phase may not be in every program where variables are used, although it is very common. No exceptions should be thrown as long as the variable holds a (even default) value.

To change the value of a variable, follow this structure:

`$identifier = new_value ;`

- `$identifier` is the identifier (name) of the variable to change its value  preceded by a dollar sign ("$"). From now on, you must remember that **variables are accessed by writing its identifier preceded by a dollar sign**. Basically, you **must** always use it except in creation and deletion.
- `=` is the assignment operator (used in variable changes).
- And `new_value` stands for the new value you want to assign to the variable. It can be a raw value of the variable data type (e.g. `$foo = 1 ;`, obviating that the variable `foo` is of type integer and changes its value to 1, a raw integer numeric value), a value stored in another variable (e.g. `$foo = $bar ;`, where, obviating that variables `foo` and `bar` are of the same data type, the `foo` variable's value changes to the one stored in the `bar` variable, remaining this last one unmodified. Note also that accessing a variable the way `bar` variable has been accessed behaves as a raw value), a set of arithmetic operations (e.g. `$foo = 3 + 4 ;`, where, obviating that `foo` variable is of type `:int`, the new value stored in it will be the result of the `3 + 4` operation, so the new value of `foo` will be 7), value changing functions, or a mix of them (e.g. `$foo = $bar + 1 ;`, where, obviating that `foo` and `bar` are both of type `:int`, the new value of `foo` will be the value of `bar` plus 1).

## Access to memory

This is, for example, when we want to display the value stored in a variable:

`outv $foo ;`

Or, when we pass a variable as a parameter to a function:

`boring_function($foo) ;`

And many other ways.

## Deletion

This method is used to free space in memory. If not done manually at any point of the program, the compiler will, by default, delete all variables from memory at the end of the program.

To delete a variable from memory, follow this structure:

`delete identifier ;`

And change `identifier` by the corresponding identifier (name) of the variable that you want to delete. Note that **this action cannot be undone**.

#### Example

`delete foo ;`

Which would delete the `foo` variable and its value from memory.

### default() function (only numeric variables)

This function changes a numeric variable's value to a default one (0 by default).

#### Usage

`$identifier.default() ;`

(Change `identifier` by your variable's identifier (name))

#### Example

`$foo.default() ;`

Obviating that `foo` is of type `:int`, its value would be changed to 0.
