# Welcome to Linux Excercises
# Table of Contents 
 1. [Bandit Level 0](#bandit-level-0) 
 2. [Bandit Level 1](#bandit-level-1)
 3. [Bandit  Level 2](#bandit-level-2)

## Bandit Level 0 
(https://overthewire.org/wargames/bandit/bandit0.html)
The goal of this level on OverTheWire's Bandit game is for you to log into the game using SSH. 

- The host to which you need to connect is `bandit.labs.overthewire.org`.
- The port is `2220`.
- The username is `bandit0`.
- The password is `bandit0`.

Once logged in, you can proceed to the Level 1 page to find out how to beat Level 1. [^5^]

If you're using a Unix-based system like Linux or MacOS, you can open a terminal and enter the following command to connect:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

After running this command, you'll be prompted for the password. Enter `bandit0`, and you should be logged in.

Please note that if you're using Windows, you might need an SSH client like PuTTY to do this.

## Bandit Level 1 
The goal of the Bandit Level 1 on OverTheWire is to find the password for the next level. The password is stored in a file called `readme` located in the home directory. Once you find the password, you should use it to log into `bandit1` using SSH[^13^].

To find the password, after you have logged into the game with the credentials for `bandit0`, you can use the `cat` command to read the `readme` file:

```bash
cat ~/readme
```

This command will output the contents of the `readme` file, which should be the password for `bandit1`. You can then use this password to log into `bandit1` and proceed with the game.

Here's the command to log into `bandit1` (replace `password` with the actual password you found):

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

After running this command, you'll be prompted for the password. Enter the password you found, and you should be logged in. [^13^]: [source](https://overthewire.org/wargames/bandit/bandit1.html)

---
## Bandit Level 2

The goal of the Bandit Level 2 on OverTheWire is to find the password for the next level. The password is stored in a file named `-` located in the home directory[^21^].

As the file has a special name (`-`), you'll need to provide a path to the `cat` command to avoid interpretation of the `-` as a special character. You can use `./-` to refer to the file in the current directory:

```bash
cat ./-
```

This command will output the contents of the file `-`, which should be the password for `bandit2`. You can then use this password to log into `bandit2` and proceed with the game.

Here's the command to log into `bandit2` (replace `password` with the actual password you found):

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

After running this command, you'll be prompted for the password. Enter the password you found, and you should be logged in.   [^21^]: [source](https://overthewire.org/wargames/bandit/bandit2.html)

----
## Bandit Level 3
The goal of the Bandit Level 3 on OverTheWire is to find the password for the next level. The password is stored in a file named `spaces in this filename` located in the home directory[^27^].

As the file has spaces in its name, you'll need to handle it properly when providing the filename to the `cat` command. In Unix-based systems, you can use backslashes (`\`) to escape the spaces:

```bash
cat spaces\ in\ this\ filename
```

Or you can use quotes around the filename:

```bash
cat "spaces in this filename"
```

Either of these commands will output the contents of the file `spaces in this filename`, which should be the password for `bandit3`. You can then use this password to log into `bandit3` and proceed with the game.

Here's the command to log into `bandit3` (replace `password` with the actual password you found):

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

After running this command, you'll be prompted for the password. Enter the password you found, and you should be logged in. [^27^]: [source](https://overthewire.org/wargames/bandit/bandit3.html)


---

## # Bandit Level 3 → Level 4

The goal of the Bandit Level 4 on OverTheWire is to find the password for the next level. The password is stored in a hidden file in the `inhere` directory[^33^].

In Unix-based systems, hidden files start with a dot (`.`), and the `ls` command does not display them by default. However, you can use the `-a` option with `ls` to display all files, including hidden ones:

```bash
ls -a inhere
```

This command will list all files in the `inhere` directory, including the hidden one. Once you have the name of the hidden file, you can use the `cat` command to display its contents:

```bash
cat inhere/.hiddenfile
```

Replace `.hiddenfile` with the actual name of the hidden file. This command will output the contents of the hidden file, which should be the password for `bandit4`. You can then use this password to log into `bandit4` and proceed with the game.

Here's the command to log into `bandit4` (replace `password` with the actual password you found):

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

After running this command, you'll be prompted for the password. Enter the password you found, and you should be logged in.  [^33^]: [source](https://overthewire.org/wargames/bandit/bandit4.html)

---
## # Bandit Level 4 → Level 5
The goal of the Bandit Level 5 on OverTheWire is to find the password for the next level. The password is stored in the only human-readable file in the `inhere` directory[^39^].

To find this file, you can use the `file` command, which determines the file type. In Unix-based systems, the `file` command can be used to identify human-readable (i.e., text) files. You can use a wildcard (`*`) to apply the `file` command to all files in the directory:

```bash
file inhere/*
```

This command will display the file type of all files in the `inhere` directory. Look for the file that is identified as a text file.

Once you have identified the human-readable file, you can use the `cat` command to display its contents:

```bash
cat inhere/humanreadablefile
```

Replace `humanreadablefile` with the actual name of the human-readable file. This command will output the contents of the file, which should be the password for `bandit5`. You can then use this password to log into `bandit5` and proceed with the game.

Here's the command to log into `bandit5` (replace `password` with the actual password you found):

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

After running this command, you'll be prompted for the password. Enter the password you found, and you should be logged in.   [source](https://overthewire.org/wargames/bandit/bandit5.html)

---
## # Bandit Level 5 → Level 6

The goal of the Bandit Level 6 on OverTheWire is to find the password for the next level. The password is stored in a file somewhere under the `inhere` directory and has all of the following properties:

- It is human-readable
- It is 1033 bytes in size
- It is not executable[^47^]

To find this file, you can use the `find` command, which is used for searching files and directories in Unix-based systems. You can specify the `inhere` directory as the starting point for the search, and use the `-type f` option to search for files. You can then use the `-readable`, `-size`, and `! -executable` options to match the properties specified in the level goal:

```bash
find inhere -type f -readable -size 1033c ! -executable
```

This command will list the path to the file that matches the specified properties. The `-size 1033c` option is used to search for files of exactly 1033 bytes in size (the `c` suffix stands for bytes).

Once you have the path to the file, you can use the `cat` command to display its contents:

```bash
cat /path/to/file
```

Replace `/path/to/file` with the actual path to the file. This command will output the contents of the file, which should be the password for `bandit6`. You can then use this password to log into `bandit6` and proceed with the game.

Here's the command to log into `bandit6` (replace `password` with the actual password you found):

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

After running this command, you'll be prompted for the password. Enter the password you found, and you should be logged in. [^47^]: [source](https://overthewire.org/wargames/bandit/bandit6.html)

