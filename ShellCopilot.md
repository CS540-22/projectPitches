# **Shell copilot**

Members:
* Aiden Rutter
* Justin Langston
* Rachael Dylewski

Use the codex API powering github copilot to power shell completion. Copilot can already effectively perform shell script completion, so with some modifications, it should also be able to be applied to an interactive shell. This can be done through traditional completion, similar to what zsh might offer, or additionally a hotkey or command to enter a 'describe mode' which allows a natural language description of what you want to accomplish with the shell.

ie, 

`compress folder lab3 to lab3.tar.gz`

would result in an appropriate tar command to be displayed in the shell and optionally executed.

Some additional enhancements include:
* Enhance prediction with additional context: history, working directory, PATH, return status, git context
* Show your work: Get a natural language description of commands
* Proceed with caution!: Display a warning in your powershell for potentially destructive commands. Get a natural language justification as to why.
* Break it down: Summarize verbose documentation or logs.
