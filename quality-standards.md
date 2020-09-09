# Quality Standards

## Simplicity

Simple code makes its intent obvious.
Decomposition and Naming help a developer
to understand without ambiguity.

Low duplication yields a single source of truth, reducing surprises
during maintenance.

Low function-complexity helps in testability as well.
Towards this, the cyclomatic complexity-limit for a method is 3.
[This workflow](https://github.com/Engin-Boot/get-started/tree/master/workflow-files/complexity)
implements such a limit.

## KPI

- Zero compiler warnings
- Zero findings from static analysis
- High test coverage

## Workflows

These workflows are starting points to gate according to
the above list of KPI.

[Complexity-limit](https://github.com/Engin-Boot/get-started/tree/master/workflow-files/complexity)

[C++ starter workflow](https://github.com/Engin-Boot/get-started/tree/master/workflow-files/cpp)

[C# starter workflow](https://github.com/Engin-Boot/get-started/tree/master/workflow-files/cs)

[Java starter workflow](https://github.com/Engin-Boot/get-started/tree/master/workflow-files/java)

### Tips

- These are example workflows. They would need modifications to use.
- Start setting up your workflow like unit tests:
Write the smallest piece of code to get the workflow functional.
Then build on top of it.
- Quality @desk: Install these tools locally. You will notice failures faster
when you run locally.
- Quality @desk: Look for plugins to the IDE and install them. Then you can address
the issues as you type them!
