Introduction to Linux and shells

https://www.onworks.net/runos/create-os.html

From <https://meet.go+ogle.com/ezq-hmmg-cjm> 


 
 
What is Linux?
Linux is an operating system, like macOS or Windows.
 
It is also the most popular Open Source operating system, and it gives
you a lot of freedom.
 
It powers the vast majority of the servers that compose the Internet.
It's the base upon which everything is built. But not just that. Android
is based on (a modified version of) Linux.
 
The Linux "core"(called a kernel) was born in 1991 in Finland, and it
has come a really long way from its humble beginnings. It went on to
be the kernel of the GNU Operating System, creating the duo
GNU/Linux.
 
There's one thing about Linux that corporations like Microsoft, Apple,
and Google will never be able to offer: the freedom to do whatever
you want with your computer.
 
 
 
Linux is the ultimate freedom.
 
It is developed by volunteers, some paid by companies that rely on it,
some independently. But there's no single commercial company that
can dictate what goes into Linux, or the project's priorities.
 
You can also use Linux as your day to day computer. I use macOS
because I really enjoy the applications and design (and I also used to
be an iOS and Mac apps developer). But before using macOS I used
Linux as my main computer Operating System.
 
No one can dictate which apps you can run, or "call home" with apps
that track you, your position, and more.
 
Linux is also special because there's not just "one Linux", like is the
case with Windows or macOS. Instead, we have distributions.
 
A "distro" is made by a company or organization and packages the
Linux core with additional programs and tooling.
 
For example you have Debian, Red Hat, and Ubuntu, probably the
most popular distributions.
 
But many, many more exist. You can create your own distribution, too.
But most likely you'll use a popular one that has lots of users and a
community of people around it. This lets you do what you need to do
without losing too much time reinventing the wheel and figuring out
answers to common problems.
 
 
idea of how Linux works.
 
I don't have a Linux computer.
 
If you use a Mac, you just need to know that under the hood macOS is
a UNIX Operating System. It shares a lot of the same ideas and
software that a GNU/Linux system uses, because GNU/Linux is a free
alternative to UNIX.
 
UNIX is an umbrella term that groups many operating systems used
in big corporations and institutions, starting from the 70's
The macOS terminal gives you access to the same exact commands I'll
describe in the rest of this handbook.
 
Microsoft has an official Windows Subsystem for Linux which you can
(and should!) install on Windows. This will give you the ability to run
Linux in a very easy way on your PC.
 
But the vast majority of the time you will run a Linux computer in the
cloud via a VPS (Virtual Private Server) like Digital Ocean.
 
What is a Linux shell?
 
A shell is a command interpreter that exposes an interface to the user
to work with the underlying operating system.
 
It allows you to execute operations using text and commands, and it
provides users advanced features like being able to create scripts.
options without being too complex to use.
 
There are many different kind of shells. This post focuses on Unix
shells, the ones that you will find commonly on Linux and macOS
computers.
 
Many different kind of shells were created for those systems over
time, and a few of them dominate the space: Bash, Csh, Zsh, Fish and
many more!
All shells originate from the Bourne Shell, called sh . "Bourne"
because its creator was Steve Bourne.
 
Bash means Bourne-again shell. sh was proprietary and not open
source, and Bash was created in 1989 to create a free alternative for
the GNU project and the Free Software Foundation. Since projects
had to pay to use the Bourne shell, Bash became very popular.
 
If you use a Mac, try opening your Mac terminal. By default it runs
ZSH (or, pre-Catalina, Bash).
 
You can set up your system to run any kind of shell – for example I use
the Fish shell.
 
Each single shell has its own unique features and advanced usage, but
they all share a common functionality: they can let you execute
programs, and they can be programmed.
 
In the rest of this handbook we'll see in detail the most common
 
To use linux terminal in windows
 
        PowerShell as a administrator run this command(WSL (windows sub system for linux))
             
            >>    wsl --install
             
        After  this process u need to restart your machine
        And search for ubuntu and open
        In terminal u have to   give  new user credentials
         
         
        After that  in Microsoft store search for windows terminal  and install
        Then  process over !
         
        To reset password
            open cmd for open root user
                >ubuntu config --default-user root
                 



                 
             
         
 
 
 
 
 
 
 
 
 
 
 
whoami    :
 
        To find user
         
        
        
        
         
         
         
         
         
man           :
         
         
        Every time I don't know how to use a command, I type man <command>  to get the manual
         
         
        
        
        
         
        THE output should be like this
         
        
        
        
         
         
         
         
clear :
        The clear command is used to clear all the commands that were ran in the current terminal
         
        
        
        
         
        After execute clear command
         
        
        
        
         
         
        Clear -x :
         
            it is used to clear current page only
             
pwd  :
        it stands for (print working directory)
 
        Whenever you feel lost in the filesystem, call the pwd command to know where you are:
         
        
        
        
         
        It will print the current folder path.
         
         
ls      :
 
        Inside a folder you can list all the files that the folder contains using the ls command
         
         
        
        
        
     
     
ls  -al :
         
         
         
        ls -a   :
            (this command used to print all the hidden files from the folder)
         
        ls -l  :
            (this command is used to print hidden file which has . Before file name )
         
         
        ls  -al   :
            
            
            
            Compared to the plain ls command, this returns much more
            information.
            You have, from left to right:
             
            the file permissions (and if your system supports ACLs, you get
            an ACL flag as well)
             
            the number of links to that file
            the owner of the file
             
             
cd        :
         
        Once you have a folder, you can move into it using the cd command. cd means change directory. You invoke it specifying a folder to move into. You can specify a folder name, or an entire path.
         
        
        
        
         
         
        cd ..                (back to the home folder)
         
        
        
        
         
         
        If you want go to multiple folders back we use
         
         
            cd ../../../
             
         
         
         
        
        
        
             
             
        If u don’t know the folder exact directory u can use
         
         
         
        cd ~/colt
         
         
        This command is directly go  from home folder directory
         
         
Mkdir          :
         
        You create folders using the mkdir command
         
        
        
        
         
        You can create multiple folders with one command
         
         
        
        
        
         
        You can also create multiple nested folders by adding the -p option
         
        
        
        
         
         
        
        
        
         
         
         
touch            :
 
        You can create a empty folder using touch command
         
        If the file already exist  the time stamp of the file is updated
         
        
        
        
         
rmdir        :
 
        Just as you can create a folder using mkdir, you can delete a folder using rmdir
        
        
        
         
         
        You can also delete multiple folders at once
         
        
        
        
         
        If you want to delete file instead of folder we can use  rm command
         
        >>       rm <filename>
         
        The folder you delete must be empty.
        To delete folders with files in them, we'll use the more generic rm command which deletes files and folders, using the -rf option
        
        
        
         
        Be careful as this command does not ask for confirmation and it will immediately remove anything you ask it to remove.
        There is no bin when removing files from the command line, and recovering lost files can be hard.
         
        if u have multiple files in folder and u want to remove only selected files then we can use -r and -i for asking for each file
         
        >> rm -ri <foldername>      # -r for recursive -i for interactive mode
         
        
        
        
         
         
open :
        The open command lets you open a file using this syntax
         
        In that directory use command to open file
         
         
        >>      open <filename>
     
     
        
        
        
         
         
         
Mv    :
        It stands for move
         
        Once you have a file, you can move it around using the mv command. You specify the file current path, and its new path
         
        
        
        
 
         
         
        If you want to rename a file which is already exist  we can use
         
        Mv <file name>  <new name of  file
         
         
        
        
        
         
         
         
        If u want to move to one directory we can use
         
         
        
        
        
         
         
         
cp       :
 
        You can copy a file using the cp command(copied file created in a given name)
         
        
        
        
         
         
        To copy folders you need to add the -r option to recursively copy the whole folder contents:
         
        
        
        
 
         
         
head :
    It is used to print 1st 10 lines of a file content
    
    
    
    
    
         
    If u want to specify number of lines need to print u can use -n flag
     
        >> head <file name > -n < no of lines need to print >
         
     
    
    
    
 
tail  :
        Tail command is used to print last 10 lines of a file
         
            >> tail <file name>
             
             
        The best use case of tail in my opinion is when called with the -f option. It opens the file at the end, and watches for file changes.
        Any time there is new content in the file, it is printed in the window. This is great for watching log files, for example
         
        >>  tail -f /var/log/system.log
         
        To exit, press ctrl-C .
         
         
        You can print the last 10 lines in a file
         
        >> tail -n 10 <file name>
         
        You can print the whole file content starting from a specific line using + before the line number
         
        >> tail -n +10  <file name>
         
Redirecting standard output to a file :
 
 
    we can use  >  to over ride file content
        >>       echo test  > test.txt
        >>      ls -l    >   test.txt
        >>       date >   test.txt
     
    We can use  >> to append output to   file content
     
        >>    ls -l   >>    test.txt
        >>   date   >>   test.txt
         
         
Cat  :
         
        Similar to tail in some ways, we have cat . Except cat can also add content to a file, and this makes it super powerful.
        In its simplest usage, cat prints a file's content to the standard output
         
        You can print the content of multiple files
         
        >>     cat file1 file2
         
         
        and using the output redirection operator > you can concatenate the content of multiple files into a new file
         
        >>     cat file1 file2 > file3
         
        Using >> you can append the content of multiple files into a new file, creating it if it does not exist
         
        >>    cat file1 file2 >> file3
         
         
        When you're looking at source code files it's helpful to see the line numbers. You can have cat print them using the -n option
         
         
         
        >>  cat -n file1
         
         
         
less     :
        It shows you the content stored inside a file, in a nice and interactive UI.
         
        >>     less <filename>
         
         
        Once you are inside a less session, you can quit by pressing q.
        You can navigate the file contents using the up and down keys, or using the space bar and b to navigate page by page. You can also jump to the end of the file pressing G and jump back to the start by pressing g.
        You can search contents inside the file by pressing / and typing a word to search. This searches forward. You can search backwards using the ? symbol and typing a word.
        This command just visualizes the file's content. You can directly open an editor by pressing v. It will use the system editor, which in most cases is vim.
        Pressing the F key enters follow mode, or watch mode. When the file is changed by someone else, like from another program, you get to see the changes live.
        This doesn't happen by default, and you only see the file version at the time you opened it. You need to press ctrl-C to quit this mode. In this case the behavior is similar to running the tail -f <filename> command.
        You can open multiple files, and navigate through them using :n (to go to the next file) and :p (to go to the previous).
         
         
         
         
Echo :
        The echo command does one simple job: it prints to the output the argument passed to it
         
         
        >>         echo "hello"
        will print hello to the terminal.
        We can append the output to a file
         
        >>        echo "hello" >> output.txt
         
         
        We can interpolate environment variables
             
            >>  echo "The path variable is $PATH"
             
        This is just the start. We can do some nice things when it comes to interacting with the shell features.
         
        We can echo the files in the current folder
         
        >>       echo *
         
         
        We can echo the files in the current folder that start with the letter o
         
        >>   cho o*
         
        You can also execute commands, and print the result to the standard output (or to file, as you saw
         
        >>    echo $(ls -al)
         
        You can generate a list of strings, for example ranges
         
         
        >>   echo {1..5}
        
        
        
         
         
         
wc :
        It stands for word count
         
        The wc command gives us useful information about a file or input it receives via pipes.
         
        
        
        
         
         
        Example via pipes, we can count the output of running the ls -al command
         
         
        
        
        
         
         
        The first column returned is the number of lines. The second is the number of words. The third is the number of bytes.
         
        We can tell it to just count the lines
         
        
        
        
         
         
        or just the words
         
        
        
        
         
         
         
        Bytes in ASCII charsets equate to characters. But with non-ASCII charsets, the number of characters might differ because some characters might take multiple bytes (for example this happens in Unicode).
         
        In this case the -m flag will help you get the correct value:
         
         
Sort      :
        Suppose u have  text which contains  the name of dogs
         
        
        
        
         
         
        -u  flag is used to sort  output with unique values
        -n  flag is used to sort  output with  values by number values
         
         
Uniq   :
        uniq is a command that helps you sort lines of text.
        You can get those lines from a file, or using pipes from the output of another command
         
        >>>      uniq dogs.txt
        >>>     ls | uniq
         
         
        You need to consider this key thing: uniq will only detect adjacent duplicate lines.
        This implies that you will most likely use it along with sort
         
         
        The sort command has its own way to remove duplicates with the - u (unique) option. But uniq has more power
         
        By default it removes duplicate lines
         
        You can tell it to only display duplicate lines, for example, with the -d
        >>>    sort dogs.txt | uniq -d
         
         
        You can use the -u option to only display non-duplicate lines
         
         
Diff       :
 
        diff is a handy command. Suppose you have 2 files, which contain almost the same information, but you can't find the difference between the two
        diff will process the files and will tell you what's the difference.
         
        Suppose you have 2 files: dogs.txt and moredogs.txt . The difference is that moredogs.txt contains one more dog name
         
        
        
        
         
        diff dogs.txt moredogs.txt will tell you the second file has one more line,
        line 3 with the line Vanille
         
        
        
        
         
         
        Using the -y option will compare the 2 files line by line
         
         
         
Find :
 
        The find command can be used to find files or folders matching a particular search pattern. It searches recursively.
         
         
        Find all the files under the current tree that have the .js extension and print the relative path of each file that matches
         
        
        
        
         
        Or to find with name
         
        
        
        
     
     
     
        To mention a directrory and search
         
        
        
        
         
        IF  u want to search in all folders  we can use . In the place of  jsfiles
         
        >>>    find .  Or <file path >  -name "*<filename*>
         
        It's important to use quotes around special characters like * to avoid the shell interpreting them.
         
        Find directories under the current tree matching the name "src"
         
        Use -type f to search only files, or -type l to only search symbolic links.
         
        -name is case sensitive. use -iname to perform a case-insensitive search.
         
        You can search under multiple root trees:
         
        >>>>   find folder1 folder2 -name filename.txt
         
         
         
         
        Find directories under the current tree matching the name "node modules" or 'public':
         
         
        >>>        find . -type d -name node_modules -or -name public
         
         
         
        You can also exclude a path using -not -path
         
            >>>      find . -type d -name '*.md' -not -path 'node_modules/*'
             
             
        You can search files that have more than 100 characters (bytes) in them
         
         
            >>>     find . -type f -size +100c
             
            >>>    find . -type f -size +100k -size -1M
             
             
        Search files edited more than 3 days ago
         
         
            >>>   find . -type f -mtime +3
             
             
             
        Search files edited in the last 24 hours:
         
         
            >>>       find . -type f -mtime -1
             
             
             
        You can delete all the files matching a search by adding the -delete option. This deletes all the files edited in the last 24 hours
         
         
            >>>     find . -type f -mtime -1 -delete
             
             
             
             
Grep :
        You can use grep to search in files, or combine it with pipes to filter the output of another command.( it is used to find text inside a file )
         
         
        For example here's how we can find the occurrences of the document.getElementById line in the index.md file
         
            >>>    grep document.getElementById index.md
             
            
            
            
             
             
             
        Using the -n option it will show the line numbers:
             
            >>>       grep -n document.getElementById index.md
         
         
        One very useful thing is to tell grep to print 2 lines before and 2 lines after the matched line to give you more context. That's done using the -C option, which accepts a number of lines
         
         
            >>>    grep -nC 2 document.getElementById index.md      # C is capital
             
             
        Another thing you might find very useful is to invert the result, excluding the lines that match a particular string, using the -v option
             
            >>>   less index.md | grep -n document.getElementById
             
             
             
        For example if u want to search a string in all the files in the directory u can use -r (recursive)
         
         
            >>>     grep -r  "text  u want to search"    .   Or  <folder path >
             
            #   -i can be used for insensitive    means there is no selection of upper case and lowercase it will print both
            
         Case insensitive search : The -i option enables to search for a string case insensitively in the given file. It matches the words like “UNIX”, “Unix”, “unix”. 
        
         
        
        Displaying the count of number of matches : We can find the number of lines that matches the given string/pattern
        
        grep -c "unix" geekfile.txt
        
        
        
        Display the file names that matches the pattern : We can just display the files that contains the given string/pattern. 
         
        $grep -l "unix" *
        
        grep -l "unix" f1.txt f2.txt f3.xt f4.txt
        
        
        
        
        
        
        
        
             
             
             
Du    : (disk utility)
        The du command will calculate the size of a directory as a whole (file size and folder size)
         
        here is a value expressed in bytes
         
        
        
        
             
             
        You can set du to display values in Megabytes using du -m , and Gigabytes using du -g .
         
        The -h option will show a human-readable notation for sizes, adapting to the size
         
         
         
Df               :
        The df command is used to get disk usage information.
        Its basic form will print information about the volumes mounted
         
         
        
        
        
         
         
        You can also specify a file or directory name to get information about the specific volume it lives on
         
         
        
        
        
         
         
History   :
        Every time you run a command, it's memorized in the history.
         
        You can display all the history using
         
            >>>      history
             
        This shows the history with numbers
         
        
        
        
         
         
         
        You can combine this with grep to find a command you ran
             
            >>>      history | grep docker
             
             
        
        
        
         
         
         
        To clear the history, run history -c .
         
         
Ps :                 (process status )
        Your computer run  all times  tuns of different processes
        you can inspect them by using ps command
         
         
         
Top :
 
 
        The top command is used to display dynamic real-time information about running processes in the system
         
Kill :
        The kill program can send a variety of signals to a program
        It's not just used to terminate a program, like the name would suggest, but that's its main job.
        We use it in this way
         
            >>>> kill <pid>
             
        By default, this sends the TERM signal to the process id specified.
         
        We can use flags to send other signals, including:
     
            kill -HUP <PID>
            kill -INT <PID>
            kill -KILL <PID>
            kill -TERM <PID>
            kill -CONT <PID>
            kill -STOP <PID>
         
Killall :
        Killall used to kill the processes withot id by usin name if u want to kill the processes name by some thing u can use
         
            >>> kill -KILL or -9 or SIGKILL  "name of the processes"
             
             
             
Jobs:
        When we run a command in Linux / macOS, we can set it to run in the background using the & symbol after the command
         
         
        We can get back to that program using the fg command. This works fine if we just have one job in the background, otherwise we need to use the job number: fg 1 , fg 2 and so on.
         
         
        Use >>>   bg <id>     #to run in background
        Use >>>  fg <id>       #to run in foreground
         
Gzip :
        You can compress a file using the gzip compression protocol named LZ77 using the gzip command.
         
         
         
        >>> gzip filename
         
        This will compress the file, and append a .gz extension to it. The
        original file is deleted.
         
         
        To prevent this, you can use the -c option and use output redirection
        to write the output to the filename.gz file:
         
            >>     gzip -c filename > filename.gz
             
        The -c option specifiesthat the output will go to the standard
        outputstream, leaving the original file intact.
         
        Or you can use the -k option:
         
        gzip -k filename
         
         
        There are various levels of compression. The more the compression, the longer it will take to compress (and decompress). Levels range from 1 (fastest, worst compression) to 9 (slowest, better compression), and the default is 6
         
        You can compress multiple files by listing them
         
            >>>   gzip filename1 filename2
             
        You can compress all the files in a directory, recursively, using the -r option
         
            >>> gzip -r a_folder
         
        The -v option prints the compression percentage information. Here's an example of it being used along with the -k (keep) option
         
        
        
        
         
         
        gzip can also be used to decompress a file, using the -d option
         
            >>>    gzip -d filename.gz
             
         
         
         
Gunzip     :
         
        The gunzip command is basically equivalent to the gzip command, except the -d option is always enabled by default
         
         
        The command can be invoked in this way
         
            >>> gunzip filename.gz
             
             
        This will gunzip and will remove the .gz extension, putting the result
        in the filename file. If that file exists, it will overwrite that.
         
         
        You can extract to a different filename using output redirection using
        the -c option:
         
            >>>      gunzip -c filename.gz > anotherfilename
         
         
Tar :
    tar is used to create  multiple files in to a file  it is an  archive grouping
    U can use command
        >>>    tar -cf archive.tar file1 file2 file3
         
        C option is stnads for create  f option used to write to file archive
         
    To extract files from an archive in the current folder, use:
     
        >>>  tar -xf archive.tar
         
        the x option standsfor extract.
         
    And to extract them to a specific directory, use:
     
        >>> tar -xf archive.tar -C director
         
    To check archived files u can use :
         
        >>> tar -tf archive.tar
         
    tar is often used to create a compressed archive, gzipping the archive.
     
    This is done using the z option:
     
        >>> tar -czf archive.tar.gz file1 file2
     
    This is just like creating a tar archive, and then running gzip on it.
     
    To unarchive a gzipped archive, you can use gunzip , or gzip -d , and
    then unarchive it. But tar -xf will recognize it's a gzipped archive,
    and do it for you:
     
        >>>  tar -xf archive.tar.gz
     
     
     
Nano :
        Nano is beginner friendly editor
         
        To run nano
            >>>  nano <file name >
             
             
            To exit or save file u can use  CTRL+X
            Then hit y to save
            Hit n to don’t exit
             
Alias     :
        It's common to always run a program with a set of options that you like using.
        For example, take the ls command. By default it prints very little information:
        
        
        
        But if you use the -al option it will print something more useful, including the file modification date, the size, the owner, and the permissions. It will also list hidden files (files starting with a .):
        
        
        
        You can create a new command, for example I like to call it ll, that is an alias to ls -al.
        You do it like this:
        aliasll='ls -al'
        Once you do, you can call ll just like it was a regular UNIX command:
        
        
        
        Now calling alias without any option will list the aliases defined:
        
        
        
        The alias will work until the terminal session is closed.
         
         
Xargs:
        The xargs command is used in a UNIX shell to convert input from standard input into arguments to a command.
        In other words, through the use of xargs the output of a command is used as the input of another command.
        Here's the syntax you will use:
        command1 |xargscommand2
        We use a pipe (|) to pass the output to xargs. That will take care of running the command2 command, using the output of command1 as its argument(s).
        Let's do a simple example. You want to remove some specific files from a directory. Those files are listed inside a text file.
        We have 3 files: file1, file2, file3.
        In todelete.txt we have a list of files we want to delete, in this example file1 and file3:
        
        
        
        We will channel the output of cat todelete.txt to the rm command, through xargs.
        In this way:
        cattodelete.txt |xargsrm
        That's the result, the files we listed are now deleted:
        
        
        
        The way it works is that xargs will run rm 2 times, one for each line returned by cat.
        This is the simplest usage of xargs. There are several options we can use.
        One of the most useful, in my opinion (especially when starting to learn xargs), is -p. Using this option will make xargs print a confirmation prompt with the action it's going to take:
        
        
        
        The -n option lets you tell xargs to perform one iteration at a time, so you can individually confirm them with -p. Here we tell xargs to perform one iteration at a time with -n1:
        
        
        
        The -I option is another widely used one. It allows you to get the output into a placeholder, and then you can do various things.
        One of them is to run multiple commands:
        command1 |xargs-I % /bin/bash -c 'command2 %; command3 %'
        
        
        
        You can swap the % symbol I used above with anything else – it's a variable.
         
Ln   :
 
        The ln command is part of the Linux file system commands.
        It's used to create links. What is a link? It's like a pointer to another file, or a file that points to another file. You might be familiar with Windows shortcuts. They're similar.
        We have 2 types of links: hard links and soft links.
        Hard links
        Hard links are rarely used. They have a few limitations: you can't link to directories, and you can't link to external filesystems (disks).
        A hard link is created using the following syntax:
        ln<original><link>
        For example, say you have a file called recipes.txt. You can create a hard link to it using:
        lnrecipes.txt newrecipes.txt
        The new hard link you created is indistinguishable from a regular file:
        
        
        
        Now any time you edit any of those files, the content will be updated for both.
        If you delete the original file, the link will still contain the original file content, as that's not removed until there is one hard link pointing to it.
        
        
        
        ADVERTISEMENT
        Soft links
        Soft links are different. They are more powerful as you can link to other filesystems and to directories. But keep in mind that when the original is removed, the link will be broken.
        You create soft links using the -s option of ln:
        ln-s <original><link>
        For example, say you have a file called recipes.txt. You can create a soft link to it using:
        ln-s recipes.txt newrecipes.txt
        In this case you can see there's a special l flag when you list the file using ls -al. The file name has a @ at the end, and it's also colored differently if you have colors enabled:
        
        
        
        Now if you delete the original file, the links will be broken, and the shell will tell you "No such file or directory" if you try to access it:
        
        
        
         
 
         
 
Who   :
        The who command displays the users logged in to the system.
         
         
        Unless you're using a server multiple people have access to, chances are you will be the only user logged in, multiple times:
        
        
        
        Why multiple times? Because each shell opened will count as an access.
         
        You can see the name of the terminal used, and the time/day the session was started.
         
        The -aH flags will tell who to display more information, including the idle time and the process ID of the terminal:
        
        
        
        The special who am i command will list the current terminal session details:
        
        
        
         
        
        
        
su :   (switch user)
 
        While you're logged in to the terminal shell with one user, you might need to switch to another user.
         
        For example you're logged in as root to perform some maintenance, but then you want to switch to a user account.
        You can do so with the su command:
         
            >> >     su <username>
             
        For example: su flavio.
         
        If you're logged in as a user, running su without anything else will prompt you to enter the root user password, as that's the default behavior.
        
        
        
        su will start a new shell as another user.
         
        When you're done, typing exit in the shell will close that shell, and will return you back to the current user's shell.
         
Sudo :  (super user do)
 
 
        sudo is commonly used to run a command as root.
         
        You must be enabled to use sudo, and once you are, you can run commands as root by entering your user's password (not the root user password).
         
        The permissions are highly configurable, which is great especially in a multi-user server environment. Some users can be granted access to running specific commands through sudo.
         
        For example you can edit a system configuration file:
         
            >>>        sudonano/etc/hosts
             
        which would otherwise fail to save since you don't have the permissions
        for it.
         
        You can run sudo -i to start a shell as root:
        
        
        
        You can use sudo to run commands as any user. root is the default, but use the -u option to specify another user:
         
         
            >>>      sudo-u flavio ls/Users/flavio
             
             
Passwd       :
 
        Users in Linux have a password assigned. You can change the password using the passwd command.
        There are two situations here.
         
        The first is when you want to change your password. In this case you type:
         
            >>>      passwd
             
        and an interactive prompt will ask you for the old password, then it will ask you for the new one:
        
        
        
        When you're root (or have superuser privileges) you can set the username for which you want to change the password:
         
            >>>     passwd<username><new password>
         
        In this case you don't need to enter the old one.
         
Chown:
 
        Every file/directory in an Operating System like Linux or macOS (and every UNIX system in general) has an owner.
        The owner of a file can do everything with it. It can decide the fate of that file.
         
        The owner (and the root user) can change the owner to another user, too, using the chown command:
         
        Chown  <owner> <file>
         
        Like this:
         
        Chown flavio test.txt
        For example if you have a file that's owned by root, you can't write to it as another user:
        
        
        
        You can use chown to transfer the ownership to you:
        
        
        
        It's rather common to need to change the ownership of a directory, and recursively all the files contained, plus all the subdirectories and the files contained in them, too.
         
        You can do so using the -R flag:
         
        chown-R <owner><file>
         
        Files/directories don't just have an owner, they also have a group. Through this command you can change that simultaneously while you change the owner:
         
        chown<owner>:<group><file>
         
        Example:
         
        chownflavio:users test.txt
        You can also just change the group of a file using the chgrp command:
         
        chgrp<group><filename>
         
         
         
Chmod     :
        
        
        
 
 
 
        
        
        
         
         
        
        
        
         
         
         
         
 
        
        
        
         
         
        
        
        
         
         
        
        
        
         
        
        
        
 
         
        Every file in the Linux / macOS Operating Systems (and UNIX systems in general) has 3 permissions: read, write, and execute.
         
        Go into a folder, and run the ls -al command.
         
        
        The weird strings you see on each file line, like drwxr-xr-x, define the permissions of the file or folder.
         
        Let's dissect it.
         
        The first letter indicates the type of file:
         
        - means it's a normal file
        
        d means it's a directory
        
        l means it's a link
        
        Then you have 3 sets of values:
         
        The first set represents the permissions of the owner of the file
        
        The second set represents the permissions of the members of the group the file is
         associated to
        
        The third set represents the permissions of the everyone else
        
        Those sets are composed by 3 values. rwx means that specific persona has read, write and execution access. Anything that is removed is swapped with a -, which lets you form various combinations of values and relative permissions: rw-, r--, r-x, and so on.
         
        You can change the permissions given to a file using the chmod command.
         
        chmod can be used in 2 ways. The first is using symbolic arguments, the second is using numeric arguments. Let's start with symbols first, which is more intuitive.
         
        You type chmod followed by a space, and a letter:
         
        a stands for all
        
        u stands for user
        
        g stands for group
        
        o stands for others
        
        Then you type either + or - to add a permission, or to remove it. Then you enter one or more permission symbols (r, w, x).
         
        All followed by the file or folder name.
         
        Here are some examples:
         
        chmod a+r filename #everyone can now read
        
        chmod a+rw filename #everyone can now read and write
        
        chmod o-rwx filename #others (not the owner, not in the same group of the file) cannot read, write or execute the file
        
        You can apply the same permissions to multiple personas by adding multiple letters before the +/-:
         
        chmod og-r filename #other and group can't read any more
        
        In case you are editing a folder, you can apply the permissions to every file contained in that folder using the -r (recursive) flag.
         
        Numeric arguments are faster but I find them hard to remember when you are not using them day to day. You use a digit that represents the permissions of the persona. This number value can be a maximum of 7, and it's calculated in this way:
         
        1 if has execution permission
        
        2 if has write permission
        
        4 if has read permission
        
        This gives us 4 combinations:
         
        0 no permissions
        
        1 can execute
        
        2 can write
        
        3 can write, execute
        
        4 can read
        
        5 can read, execute
        
        6 can read, write
        
        7 can read, write and execute
        
        We use them in pairs of 3, to set the permissions of all the 3 groups altogether:
         
        chmod 777 filename
        
        chmod 755 filename
        
        chmod 644 filename
        
        
Permissions in Linux

Linux is a multi-user operating system, so it has security to prevent people from accessing each other’s confidential files. 
 
Introduction
When you execute an “ls” command, you are not given any information about the security of the files, because by default “ls” only lists the names of files. You can get more information by using an “option” with the “ls” command. All options start with a ‘-‘. For example, to execute “ls” with the “long listing” option, you would type ls -l 
When you do so, each file will be listed on a separate line in long format. There is an example in the window below. 
 

There’s a lot of information in those lines. 
 
1. The first character will almost always be either a ‘-‘, which means it’s a file, or a ‘d’, which means it’s a directory.
2. The next nine characters (rw-r–r–) show the security; we’ll talk about them later.
3. The next column shows the owner of the file. In this case it is me, my userID is “aditya314”.
4. The next column shows the group owner of the file. In my case I want to give the “aditya314” group of people special access to these files.
5. The next column shows the size of the file in bytes.
6. The next column shows the date and time the file was last modified.
7. And, of course, the final column gives the filename.
Deciphering the security characters will take a bit more work. 
 
Understanding the security permissions
First, you must think of those nine characters as three sets of three characters (see the box at the bottom). Each of the three “rwx” characters refers to a different operation you can perform on the file. 
 
---     ---     ---
rwx     rwx     rwx
user    group   other
 
Read, write, execute and –
The ‘r’ means you can “read” the file’s contents. 
The ‘w’ means you can “write”, or modify, the file’s contents. 
The ‘x’ means you can “execute” the file. This permission is given only if the file is a program. 
If any of the “rwx” characters is replaced by a ‘-‘, then that permission has been revoked. 
 
User, group and others
user – The user permissions apply only the owner of the file or directory, they will not impact the actions of other users. 
group – The group permissions apply only to the group that has been assigned to the file or directory, they will not effect the actions of other users. 
others – The others permissions apply to all other users on the system, this is the permission group that you want to watch the most. 
 
Reading the security permissions
For example, consider that the user’s permissions for some files is “rw-” as the first three characters. This means that the owner of the file (“aditya314”, i.e. me) can “read” it (look at its contents) and “write” it (modify its contents). I cannot execute it because it is not a program; it is a text file. 
If “r-x” is the second set of 3 characters it means that the members of the group “aditya314” can only read and execute the files. 
The final three characters show the permissions allowed to anyone who has a UserID on this Linux system. Let us say we have the permission (“r–“). This means anyone in our Linux world can read, but they cannot modify the contents of the files or execute it. 
 
Changing security permissions
The command you use to change the security permissions on files is called “chmod”, which stands for “change mode”, because the nine security characters are collectively called the security “mode” of the file. 
 
8. The first argument you give to the “chmod” command is ‘u’, ‘g’, ‘o’. We use: 
u for user 
g for group 
o for others, 
you can also use a combination of them (u,g,o). 
This specifies which of the three groups you want to modify. 
 
9. After this use 
a ‘+’ for adding 
a ‘-‘ for removing 
and a “=” for assigning a permission.
10. Then specify the permission r,w or x you want to change. 
Here also you can use a combination of r,w,x. 
This specifies which of the three permissions “rwx” you want to modify
11. use can use commas to modify more permissions
12. Finally, the name of the file whose permission you are changing
An example will make this clearer. 
For example, if you want to give “execute” permission to the world (“other”) for file “xyz.txt”, you would start by typing 
 
chmod o
Now you would type a ‘+’ to say that you are “adding” a permission. 
 
chmod o+
Then you would type an ‘x’ to say that you are adding “execute” permission. 
 
chmod o+x
Finally, specify which file you are changing. 
 
chmod o+x xyz.txt
You can see the change in the picture below. 
 

You can also change multiple permissions at once. For example, if you want to take all permissions away from everyone, you would type 
 
chmod ugo-rwx xyz.txt
The code above revokes all the read(r), write(w) and execute(x) permission from all user(u), group(g) and others(o) for the file xyz.txt which results to this. 
 

Another example can be this: 
 
chmod ug+rw,o-x abc.mp4
The code above adds read(r) and write(w) permission to both user(u) and group(g) and revoke execute(x) permission from others(o) for the file abc.mp4. 
Something like this: 
 
chmod ug=rx,o+r abc.c
assigns read(r) and execute(x) permission to both user(u) and group(g) and add read permission to others for the file abc.c. 
There can be numerous combinations of file permissions you can invoke, revoke and assign. You can try some in your linux system. 
 
The octal notations
You can also use octal notations like this. 
 

Using the octal notations table instead of ‘r’, ‘w’ and ‘x’. Each digit octal notation can be used of either of the group ‘u’,’g’,’o’. 
So, the following work the same. 
 
chmod ugo+rwx [file_name]
chmod 777 [file_name]
Both of them provides full read write and execute permission (code=7) to all the group. 
Same is the case with this.. 
 
chmod u=r,g=wx,o=rx [file_name]
chmod 435 [file_name]
Both the codes give read (code=4) permission to user, write and execute (code=3) for group and read and execute (code=5) for others. 
And even this… 
 
chmod 775 [file_name]
chmod ug+rwx,o=rx [file_name]
Both the commands give all permissions (code=7) to user and group, read and execute (code=5) for others. 
 
