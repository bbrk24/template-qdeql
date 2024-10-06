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

## Using Template Qdeql

You can run Template Qdeql directly with `civet src/index.civet` if you have Civet installed globally (using `npx civet` to use the local Civet doesn't work -- see [this issue](https://github.com/npm/cli/issues/7821)). Alternatively, you can compile to JS using `npm run build`, and then run `node dist/index.mjs`.

After running `npm run build`, you may `npm i -g .` to add template-qdeql to your PATH as `tqdeql`.
