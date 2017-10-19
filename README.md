# Using Catch with CMake

This is a quick example of using Catch with CMake to build two executables:

  - tests
  - main

The `tests` executable will execute the tests and `main` will be compiled
without any test code and will just call the Factorial function and output
the result to the screen.

The `include` and `src` folders will be used by the `main` application and
comprises all of the non-test code, while the `tests` folder contains test specific
code and will only be compiled for the `tests` executable.

This is based on the Catch tutorial at https://github.com/philsquared/Catch/blob/master/docs/tutorial.md.
