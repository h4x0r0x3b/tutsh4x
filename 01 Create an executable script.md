<h2 align="center">Create an executable script</h2>
<p align="center"><img width="350" height="350" src="https://a.top4top.io/p_2505pecmc1.png"></p>

- - - - - - - - - - - - - - - - - - - - - -
Script files should be named in a **file_name.extension** format such as **script.sh** 

To create, modify, change file details such as the date, etc. Use **touch** command :
```bash
$ touch script.sh
```
> Alternative :

Use **cat** command to create a file with a **redirect** (denoted with the **>** symbol) :
```bash
$ cat > script.sh
#!/bin/bash
echo 'Hello World'
```
press **CTRL + D** while under **cat** command to exit and return to the prompt.

To see what’s in the script.sh file :
```bash
$ cat script.sh
```
- - - - - - - - - - - - - - - - - - - - - -
**ls** stands for Lists, to see the contents of a directory (the files and subdirectories)

| **Switch options** | **Explanation** |
| :---: | :---: |
| **-l** | for long list format (also contains the permission) |
| **-a** | --all, to show all contents (includes hidden files) |
| **-h** | --human-readable, print sizes (with -l switch) |

Use **-switch** with **ls** command :
```bash
# Multiple switch
$ ls -a -h -l
# Single-lined multiple switch
$ ls -lah
total 8K
drwx------ 14 0x3b 0x3b 4.0K Aug 16 13:22 .
drwxrwx--x  4 0x3b 0x3b 4.0K Jul 17 09:42 ..
-rw-------  1 0x3b 0x3b   31 Aug 16 11:16 script.sh
```
| **File** | **Meaning** |
| :---: | :---: |
| **Single dot (.)** | the current directory |
| **Double dot (..)** | the parent directory |

Following are the possible file type options in the **1st character** of the **ls -l** output.

| **File** | **Type** |
| :---: | :---: |
| **-** | normal |
| **d** | directory |
| **s** | socket |
| **l** | link |

Every file and directory are allocated with a level of permission

| **Level** | **Permission** |
| :---: | :---: |
| **r** | **r**ead |
| **w** | **w**rite |
| **x** | e**x**ecute |

Grant executable permission with **chmod** command :
```bash
$ chmod +x script.sh
```
The **mark \*** is known as a glob and used to match any character(s) in the filename :
```bash
# Will grant permission to 'script' named files
$ chmod +x script.*
# Will grant permission to files with .sh extension
$ chmod +x *.sh
# Will grant permission to all files within the current directory
$ chmod +x *
```

Check the permission again with **ls** :
```bash
$ ls -la
-rwx------  1 0x3b 0x3b   31 Aug 16 11:16 script.sh
```

Use a shortcut to refer to permissions by using a single number to represent **one rwx set** of permissions.

| **Binary** | **Octal** | **rwx** |
| :---: | :---: | :---: |
| 000 | 0 | --- |
| 001 | 1 | --x |
| 010 | 2 | -w- |
| 011 | 3 | -wx |
| 100 | 4 | r-- |
| 101 | 5 | r-x |
| 110 | 6 | rw- |
| 111 | 7 | rwx |

Grant **Octal** permission shortcut :
```bash
# Will grant rwx permissions to UGO (User, Group, Others)
$ chmod +777 script.sh
# Check the permission again with ls
$ ls -la
-rwxrwxrwx  1 0x3b 0x3b   31 Aug 16 11:16 script.sh
```
- - - - - - - - - - - - - - - - - - - - - -
Use **nano** command to modify the script :
```bash
$ nano script.sh
```
While under **nano** command :<br>
press **CTRL + O** to **Overwrite** the script.<br>
press **CTRL + X** to **Exit** and return to the prompt.<br>
- - - - - - - - - - - - - - - - - - - - - -
Scripts all begin with the same line called the **shebang #!**

**SHELL (SH) :**
> Script :
```bash
#!/bin/sh
```
> Command Line :
```bash
$ sh script.sh
```
**Bourne Again SHell (BASH) :**
> Script :
```bash
#!/bin/bash
```
> Command Line :
```bash
$ bash script.sh
```
> Alternative :
```bash
$ ./script.sh
```
Use **-switch** with **BASH** :
> Script :
```bash
#!/bin/bash -x -v -e
```
> Command Line :
```bash
# Multiple switch
$ bash -x -v -e script.sh
# Single-lined multiple switch
$ bash -xev script.sh
```

| **Switch options** | **Explanation** |
| :---: | :---: |
| **-x** | displays commands and their results. Useful for debugging. |
| **-v** | Verbose, displays everything even comments and spaces. |
| **-e** | Error Exit, causing the script to immediately exit on the first error. |
| **-f** | checks if the file exists and is a regular file. |

**PYTHON (PY) :**
> Script :
```python
#!/usr/bin/python
```
> Alternative :
```python
#!/usr/bin/env python
```
> Command Line :
```bash
$ python script.py
```
- - - - - - - - - - - - - - - - - - - - - -
Pass an **Argument** to a script from Command Line

Use "0x3b" as command line argument

**BASH :**
> Script :
```bash
#!/bin/bash
echo "Hello $1"
```
> Command Line :
```bash
$ ./script.sh 0x3b
OUTPUT: Hello 0x3b
```
**PYTHON :**
> Script :
```python
#!/usr/bin/python
print("Hello", __import__('sys').argv[1])
```
> Alternative :
```python
#!/usr/bin/python
import sys
print("Hello %s" % sys.argv[1])
```
> Command Line :
```python
# Can run script without #!shebang
$ python script.py 0x3b
OUTPUT: Hello 0x3b
```
> Alternative :
```python
$ ./script.py 0x3b
OUTPUT: Hello 0x3b
```