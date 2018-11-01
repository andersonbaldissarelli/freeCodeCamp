
## Linux Terminal

Most users prefer to interact with the system through the graphical interface, but this presents many limitations when it comes to changes that the user can make in the system. For the user to get out of this limitation and have full control there is a powerful tool called terminal, also known as command line or shell. The Linux terminal allows the user to make advanced changes to the system through root access, when a user becomes root means that he becomes superuser or system administrator.

For those of you who have never used the terminal, you may find it a bit intimidating at first, but once you're practicing, you'll realize that it's more efficient and even easier than using the GUI (yes, you'll find that).

The following is a list of basic and useful commands that are used not only by those who have arrived in the world of linux, but also by experienced users.

(Before you begin, you can open the terminal using the CTRL + ALT + T shortcut or you can search for the terminal in dash)

#### man
The man command should be at the top of any list of important Linux commands. The reason is very simple: simply run it to load a man page on the system commands, with definitions not only of the use of each tool, but also detailed descriptions of the numerous parameters of the software and examples of use.

To read the man pages is very easy and just run the following man from the name of the command you want to get help. Do not forget to press the Enter key after entering the command, otherwise it will not run.

```
man cp
```

When executing the above command, you can read all instructions for using the cp command.


#### ls
To list the files in any directory, simply use the ls command. If run without parameters, it will list the contents of the directory you are in, but you can indicate a path to it.

```
ls / usr / local / bin
```

You can also use ls to check the size and creation date of each file or folder. To do this, use the -l parameter and if you also want to list the hidden files, which start with a period, use:

```
ls -lha / usr / local / bin
```


#### cd
To skip from folder to folder, you do not need to open the file manager. In the terminal itself it is possible to navigate through the file system using the cd command followed by
path you want to follow.


```
cd / usr / local
```

It is worth noting that there are some shortcuts that can make life easier for the user. If you run the cd command without parameters, it returns to the user's folder, located in / home. To go back one level in the directory tree, use:

```
cd ..
```

That way, if you are in / usr / local and running "cd ..", you will return to the / usr directory.

#### cp
Copy a file through the terminal, use the following cp command from the source file and the destination to it, which can be either a new folder or a new file with a different name.

```
cp file1.txt and file2.txt
```

or else

```
cp file1.txt pastanova /
```

To copy an entire directory, do not forget to enter the -r parameter. If you want to clone a folder, use:

```
cp -r folder1 folder2
```

#### mv
To move files there is the mv command, and it can be used both to reshuffle files and to rename them. If you want to send the file from one folder to another, just use:

```
mv folder1 / file1 folder2 /
```

If you prefer to just rename it, use:

```
mv file1 file2
```

#### more
If you need to read the contents of a text file, use the more command followed by the path and filename.

```
more /home/user/file.txt
```

All contents of the file will be displayed in the terminal, filling the screen with text. To continue reading, press the spacebar and, if you need to return one or more pages, use the "b" key. If you want to exit before the end of the file, press "q".

#### df
To find out what the total space is and how many GB available there are in each system partition, we use:

```
df -h
```

The -h option, by the way, means human-readable, ie readable for humans. If you run the command without it, the information will be displayed in kilobytes and you will need to mentally convert it to other drives.

#### sudo
For security reasons, Linux works with user permissions. Therefore, certain commands or files are accessible only by the owner or by the root user. So you do not have to switch users at all times, there is the sudo command, which guarantees root user credentials temporarily, by means of password information.

To take the test, try to execute the command:

```
ls / root
```

You will be denied a permission notice. Then, run:

```
sudo ls / root
```

After entering your own user's password (in the case of Ubuntu), the command will run normally and the files in the root folder will be listed on the terminal.

#### grep
Imagine the following situation: You have a text file with about 200 names of students from a certain school, but you are not sure if a particular name is listed. Grep helps you search for that student and do a lot more with the help of regular expressions. If you are not sure if the student's name was written in full capital letters, add the -i parameter so that grep ignores this distinction during the search.

```
grep isadora -i file.txt
```

#### clear
Finally, a command that helps to organize a bit of the confusion of letters that remain in the terminal after hours of use. To clear all of it, run the clear command. Then just use the terminal again as if nothing had happened.

```
clear
```
