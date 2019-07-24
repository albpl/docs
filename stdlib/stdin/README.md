# Standard Input (stdin)

This is the easiest way to assign a value entered by the user to a variable. The method employed to make use of the Standard Input, or _stdin_, is the `in` method.

## in method

To ask the user for a value to store, we use this method. This is the simplest and most common method in Standard Input.

#### Structure

`in $identifier ;`

Where `in` is the reserved keyword referring to the in method, and `$identifier` refers to the variable in that we want to store the value. You must change `identifier` by the actual identifier of the variable. The variable must have also been created previously. Check out docs/variables/ for further information.

There is no need to add the variable's data type, because the in method itself will look for a value entered at the console, according to the data type needed, that the in function will read automatically from the variable information.

#### Example

`in $myInt ;`

Obviating that `$myInt` is a variable of type `:int` that has been defined and initialized previously, when the program execution arrives at this order, it will stop and wait until a value has been introduced. In case the value entered does not correspond to the variable's data type, an exception will be thrown.

Now, the user will enter a value chosen by himself/herself, and it will be assigned to the `$myInt` variable, so that we can access and modify its value later.

## Input Initialization

This is a way to assign a user-defined value to a variable during its creation.

#### Structure

`var :data_type identifier in ;`

Here,

- `var` is the reserved keyword used to create variables.

- `:data_type` refers to the data type of the variable to be created. It will later be used by the `in` function to search for a value of this exact data type. It must be changed by the actual data type of the variable (`:int`, `:float`, `:hex`, `:oct`, `:bin`, `:char`, `:str`). Look at docs/variables/ for further information.

- `identifier` refers to the variable's identifier. It must be changed by the actual identifier.

- `in` refers to the in method to make use of the Standard Input. The execution will stop and wait until a value is entered to be assigned to the variable about to be created and initialized. If the data type of the input is not the same as the variable's, an exception will be thrown.

#### Example

`var :str myString in ;`

A variable called `$myString` of type `:str` will be created, and it will be initialized with a user-defined value.

For example, if we introduce the string _Hello!_, we will later be able to access this value in other functions, as the out function, so we can see that the output is the same as the previous input (`outv $myString ;`).
