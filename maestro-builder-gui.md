# Maestro Builder GUI

**Members (2): Ian Lumsden (ilumsden@vols.utk.edu), Kae Suarez (dsuarez1@vols.utk.edu)**

## Intro/Background

This project is (tangentially) related to High Performance Computing (HPC). In HPC, developers and users work on extremely powerful, but complex, systems called
clusters or (for the most powerful systems) supercomputers. Because of their complexity, it can be difficult for even skilled computer scientists to develop
and execute code on these systems. However, they can be even more tricky to use for one of HPC's largest userbases: domain scientists (e.g., physicists, chemistist, biologists).
These users usually have less technical knowledge than other HPC users, and they also usually have the most complex codebases that they want to execute on HPC systems.
These codebases usually take the form of scientific simulation and analysis workflows.

To assist users in executing their scientific workflows on HPC resources, a team at Lawrence Livermore National Lab (LLNL) created Maestro, a lightweight workflow orchestration
tool. With Maestro, instead of having to manually configure and launch each part of the workflow on the HPC system, scientists can create a special YAML file describing their
workflow. Based on this file, Maestro will dynamically launch pieces of the workflow to HPC resources and monitor the workflow for the user. Additionally, by abstracting
the execution of workflows away from the details of the specific system they run on, Maestro provides enhanced replicability and reproducability to workflows.

## Project Concept

Although Maestro already abstracts the process of running scientific workflows on HPC resources, additional abstraction could still be useful to the average domain scientist.
This further abstraction is the goal of this project. In this project, the team will create a Graphical User Interface (GUI) for Maestro. Broadly, this GUI will consist of
two types of elements: 
1. A canvas-like element to allow users to see and manipulate their workflow
2. Several "forms" to do things like create, modify, and delete elements of the workflow

There are two possible "final outputs" of this GUI. The first and more managable of the two is to generate a Maestro YAML file based on the current state of the GUI (i.e.,
what the workflow currently looks like in the canvas). The second output, which is more of a stretch goal, is to both create the YAML file and then actually launch Maestro
on the current system.

In terms of implementation, three broad approaches are currently being considered, but this can easily change with additional members, input, and discussion.
1. Design the GUI as a fully native app (e.g., with a library like Qt)
2. Design the GUI as a web app
3. Design the GUI in a way that would allow it to be built as either a native app or a WASM binary (e.g., write with Qt then compile with Emscripten or GCC/Clang)

## January 31 Update:

To make this project more feasible for the course, the concept above has been broken down into 4 goals:
1. Create a visualizer that will take a Maestro YAML file and visualize the workflow in a Canvas
2. Add forms to the visualizer to allow for workflow elements to be added, edited, or deleted
3. Add the ability to export the workflow state to a Maestro YAML file using a form
4. Add the ability to execute Maestro on the current system

In this project, we will try to perform as many of these goals as is feasible. At the very least, we will complete the first goal.
