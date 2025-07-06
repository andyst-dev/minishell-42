# Minishell
Well, not so mini as it turns out...

_Co-created with @42andy_




## So, what is this project about?


Minishell is essentially as the name implies, a somewhat cut-down version of a UNIX shell such as Bash. The penultimate C language project in 42's cursus, it's usually considered to be one of the most challenging. Using raw C with limited access to existing libraries and functions, we built a leak-free and crash-proof shell working entirely at the POSIX system-call level that parses commands, executes any number of pipes/redirects/heredocs etc, manages environment variables and handles various signals. This project forces, by no uncertain means, the creator to truly dive into [very] low-level programming particularly concerning memory management and string manipulation, while simultaneously becoming much more comfortable in the terminal and harnessing the power of existing shell functionality.




## Sounds complex, how does it work? 

Well, essentially it goes like this:


![Minishell Flowchart](https://github.com/user-attachments/assets/96e36cf9-f26e-4ff6-83d7-905d3a9d514b)



Easy, right?

_Feel free to clone the repo and try it out - feedback welcome_!
