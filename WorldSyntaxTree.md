## Project Idea

Current Team members: Ben Klein (bklein3), Ben Roberson (brobers3)

In need of 1-2 more team members!

https://github.com/utk-se/WorldSyntaxTree

World Syntax Tree is a project to allow language-agnostic graph-based queries across as many codebases as possible.

It can be used for a variety of applications, imagine being able to ask any of these questions across all repositories and languages:

- Locate nested loops, classes, functions, and other complex code structures
- Locate the same algorithm implementation across different languages
- Resolve imports/includes using their local or aliased name, and automatically generate example real-world usages for libraries
- See how code changes by syntactic structure, rather than by lines
- Identify logical / flow changes between commits
- Follow the copy/paste/move of entire functions between files instead of looking like simple addition/deletion of lines

And many more!

Right now only the infrastructure part of the project is working, what's needed is an interface that allows users to write and visualize these kinds of queries effectively, most likely a web UI.

If you've ever used Neo4j you might have an idea of the interface we'd like to emulate. If not, there are some example WST query results used as the background of my post at https://unhexium.net/research/neo4j-performance-adventures-for-petabyte-scale-datasets/ and they look cool, right?

============================================================================================


# World Syntax Tree

https://github.com/utk-se/WorldSyntaxTree

## Overview

WorldSyntaxTree is a library, a collection of CLI utilities, and a research-oriented tool for exploring code across language boundaries and at incredibly large scale.

This is accomplished by storing WST datasets in the form of queryable, explorable graphs. The graph stores as much information as possible about the code, sometimes including the actual text contents of files, functions, variables, etc. In essence: all parts of the syntax tree for every repository, commit, and file of input are accessible by traversing the graph.

## Why is this useful?

On top of the use cases that make World of Code desirable, with World Syntax Tree you can also:

- find usage of a particular algorithm across languages
- locate pieces of code by structure while ignoring text content like naming and spacing
  - a huge number of higher-level use cases on top of this: scanning for copied security vulnerabilities, copyright / plagiarism analysis, assertion of consistency in formatting tools, and many more
- compare pieces of code between commits to retrieve a AST diff, representing only changes to functionality instead of changes to lines (another planned project)
- analyze usage of language libraries and understand usage patterns for example generation
- follow cut/copy/paste/rename operations across files and across repositories, which would otherwise look like simple line additions/deletions

## FAQ

> There's already so much code already written? What's there left to do?

In actuality, we are still very far from achieving the goal of the project. Collecting and storing data is only half the problem, the other half (or more) being search, pattern matching, analysis, visualization, comparison, and evaluation.

> Why the name?

"World Syntax Tree" was derived from "World of Code" in that they have similar goals, but very different approaches. Much of the data from World of Code can be used as source / input information for constructing WST datasets and thus we wanted to show some relation.

## People

- Ben Klein: original author of WST

============================================================================================


# Git ASTdiff Idea

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
