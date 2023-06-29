Basic command line
================
Kirstyn Brunker

- <a href="#1-1-basic-command-line" id="toc-1-1-basic-command-line">1 1:
  Basic Command Line</a>
  - <a href="#11-11-tab-autocomplete" id="toc-11-11-tab-autocomplete">1.1
    1.1: Tab Autocomplete</a>
  - <a href="#12-12-exiting-a-program" id="toc-12-12-exiting-a-program">1.2
    1.2: Exiting a program</a>
  - <a href="#13-13-typing-on-the-command-line"
    id="toc-13-13-typing-on-the-command-line">1.3 1.3 Typing on the command
    line</a>
  - <a href="#14-14-reuse-old-commands"
    id="toc-14-14-reuse-old-commands">1.4 1.4 Reuse old commands</a>
- <a href="#2-2-navigation-in-linux" id="toc-2-2-navigation-in-linux">2 2:
  Navigation in Linux</a>
  - <a href="#21-21-pwd-print-working-directory"
    id="toc-21-21-pwd-print-working-directory">2.1 2.1: <code>pwd</code>
    (Print Working Directory)</a>
  - <a href="#22-22-ls-list" id="toc-22-22-ls-list">2.2 2.2: <code>ls</code>
    (List)</a>
  - <a href="#23-23-mkdir-make-directory"
    id="toc-23-23-mkdir-make-directory">2.3 2.3: <code>mkdir</code> (Make
    Directory)</a>
  - <a href="#24-24-cd-change-directory"
    id="toc-24-24-cd-change-directory">2.4 2.4: <code>cd</code> (Change
    Directory)</a>

*Credit*: Modified from [GECO Viral Bioinformatics training
material](https://github.com/josephhughes/viral-bioinformatics-training/blob/main/Bash_Scripting/Basic_Command_Line.md#1-basic-command-line)

# 1 1: Basic Command Line

There are a number of handy commands and shortcuts that are useful to
know before diving into the Linux command line. Let’s try some!

## 1.1 1.1: Tab Autocomplete

When using the command line, often typing is the slowest part. Linux is
aware of this and lets you use the tab button to autocomplete for
certain filenames or directories.

While typing in a folder/filename, if you type the first few letters and
hit the tab button, Linux will attempt to autocomplete the name for you.
Let’s try the text below, followed by hitting the tab button once:

``` shell
jovyan:~$ cd s
```

The shell has managed to autocomplete some of the name, but not all of
it. This likely means there is not enough information to uniquely
identify the file. This can be verified by hitting the tab button twice
which will produce the following output:

``` shell
jovyan:~$ cd shared-
shared-public/ shared-team/         
```

There are two folders that start with the name “shared-” so must
manually complete (at least until the text is sufficient to pinpoint the
file i.e. in this case `shared-t`, then tab, would be enough to find
“shared-team/”)

## 1.2 1.2: Exiting a program

Sometimes you might want to exit a program if for example it is running
for too long, or is stuck in an infinite loop. We can do this with
`ctrl+c`.

For example, run the command `top`, which shows a list of the processes
currently running on the machine.

``` shell
jovyan:~$ top         
```

There is no clear way out! But now try `ctrl+c` to exit.

## 1.3 1.3 Typing on the command line

When typing a command, you might want to jump to the front of the
command if you have made a typo or want to edit the command. We can do
this using `ctrl+a` to move to the front of a command and `ctrl+e` to
move to the end.

## 1.4 1.4 Reuse old commands

Often we want to reuse commands we have already run before. in Linux you
can do this using the up and down arrow keys on the keyboard to flick
through the most recently used commands. This saves a lot of time
typing, especially if you are writing and re-runnng scripts to check
they work correctly.

# 2 2: Navigation in Linux

The file system of linux is organised as a hierarchy of files and
directories(folders). The root directory is the top of the hierarchy
with all other files and direstories in the operating system located
below it. ![alt text](Images/filesystem.png) When you login to your
account on a linux machine, normally you will be placed into a directory
named after your username (for example, if my username is kirstyn, my
directory will be found at **‘/home/kirstyn’** ). This is located inside
another directory called home, which is contained within the root
directory (which is called /). On CLIMB the default username is
joyvan.  
In order to use Linux via the terminal, it is important to know how to
navigate around the operating system using commands.

## 2.1 2.1: `pwd` (Print Working Directory)

The first thing you might want to know when you enter the command line
is where exactly you are in the operating system. The `pwd` is used for
exactly that. The command stands for **“print working directory”** and
will print the users current location.

``` bash
jovyan:~$ pwd
/home/joyvan
```

As we are in the home directory of my user, the command returns
`/home/joyvan`.

------------------------------------------------------------------------

### 2.1.1 Task 1

Find your current directory using pwd.

------------------------------------------------------------------------

## 2.2 2.2: `ls` (List)

The next thing we might want to do is to have a look at what files and
directories are in our home directory. We can do this using the `ls`
command, which lists the contents of the current working directory (i.e
where the user currently is).

``` bash
jovyan:~$ ls
lost+found  shared-public  shared-team
```

The output of `ls` on my machine shows that I have 3 directories called
**lost+found**, **shared-public**,and **shared-team**. The output will
vary depending on the contents of your home directory. `ls` can also be
used with flags to change the output in various ways. Flags are
specified by adding a `-` followed by a character that indicates the
flag type. An example of an `ls` flag is the `-l` flag which prints each
item in the list on a separate line. We can also use the -h flag to make
the output (specifically any output relating to file sizes) more human
readable:

``` bash
jovyan:~$ ls -l -h
total 16K
drwxrws--- 2 root   users 16K Jun 20 20:31 lost+found
lrwxrwxrwx 1 jovyan users  14 Jun 27 15:58 shared-public -> /shared/public
lrwxrwxrwx 1 jovyan users  12 Jun 27 15:58 shared-team -> /shared/team
```

We can see that each file and directory is printed on its own line,
along with some extra information about its user permissions, last edit
dates and file sizes.

Most Linux commands have optional flags and follow a similar pattern of
use i.e: `command_name [-flags] [parameters]`. A full example of `ls`
may look like `ls -l -h shared-team`, where the output would be a listed
print of all files and directories in the shared-team directory in a
human readable form.

------------------------------------------------------------------------

### 2.2.1 Task 2

Use `ls` to list the folders in your current directory.

### 2.2.2 Task 3

Use `ls` to list each item in the directory in a new line.

### 2.2.3 Task 4

Repeat task 3, but make the file sizes “human readable”.

------------------------------------------------------------------------

## 2.3 2.3: `mkdir` (Make Directory)

The `mkdir` command is used to create a directory in Linux. Lets use it
to make an example directory to navigate into. We do this by using
`mkdir` followed by the name of the directory we wish to create:

``` bash
jovyan:~$ mkdir example_directory
```

------------------------------------------------------------------------

### 2.3.1 Task 5

Create 2 new directories using `mkdir`

### 2.3.2 Task 6

List the contents of one of these new directories.

------------------------------------------------------------------------

## 2.4 2.4: `cd` (Change Directory)

Now lets try and navigate around the operating system and explore a bit.
To do this we will need to use the `cd` command which allows us to move
up or down the file system. At its most basic, `cd` works as follows:

``` bash
jovyan:~$ cd directory_name
```

If the directory name is correct, then the command will move the user to
that directory. We can check this has worked using `pwd`.

``` bash
jovyan:~$ cd example_directory/
jovyan:~/example_directory$ pwd
/home/jovyan/example_directory
```

Depending on the distro of Linux you are using, you might notice that
the `~` before the `$` has changed to `~/example_directory`. This is
actually equivalent to the output of `pwd`, with the exception that `~`
is being used to represent `/home/kieran/`. In Linux systems, `~` is
used to represent the users home directory. This means that if we ever
want to quickly return to our home directory, we can do so with the
following:

``` bash
jovyan:~/example_directory$ cd ~
jovyan:~$ pwd
/home/joyvan/
```

So we can now enter a directory and return home using `~`, how do we
move up to a directory above our current directory? In Linux, we can use
`..` to indicate we want to move up a level in the hierarchy.

``` bash
jovyan:~$ cd ..
joyvan:/home$ pwd
/home
```

`pwd` shows that we are now in the home directory, which is indeed one
directory above the user directory. We can mavigate back down to our
home using either `cd ~` or `cd username` (`cd joyvan`).

While the examples here show moving up and down to folders that are
directly above or below our working directory, `cd` can be given all
sorts of filepaths.

``` bash
jovyan:~$ cd ../joyvan/example_directory/
joyvan:~/example_directory$ pwd
/home/joyvan/example_directory
```

This example is a bit unnecessary, but to summerise, we moved up one
directory using `..`, then back down to our current directory with
`/joyvan`, then down again with `/example_directory`. We could do the
same thing using either `cd /home/joyvan/example_directory` or
`cd ~/example_directory` or `cd example_directory` if we are in the home
directory already.

The path `/home/joyvan/example_directory` is actually an example of a
**absolute path**, meaning that the path begins at the root of the
filesystem and ends at the destination. Absolute paths are handy when we
know files are stored at a static location that is unlikely to change
(configuration files are a good example of this) but since they require
the whole path to be listed, they appear very long. As such, **relative
paths** are often used. These identify the location of a file relative
to either the current working directory (`cd example_directory` is an
example of using a relative path) or relative to some symbol like `~`
(again representing the users home directory) or `.` (representing the
directory the user is currently in, i.e equivelent to the working
directory).

------------------------------------------------------------------------

### 2.4.1 Task 6

Navigate to the root directory

### 2.4.2 Task 7

Navigate from the root directory back to the home directory

------------------------------------------------------------------------
