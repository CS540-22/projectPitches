A tool which suggests projects for developers to work on based on what they want to do.

Uses ML to suggest project based on resume, area of interest, specific technology, and/or desired company.
  - Easy: Can just be a large database with a decent front-end.
  - Medium: Above plus github crawler to populate project database and ML to suggest projects based on likes and dislikes?
  - Hard: Above plus resume analyzer feeding into ML along with desired company/technology to suggest projects.

Example user story:
 - Alice want a job at Google.
 - She opens up our app.
 - She selects that she wants to work on a project which would help her get an interview with Google.
 - Perhaps she also would prefer to work with Go because she's wanted to learn it for a while.
 - Our app would look for projects previously built by developers who currently work/have worked at Google, prioritizing the projects involving Go, and return these to Alice.
 - Alice would then look through this list, liking ones that look interesting and disliking the ones she doesn't care for.
 - These likes and dislikes would hopefully work to better suggest projects in the future.
 - In the end, Alice can choose to begin a project based on one or many of her liked projects.
 - Hopefully, Alice finishes her project and displays it as an example of her expertise to Google or any other company.

Technologies:
  - database: I think this can just be mysql or any other relational thing.
  - database API: REST on Go
  - front-end: Bootstrap on top of ???
  - github crawler: Rust
  - ML: Probably Python
  - resume analyzer: Kotlin???

Architecture: We have a persistent database running 24/7 on a Raspberry Pi. For all other tools, we can spin them up in their own docker containers for local execution and testing. We have tested this, and it works really well.

Features and technologies are not set in stone, just first thoughts.

Current team is Isaac Sikkema (me) and Phillip Hicks. Hoping for one more person.
