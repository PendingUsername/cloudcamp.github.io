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

9. Redirection and Pipelines: The ls -l command can be redirected using the greater-than sign (>) followed by a file name. You can also append output to an existing file using >>, which will add new content to a file without overwriting it. To redirect standard errors, you can use 2> followed by a file descriptor to indicate error redirection to a different location. To combine standard output and standard error and redirect them to the same file, you can use 2>&1. Alternatively, you can achieve the same result with &>. You can redirect the output of multiple commands to a file, for example: cat 1.txt 2.txt > 3.txt
This command will combine the contents of 1.txt and 2.txt and save the result in 3.txt. You can also pipe the output of one command into another using pipelines (|). For instance, using | less can help you navigate through large files more easily. You can narrow down your search by combining the grep command with pipelines, like | grep echo. Additionally, you can sort the output of a command using | sort. To extract specific lines from a file, you can use head and tail. head -n 1 will give you the first line of a file, making it easier to locate specific information. Conversely, tail will display the last lines of a file. These redirection and pipeline techniques are essential for efficiently managing and processing data in the command line environment.

10. How to View Permissions and Modify Them: The ls -l command will display various information about files and directories. It indicates file types with a 'd' for directories (highlighted in green) and '-' for regular files. Following this, you'll find the user permissions, group permissions, and other permissions (if you are not part of the group). The owner's name is listed to the right. The owner has full control over the file. To change the ownership of a file or directory, you can use the chown command. For example, sudo chown root newFile.txt would change the owner to the root user (sudo privileges are needed). To modify the group ownership, you can use sudo chown : followed by the group name, but this changes the group, not the user. Alternatively, you can use the chgrp command followed by the group name and the file/directory name to change the group ownership. To modify permissions, you should use the chmod command. For instance, chmod +x grants execute permissions to a file. You can also use the octal format to assign values for read (r), write (w), and execute (x) permissions of a file. Understanding and managing permissions is crucial for effective file and directory management in a Unix-like operating system.
Example:
  owner      group     others
  r  w  x    r  w  x   r  w  x
 (4)(2)(1)  (4)(2)(1)  (4)(2)(1)

11. Bash Script: 
