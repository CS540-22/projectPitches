
# VSCodeRibbon

CodeRibbon but for VSCode\*!

\* actually VSCode-compatible: since VSCode is not open source, VSCodeRibbon will be based on Theia (https://theia-ide.org/)

## CodeRibbon???

https://coderibbon.github.io/CodeRibbon/

https://austinhenley.com/pubs/Klein2021ICSME_CodeRibbon.pdf

https://youtu.be/m5wQ87ItVGg

In short, CodeRibbon is a middle ground between split-view and canvas-based workspaces, giving not 0 or 2 dimensions of freedom (respectively), but just 1 dimension.

Instead of using tabs and panes, the Ribbon extends infinitely to the right and grows to accomodate your workspace. Open code is juxtaposed along the Ribbon axis, or within columns of the Ribbon vertically.

## Motivation

CodeRibbon for Atom gained a lot of traction, with the number one response being "can I get this for VSCode?", but VSCode extensions cannot access the internals of the editor like Atom packages can, so we need to base our changes off of a different codebase from VSCode and release a standalone editor experience. Using Theia allows us to keep an entirely separate codebase that can be built into custom, standalone editors that still maintain compatibility with VSCode extensions.

