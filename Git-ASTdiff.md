
# Git ASTdiff

Uses a syntax tree of code changes from git commits to perform a structural / graph-based diff of code changes.

## Usages

- Identify changes that affect the program and separate them from non-code changes
  - automatically skip CI for non-code changes
- Follow code blocks across files
  - understand how blocks of code get copied/moved between files
  - find code reuse and suggest changes
  - make automated fixes in copied code blocks, even if names and comments change
- Rate contributions of comitters in educational settings
  - Identify students who properly use version control to update code, or those who rarely touch any actual program behavior at all
- Generate human-readable representations of changes in control flow
  - "find a commit that modified this function's control flow"

Essentially it allows for diffs to be viewed / parsed / generated in a similar manner to how a language is actually interpreted, and how it's behavior is explained in human terms.

## Implementation

The plan is to create a git command that operates in the same context and arguments as `git diff`. Using WorldSyntaxTree we can efficiently generate graph data from source code, so we need to implement the CLI, graph diff, UX, and other functionality options.

