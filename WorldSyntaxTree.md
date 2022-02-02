
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

