# Template Qdeql

**Template Qdeql** is an esolang built as an extension of [Qdeql](https://esolangs.org/wiki/Qdeql).

Template Qdeql adds the following features to Qdeql:
- Functions. Define them with braces, then call them by stating their name:
  ```
  subtract{
     \--\/\/=/
  }
  && subtract *
  ```
  Function definitions cannot be nested, and function calls must be surrounded by whitespace.
- Integer constants. These can be redefined indefinitely and are dynamically scoped.
  ```
  x:1 # set x to 1
  y:2
  z:3

  x:y+1
  x:4_z # subtraction uses _ rather than -
  ```
  NB: because integers are evaluated during compilation, they are agnostic to the program's control flow!
- Repeated code:
  ```
  n:5
  n::=
  # compiles to "====="
  ```

Because this uses characters otherwise ignored in Qdeql, comments must start with `#`.
