# cloudcamp.github.io
Cloud camp projects and documentation blog

# Part 1: Bash
1. What is Bash/Terminal: A terminal is where Bash commands are executed. Bash is a very powerful tool that increases efficiency.

2. Help within Bash: The help and man (manual) commands are useful to understand what each command does (e.g., man cd, cd help, cd --help). Use these commands when needed instead of Googling. Several options are allowed for commands, and these are supported by many Command Line Interfaces (CLIs). The /EXAMPLES section within the manual is also helpful. Use what is useful. To exit, simply type q.

3. Navigating the terminal: Use commands such as PWD (print working directory) to show the directory you are in. CD allows you to change the directory, and whoami tells you which user is logged in. You can also use the CD command with the file path to get to a certain directory. Push adds a directory to a stack, pop will take them off just like this using the pop and push command. cd ../../.. brings you back to different levels.

4. List with ls: ls will list the content of the directory. -a will show hidden and non-hidden files; green files are directories. S* will show any files with capital S, *[]* also allow for multiple characters. *.?? looks for single characters (i.e., MD). [[upper]] looks for uppercase characters. You can do this with lowercase as well.

5. Where am I?: Whereis helps you locate certain files. The which command will only show executable files. Find does not have any constraints.

6. Making/removing files and directories: mkdir creates a directory. -p allows you to make subdirectories under the parent directory. The touch command allows you to create files. The mv command allows you to move files from source to destination. You can use wildcards to move multiple files at once. cp allows you to copy files and directories. rm allows you to remove files, and rmdir allows you to delete directories. Wildcards can also be used with these commands.

7. Reading files: Bash allows you to read files using the cat command. The head command allows you to return the first 10 lines. Tail will give you the last 10. Use -n(x) with tail or head to get the first n amount. More and less give the whole file as if you were using a text editor. Less allows you to navigate the file using /. H will give you the commands. Grep allows you to pull out specific information (e.g., grep "DELETE").

8. Environment variables: Environment variables allow you to change the variables within the terminal. Use env to see them. Export allows you to create variables. These newly created variables are only in the current session, not in new ones. For them to remain, these files need to be in the startup files /etc/profile and the home directory .profile and .bashrc.
