# How To Log Into Course-Specific Account on ieng6
----
## Installing VSCode

Click on this link to go to the Visual Studio Code website: 
[Link](https://code.visualstudio.com/)

Follow the instructions and make sure you are downloading the right 
version for your device, like OSX (for Mac) or Windows (for PC).

When you open up Visual Studio Code, it should look something like this.

![Image](vscode_image.png)

Do not worry if some things look different such as the color or different tabs.
In this picture, I have the terminal opened up so it might look slighty
different. 

## Remotely Connecting

You might wonder: Why do we need to do this? Well many jobs and instituions use
course-specific accounts. It is more accessible which allows you to connect to 
a remote computer over the Internet to do work there. 

The first step to remotely connect on Windows is to install `git` for Windows: 
[Link](https://gitforwindows.org/)

After that you need to follow this post to properly set up your default terminal 
to use `git bash` in Visual Studio Code: [Link](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994)

Open up a terminal Visual Studio Code by pressing on `Terminal` and then `New Terminal` on the very top bar and insert this command where `zz` is replaced with your course-specific account. 

```
# $ ssh cs15lwi23zz@ieng6.ucsd.edu
```

It should look something like this if you have logged on before but if you haven't, type in `yes` and press enter. Then you give your password. 

![Image](remote_connecting.png)

## Trying Some Commands

Some basic commands you can try are:
* `cd ~`
* `cd`
* `mkdir`
* `ls -lat`
* `ls -a`
* `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
* `cat /home/linux/ieng6/cs15lwi23/public/hello.txt`

Try to figure out what they mean and if they produce any error messages. Here is what I have when I put in these commands. What makes yours and mine different? Why do some of them say "File Not Found"? 

![Image](code_commands.png)

If you got to the end of this page, **CONGRATULATIONS!!** You have successfully set up your course-specific account. Happy coding :DD 

![Image](360_F_307968645_mUnl6JiKrvODZlPKOqG1H5Td22OLNVS0.jpg)


