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

11. A Bash script is a text file containing a sequence of commands designed to be executed within a Bash shell environment. These scripts are a powerful tool for automating tasks, performing system administration tasks, or simply organizing and executing sets of commands efficiently. Key Elements and Best Practices: Shebang Line: Every Bash script should begin with a shebang line, which specifies the interpreter that should execute the script. In the case of Bash scripts, the shebang line looks like this: #!/bin/bash. This line tells the system to use the Bash shell to interpret the script's commands. Execution Permission: Before you can run a Bash script, you must grant it execution permission. You can use the chmod command to do this. For instance, to give the script full execution permissions for the owner and the owner's group, while restricting others, you can use:chmod 700 Name-Of-File. Alternatively, you can use chmod +x Name-Of-File for a simpler way to grant execution permission. Moving to a Directory in $PATH: To make your Bash scripts easily accessible from any location in the terminal, it is recommended to move them to a directory that is included in the system's $PATH environment variable. Common choices include /usr/local/bin or ~/bin (for user-specific scripts). Here's an example of moving a script to /usr/local/bin: sudo mv Name-Of-File /usr/local/bin/. After moving the script, you can run it from any directory without specifying its full path.

12. Variables: Variables are used to store data within a bash script. This lets you reuse code. Constants do not change where as variables change. Read-only assigns a constant. Bash variables can be called using the '$' sign (hello_world='Hello, world!'echo $hello_world). Readonly varibles remain the same; these will not change. Constants will not change.

13. Conditional statements: success or failure of a command will trigger an action.
EXAMPLE:
#!/bin/bash
# Prompt the user to enter the first number
echo "Enter the first number:"
read num1
# Prompt the user to enter the second number
echo "Enter the second number:"
read num2
# Calculate the sum
sum=$((num1 + num2))
# Display the result
echo "The sum of $num1 and $num2 is $sum"
- This script showcases basic user input, variable assignment, arithmetic operations, and output in Bash.

14. Case statements: Allows an action based on the value of a variable or of an expression. 
    EXAMPLE: #!/bin/bash

# A script that will ask for a number and print out a message depending on the value. 

read -p "Enter a number: " n
case $n in
    ???) 
        echo "One";;
    2) 
        echo "Two";;
    aa) 
        echo "Three";;
    *.txt) 
        echo "Four";;
    *) 
        echo "Other";;
esac

This Bash script prompts the user to input a value, stores it in the variable n, and then uses a "case" statement to check the value of n. Depending on what n contains, it prints out different messages. If n is "???" it prints "One," if it's "2" it prints "Two," if it's "aa" it prints "Three," if it ends with ".txt" (e.g., "myfile.txt") it prints "Four," and for any other input, it prints "Other." This script demonstrates how to make decisions and take different actions based on the value of a variable using the "case" statement in Bash.

15. Functions in Bash: A fucntion is code which can be referenced by its name and is used to break code into mini, reuseable scripts. 
#!/bin/bash

check_even () {
    local mod=2
    echo "The value of mod is $mod"
    if [ $(("$1" % $mod)) -eq 0 ]
    then 
       echo "The number $1 is even!";
    else 
       echo "The number $1 is odd!"
    fi
}


number=2344

check_even $number
echo $mod

This Bash function named check_even is designed to determine whether a given number is even or odd. It takes one argument, 1, which represents the number to be checked. Inside the function, it calculates the remainder when the input number is divided by 2 and checks if this remainder is equal to 0. If the remainder is 0, it prints "The number is even," otherwise, it prints "The number is odd." However, there is an issue with trying to print the value of the mod variable outside the function, which will result in an error since mod is defined as a local variable within the function and cannot be accessed outside of it.

Loops in Bash: Loops are programming constructs that allow you to repeatedly execute a set of commands or statements as long as a specified condition is met or for a defined number of iterations (i.e. WHILE loop, UNTL loop, FOR loop). 
