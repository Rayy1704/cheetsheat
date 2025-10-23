 alpha.txt


 Lab 1: Introduction to Linux Environment, CLI, File & Directory Management
(Source: OS Lab 1.pptx)


Lab# 1 Introduction to Linux Environment, CLI, File & Directory Management 43]
CS311 L 44]
Instructor : Mis Sidra Ayesha 45]

Learning Outcomes 46]
Log in and log out of the Linux operating system47].
Understand the Linux file system and directory hierarchy48].
Navigate and manipulate files and directories49].
Know the root directory, home directory, and paths50].

Operating System 51]
Operating System is a type of System Software and a collection (set) of programs that performs two specific functions].
First, it provides a user interface so that users can interact with the machine].
Second, the operating system manages computer resources]. It accepts user commands, then determines where programs are loaded into memory, and coordinates communication between various hardware devices].
Windows, Linux, and DOS are popular operating systems55].

Linux System Components: ]
Linux systems can be split into two parts57].
Shell: A Shell is an interface between a user and a Linux operating system59]. The Shell accepts and interprets a user's commands60].
Kernel: The Linux kernel is the core component that handles critical functions like system calls, process management, scheduling, signals, paging, swapping, file systems, and storage I/O62].
Diagram Flow: UUUSER 63] Sh 64] User 65] Shell 66] Kernel 67] Shell68].

Files 69]
Mechanism - store information70]. Two modes of storing information: File 72] and Directories73].
 File attributes:
    Read - "r": allows reading; nothing can be changed77].
    Write - "w": allows being written to and changed78].
    Execute - "x": allows execution by users or the operating system79].
The significant operations which can be performed on files are: Create 82], Delete 83], Open 84], Close 85], Read 86], Write 87], Rename 88], Get Attributes 89], Set Attributes90].

Directories 91]
A directory (folder) is a virtual location within a file system where files are stored92].
Users can navigate through the file system efficiently to locate and manage files93].
The significant operations which can be performed on the directories are: Create 96], Delete 97], Open 98], Close 99], Read 100], Write 101], Rename 102], Get Attributes 103], Set Attributes104].

Linux File System Hierarchy 105]
/home: Users’ home directory106].
/etc: All system administrator commands, configuration, and installation control files107].
/bin: The core set of system commands and programs (most systems cannot boot without executing some of the commands here)108].
/dev: The device files used to access system peripherals (e.g., your terminal can be accessed from `/dev/tty`)109].
/lib: The standard set of programming libraries required by Linux programs110].
/root: The root user’s home directory111].
/usr/bin: Common commands and programs112].
/usr/doc: Documentation113].
/usr/games: Games114].
/usr/include: Header files115].
/usr/man: Manual pages (help)116].

File and Directory Commands
Move from home to root: `cd /`16].
Move from root to home: `cd` or `cd ~`16].
`.` (single dot): Denotes the current directory17].
`..` (two dots): Denotes the parent directory (one level above)18].
`sudo su`: Stands for "Switch User" and is used to switch to another user, in this case, the root user19].
    $: non-privileged user19].
    #: privileged user19].
 Shell Commands (Case Sensitive):
    `pwd`: present working directory19].
    `mkdir name`: make a directory19].
    `rmdir name`: remove directory19].
    `cd`: change directory19].
    `rm`: remove a file19].
    `clear`: clear all19].
    `exit`: come out of the shell19].
    `ls`: list the files19].
        `-a`: Display all the files and subdirectories, including hidden files19].
        `-l`: Display detailed information about each file and directory20].
        `-r`: Display files in the reverse order20].

Pathname 21]
Absolute Path: Always starts from the root directory (/)21, 22]. It identifies a file or a directory irrespective of the user's current state21].
    Example: To locate `my_scripts.sh` in the `script` directory, the absolute path is: `/home/abhishek/scripts/my_scripts.sh`23].
Relative Path: Identifies a file or a directory that depends on the user's state (current directory)23]. It starts from the current directory23].
    Example: If you are in the `/home` directory, you can access the file using `abhishek/scripts/my_scripts.sh`24, 25].

Commands and Directories (Practice)
 How would you go to the directory you created? `cd dir_name`25, 26].
 How would you go up? `cd ..` (space between `cd` and `..`)26].
 How would you go to your home directory? `pwd`, `cd ~`, `cd ..`, `pwd`27].
 How do we remove our created directories? `ls r...`28].

---


 Lab 2: File and Directory Management
(Source: OS Lab 2.pptx)


Lab# 02 File and Directory Management 242]
CS311L 243]
Ms. Sidra Ayesha 244]

Learning Objectives 245]
To set different permissions to a file and a directory (Read, Write and Execute)246].
Set different permissions for different users (Owner, group, and others)247].
List all the users on the system and display the user ID248].
Use the manual page (`man`)249].
Use wild cards250].

Linux Commands
`date`: Displays the current date and time on the screen2, 2].
    `date +”%d”`: Display just today’s date only2, 255].
    `date +”%r”`: Display just time only2, 257].
    `date +”%Y”`: Display just year only258, 259].
    `date +”%H”`/`date +”%I”`: Display just hours only260, 261, 262, 263].
    `date +”%m”`: Display just month only264, 265].
`clear`: Clear the screen267, 268].
`echo`: Echoes back whatever you type on the command line after echo269, 270].
    `echo -n anything`: `n` doesn't begin a new line after echoing the information271, 272].
`sort file_name`: Sorts the content of a file274].
    Example Content for `vilson` file: Hello am ayesha, Sorted file, File needs to be Sorted, 10 years old, End of file, 5th semester lab276, 277, 278, 279, 280, 281].
    `sort -f file_name`: Ignores the distinction between lowercase and upper case letters284, 285, 286].
    `sort -fr file_name` / `sort -f -r file_name`: Reverse the order287, 288].
`wc` (word count) `file_name`: Displays the number of lines, number of words, and number of characters in a file291, 292].
    Options: `-c` (Display only the number of characters) 294], `-l` (Display only the number of lines) 295], `-w` (Display only the number of words)296].
`who`: Lists the login names, terminal lines, and login times of the users who are currently logged on to the system298, 299].
`whoami`: Displays who the system thinks you are300, 301].
`head file_name`: Prints the first ten lines of the file by default303, 304].
    `head –n 4 file_name`: Prints the first 4 lines instead of the first 10305, 306].
`tail file_name`: Writes the last ten lines of the input file by default309, 310].
    `tail –n4 file_name`: This will print the last 4 lines311, 312].

File and Directory Security 216]
Each file divides users into three categories: The file's owner (who creates the file), a group of users, and other users217].
The superuser (system administrator) has access to every file/directory217].

Access Permission Types 217]
| Permission | File Access Meaning | Directory Access Meaning |
| :--- | :--- | :--- |
| Read (r) | Can be examined, printed, or viewed by an editor217]. | Allows use of the `ls` command to list filenames218]. |
| Write (w) | Contents can be changed, overwritten, or deleted; access permissions can be changed217, 218]. | Allows adding or removing files from that Directory219]. |
| Execute (x) | Can be run by the user or OS217]. | Allows use of the `cd` command to change to that Directory219].

Access Specification
`ls -l` output shows nine places, divided into three sets of three: Owner access (first set), Group access (next set), and Others' access (final set)220].
Maximum access is represented by `rwx` (read, write, execute)220]. A dash (`-`) means access permission is not given220].
Check access privileges with: `ls -l file_name`220].

Change Permissions (`chmod`)
Syntax: `chmod user-type[operations][permissions] filelist`221].
User Types: `u` (User/owner) 221], `g` (Group) 221], `o` (Other) 221], `a` (All three user types)221].
Operations: `+` (Add the permission) 221], `-` (Remove the permission) 221], `=` (Set permission; all other permissions reset)222].
Permissions: `r` (Read permission) 222], `w` (Write permission) 222], `x` (Execute/run permission)222].
Examples: `chmod u-w file_name` (Remove writing permission for owner)222]. `chmod go+r file_name` (Group and other users get read access)223]. `chmod g=r + x file_name` (Set group access for reading and executing but not writing)224].

Wildcards
Special characters applied with a command (like `ls`) to operate on a group of files/directories225].
``: Matches zero or any number of characters226].
    Examples: `ls t` (last char 't'), `ls t` (first char 't'), `ls tt` (first and last char 't'), `ls oo` (last two chars 'oo')227].
`?`: Matches any single character in a file/directory226].
    Examples: `ls t?` (first char 't' with only one following char), `ls t?t`, `ls ?t`228, 229].
`[]`: Matches any one character in the bracket226].
    Examples: `ls p[12]` (ends with '1' or '2'), `ls p[1-9]`, `???[a-c]` (3 chars, last is 'a', 'b', or 'c'), `[a-c][1-9]`229, 230, 231, 232].

I/O Redirection and Piping
I/O Redirection: Changes the assignments for standard input (usually keyboard) and standard output (usually screen) to other sources like a file or another command235].
Pipe Operator (`|`): Sends the output of one Linux command as the input to a second Linux command236, 237].
    Examples: `ls | grep “eisha"`, `cat file.txt|sort -rn | head -3`237, 238].

Global Regular Expression Parser (`grep`)
The `grep` command searches for strings/patterns in a text file233].
Syntax: `grep [options] pattern [files]`233].
    Options: `-c` (Print number of matches only), `-i` (Ignore case), `-n` (Precede with line number), `-v` (Print lines NOT containing the pattern), `-w` (Select only those lines containing matches that form whole words)233].
Difference b/w Wildcards and Regular Expressions: Wildcards are for matching file names 235], while regular expressions are used for matching patterns within text\_files235].

Terminating a Process
The `kill` command sends a signal (an integer number) to the specified process, which is identified by the process ID number (PID)238, 239].

Tasks (Practice Questions)
Ready Files: `OS -> (ayesha, lab2, lab11, hello, Lab2 is in progress, I am a teacher, 2025)`, `file1 -> (Hello ayesha)`, `file2 -> (The only way to do great work is hardwork)`, `file3 -> (happy)`239].
Task: Store data of `file1`, `file2`, `file3` in `Newfile` (without overwritten)239]. Echo "Hello World" in `newfile1`240]. Count your name in `Newfile` and use it as input for `redirection_Example`240]. Find your name in `file1`, `file3`, and `file4` and put valid output in `output.txt` and error messages in `error.txt`240].
 Tasks (Files/Permissions/Wildcards): For file `task1`: Set `rwx` for group; Remove `rw` for owner240]. For file `task2`: Allow `w` for owner, `x` for group, and `r` for others241]. Find files whose first five chars can be any but the last should be a number between (5-9)241]. Find files whose first and last characters should be between (p – s) and anything between them241]. Try to copy files with extension `.c` from `Dir001` to `Dir101` (from `Dr01`)241]. Try to remove `.txt` files from `Dir001` (from `Dr00`)241].

---


 Lab 4: C Programming Introduction
(Source: CS311 updated lab 4.pptx)


Lab # 4 C Programming Introduction 8]
CS311 LAB 9]
Lab Instructor: Mis Sidra Ayesha 550]

Learning Objectives 551]
Introduction to C programming5].
Compile the C program in `gcc` compiler & difference between C and C++5].
The compilation process5].
To handle command line arguments & error handling in C555].
To know the process Environments5].
Structures in C557].

Difference between C and C++ 558]
| Feature 559] | C 0] | C++ 1] |
| :--- | :--- | :--- |
| Paradigm 2] | Procedural 3] | Multi-paradigm (Procedural, Object-Oriented) 4] |
| Objects and Classes 5] | Not supported 6] | Fundamental concepts with classes and objects 7] |
| Encapsulation 8] | Limited support through structures 9] | Strong support through classes, allowing data hiding and encapsulation 570] |
| Memory Management 571] | Manual memory management with `malloc` and `free` 572] | Supports manual memory management, through constructors and destructors573]. |

C Compiler Installation (Ubuntu Linux) 575]
Ubuntu Linux typically comes with the GNU Compiler Collection (GCC) installed576].
 If not installed, use:
    `sudo apt-get update` 578]
    `sudo apt-get install build-essential` 579]

Introduction to C 580]
C programs use the extension `.c`582].
Compile Format: `gcc first.c -o first` (creates executable `first`)584].
Execution Format: `./first`586].

C Programming Example 587]
```c
#include <stdio.h> 
int main() 
{ 
    printf(“One OS to Rule Them All !! \n”); 
    return 0; 
}
``` 588, 589, 590, 591, 592, 593]

How Does the Program Work? 594]
Must contain the `main()` function, where code execution begins595, 596].
The `printf()` is used to send formatted output to the screen597].
To use `printf()`, include the `stdio.h` header file using `#include <stdio.h>`598].
The `return 0` is the "Exit status"599].

Step by Step Compilation using `gcc` 600]
1.  Pre-processing: To expand macros601]. (Command: `cpp first.c > first.i` / `gcc –E first.c –o first.i`) 606, 607].
2.  Compilation: From source code to assembly language602]. (Command: `gcc -S first.i`) 608, 609].
3.  Assembly: From assembly language to machine code603]. (Command: `as first.s -o first.o` / `gcc -c first.s`) 610, 611].
4.  Linking: To create the final executable file604]. (Command: `gcc first.o –o first`) 612, 613].

Input and Output 614]
Input: `scanf()`616].
Output: `printf()`618].
Format Specifiers: Used with `printf()` and `scanf()` to specify how data should be formatted or interpreted620, 621, 622, 623].
    Examples: `%d` (int), `%c` (char), `%f` (float), `%lf` (double), `%hd` (short int), `%u` (unsigned int), `%li` (long int), `%lli` (long long int), `%lu` (unsigned long int), `%llu` (unsigned long long int), `%Lf` (long double)619].
Memory Management: `malloc()` and `free()` functions are used for manual Memory Allocation and Memory reallocation2].

Command Line Arguments 3]
Arguments specified after the program name that are passed to the program during execution3].
Function Signature: `int main( int argc, char argv[])`3].
    `int argc`: Counts the number of arguments passed (including the program's name itself)3].
    `char argv[]`: An array of character pointers (strings), where each element represents an argument4].
Example: `./aisha testfile.txt`5]. `argv[0]` is `./aisha`, and `argv[1]` is `testfile.txt`6].

Process Environment 6]
Programs are invoked in a context, and the environment list is passed to it6].
It contains information like user's home directory, terminal type, and current locale7].
Format: `name=value` (Name is upper case, e.g., `HOME=/home/aisha`)8].
Accessed through the global variable `environ`8].

Error Handling 8]
Global Variable `errno`: An integer variable (in `errno.h`) automatically set to the latest/last error condition encountered during a function call8, 9].
`perror()`: Displays a user-provided string, followed by ':', and the error message associated with `errno`9].
`strerror()`: Returns a pointer to the textual representation of the current `errno` value9].

Structure in C (`typedef`)
The `typedef` keyword creates an alias name (nickname) for data types0, 1].
Commonly used with structures to simplify variable declaration, making the code shorter, easier, and more readable1].

Tasks (Practice Questions)
Task 1: Write C code that asks for user's name, GPA, age, then prints "Hiii, Name(Ayesha), your age"2].
Task 2: Write C code that asks for two numbers and performs all basic operations (+, -, )3].
Task 3: Create a C program that prompts for GPA (displaying with two decimal places) and number of courses4]. Then, prompt for name, allocate dynamic memory to store the name, and display it4].
Task 4: Write C code that declares a structure to store id, pages, and price of a book5]. Input records of five books and display the most costly book6]. Clear the memory after your work7].

---


 Lab 5: Input-Output System Calls in C
(Source: OS Lab 5 updated1.pptx)


Lab# 5 Input-Output System Calls in C 738]
CS311 Lab 739]
Lab Instructor: Mis Sidra Ayesha 740]

Learning Objectives 741]
To open and read a file in C using `gcc` compiler742].
To write in a file and close the file using `gcc` compiler743].

System Calls 744]
System calls are the mechanism through which a process requests services from the Operating System (OS)745].
 Services are related to:
    file operations (e.g., `open`, `close`, `read`, `write`, `stat`) for managing files and directories747].
    process management (e.g., `fork`, `exec`, `exit`) for managing processes748].

1. `open()` System Call 749]
Used to provide access to a file/resource and allocates resources750, 751].
Header: `#include <fcntl.h>`7].
Syntax: `int open(const char pathname, int flags);`7].
 File Access Modes (Flags):
    `O_RDONLY`: Open for read-only755].
    `O_WRONLY`: Open for write-only7].
    `O_RDWR`: Open for reading and writing757].
 Optional Modes (Combined with bitwise OR):
    `O_APPEND`: Place written data at the end of the file761].
    `O_TRUNC`: Set the length of the file to zero, discarding existing contents762].
    `O_CREAT`: Creates the file, if necessary, with permissions given in mode763].
    `O_EXCL`: Used with `O_CREAT` to ensure atomic creation; the call will fail if the file already exists764, 765, 766].
Example Call: `int fd = open("example.txt", O_WRONLY | O_CREAT | O_TRUNC, 0644);`758].
Example Usage: To create a file named `new_file` for write only: `open (“new_file”, O_WRONLY|O_CREAT);`768, 769].

2. `close()` System Call 770]
Used to terminate access to a file772].
Syntax: `close(int fd);`771].
Function: Files no longer required, buffers are flushed, and the file descriptor becomes available for reuse773, 774, 775].
Return: Returns `0` if successful and `-1` on error776].

3. `write()` System Call 714]
Used to write data from a buffer to a file or file descriptor715].
Header: `#include <unistd.h>`714].
Syntax: `write(int fd, const void buf, size_t count);`714].
Arguments: File descriptor (`fd`), buffer with data (`buf`), and number of bytes to write (`count`)716].

C Program to illustrate `open` system call 777]
```c
#include<stdio.h> 779]
#include<fcntl.h> 780]
#include<errno.h> 781]
int main() 782]
{ 783]
    // if file does not have in directory 784]
    // then file first.txt is created. 785]
    int fd = open("foo.txt", O_RDONLY | O_CREAT); 786]
    printf("fd = %d\n", fd); 787]
    if (fd ==-1) 788]
    { 789]
        // print which type of error have in a code 790]
        printf("Error Number % d\n", errno); 791]
        // print program detail "Success or failure" 792]
        perror("Program"); 793]
    } 794]
    close(fd); 795]
    return 0; 796, 797]
}
``` 710, 711]

Tasks (Practice Questions)
Task 1: Write a C program to copy the content of one file (given by user) into another file (given by user) using system calls only797].
Task 2: Write a C program which reads from a user entered file and writes exactly the same data at the terminal, both by system call and `fprintf` and `fscanf` functions798].
Task 3: Write a C program that reads a file entered by the user and counts the number of lines, words, and characters, displaying the result using both system calls and `fprintf`799].
Task 4: The “Ten Thousand Rows Challenge” - write a program in C that reads a file with 10k lines of station;temp data and outputs the min, max, and median value of temperature for each station (Use `strtok()` function)800].

---


 Lab 6: Process Management System Calls
(Source: OS lab (6) updated.pptx - Content labeled Lab# 07, 8)


Lab# 07, 8 Process Management System Calls 928]
CS311 Lab 929]
LAB INS. MIS SIDRA AYESHA 930]

Outcomes 931]
To create a child process932].
To print the process ID and parent process ID933].
To understand the use of `wait()` system call934].

Process management system calls 935]
Provide a way to create, manage, and control the processes936].
Plays a crucial role in multitasking937].
Common calls: `fork()`, `wait()`, `exec()`, `exit()` etc939].

1. `fork()` System Call 940]
The first and most basic system call used for process creation in UNIX/Linux941].
Creates a child process that is an exact copy of the parent process942].
After a successful `fork()`, both the parent and the child start executing from the same point in code just after the `fork()` call943, 944, 945, 946].
 Return Values:
    Negative value: Indicates an error949].
    Zero: Returned for the child process950].
    Positive value: Returned for the parent process; this value is the Process ID (PID) of the newly created child process951].
 Example 1:
    ```c
    int main()
    {
        fork();
        printf("Called fork() system call\n");
        return 0;
    }
    ```9, 957, 958, 959, 960].
    Output: `Called fork() system call` (printed twice)961, 962, 963].

2. `wait()` System Call 905]
Headers: `#include <sys/types.h>`, `#include <sys/wait.h>`905].
Makes the parent process pause its execution until one of its child processes finishes905].
Helps synchronize parent and child processes905].
Return: Returns the Process ID (PID) of the terminated child process907]. Returns `-1` if the process has no child process907].

3. `waitpid()` System Call 908]
Used to wait for a specific child process, unlike `wait()` which waits for any arbitrary child908].
Syntax: `pid_t waitpid (child_pid, &status, options);`909].
 Options:
    `0`: Parent waits for the child to terminate909].
    `WNOHANG`: Parent does not wait (non-blocking); checks status and returns immediately if the child hasn't exited909].
    If `child_pid` is `-1`, it waits for any arbitrary child (works like `wait()`)910].
Return Value: PID of the child if a child has exited, or `0` if using `WNOHANG` and the child hasn’t exited910].

4. `exec()` family 910]
Functions (e.g., `execvp`, `execl`) are used to run a new program in place of the current process910].
The current process is completely replaced by the new program911].
Functions differ in how arguments are passed and whether the full path is provided912].
`execvp`: System searches the PATH for the executable913]. Arguments are passed using an array (`argv[]`)913].
`execl`: You know the full path to the executable (e.g., `/bin/ls`)915]. Arguments are passed one by one (followed by `NULL`)915].
 Difference Summary:
    `Execv`: Full path, array916].
    `Execvp`: Search PATH, array916].
    `Execl`: Full path, one by one916].
    `Execlp`: Search PATH, one by one916].

Tasks (Practice Questions)
Task 1: Write a C program where the main process creates a child process917]. The child calculates the factorial of a user-entered number and prints the result917]. The parent waits for the child and displays "Factorial calculation completed"917].
Task 2: Create a C program that uses the `execvp()` function to execute the `date` command and print the current date and time918].
 Task 3: Write a C program that repeatedly asks the user for a number N (1–9); 0 terminates the program919]. For any other value, create N child processes, where each child generates and prints a random number between 1 and 100919]. The parent must wait for all child processes before prompting the user again919].