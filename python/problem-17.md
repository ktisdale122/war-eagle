Challenge_custom_linux_commands_v1
Phoenix Corp. is a product-based software development organization. They recently found out that there were multiple security threats to their servers. Some external parties were trying to intrude the security of the system by trying to gain access to the logs of some deployed applications.
You are asked to help them identify the log files that were at risk or might be potential risks, present at the various workstations that might be used to penetrate the security of the organization’s servers.
Important Points:

Test all the commands to be created in this challenge using the directory structure present in the zipped file.
Manage the input, output and error streams for the commands.
Create a -h or --help option for each command to help the user identify all the features and the syntax of the command.
The solution scripts must not contain any extension, just the filename that would be used as the command.
Valid combinations of options should produce appropriate outputs, while invalid combinations should through invalidation errors.


Part 1: Listing the contents
In order to help the organization, identify the files at risk, or potential risk you need to keep a constant check on the file and directories getting created anonymously or getting updated very frequently.
To implement this, you are required to create an extended version of the Linux ls command as newls.py which would have some extra features as compared to the traditional ls command.
The newls.py command that you create should have the following features:

It should always display the last modified date-time along with the names of the constituents of the given path.
It should be able to display all files and folders.
There should be a to only view files.
There also should be an option to view only the folders.
It should be possible to filter the contents based on their last-modified time.

Example:
$ newls.py <relative or absolute path>  
Output: Gives a list of all the files and directories
The command should have multiple options which would list:

-F: only files
-D: only directories
--modifiedin: to provide time duration in hours, to filter the list by a time duration and only show the files and directories modified during that time period.

Syntax:
$ newls.py <options> <relative or absolute path> 
Example:
$ newls.py ./
Sample output:
Displays a list of all files and directories in the current path.

$ newls.py /home 
Return a list of all files and directories present in path /home
$ newls.py -F ./ 
Sample output:
Displays a list of files present in the current path
$ newls.py -F ./ --modifiedin 2 
Return a list of files and directories present in the current path, modified in last 2 hours.

Note: Incorrect combinations of options should show proper error message.
In this part, you will be expected to demonstrate concepts such as:

Reading and operating on command line arguments.
Utilizing functions of Python modules including os, sys and datetime.
Fetching the stats of files and directories.
Using output and error streams for execution results.
Using correct exit codes with output and error streams.
Filter files and directories based on the last modified time.


Part 2: Searching for files and directories.
In order to effectively identify the files at risk, we must also be able to easily find any file present in our workstations, be it by name or part of name i.e., it should be possible to search for any file at a specific location by name or part of name.
For example: If you know that any file with .exe might be at potential risk; you should be able to find all the files just by giving .exe as the parameter.
Thus, you are required to create an extended version of the Linux find command as newfind.py command which would have some extra features required by your organization, as compared to the traditional find command.
The newfind.py command that you create should have the following features:

Users should be able to find a file by name or part of name in the current location.
Users should be able to find a file by name or part of name in a specified location.
Users should be able to get creation and last modified datetime of the file.
The code should not fail for wrong options passed, instead should print out a validation error message.

Example:
newfind.py –n 'app2_23-05-2021.log' to find in current location. 

newfind.py –n 'test.txt' -d /home/
To find in directory home.
newfind.py –p 'app3' 
To find all log files and directories which have app3 string in their names, in the current location.

newfind.py –p 'tes' -d /home/ 
To find all files and directories which have tes in their names, in the home directory.
newfind.py –n 'text.txt' -d /home/ --mtime 
To find the file and if found, get the last modified datetime.
newfind.py –p 'ste' -d /home/Documents/ --ctime 
To find the files and directories by pattern and if any found, get the creation date for all.
newfind.py –p 'app' --mtime --ctime 
To find the files and directories by pattern and if any found, get the last modified datetime and creation datetime for all.

In this part you will be expected to demonstrate concepts such as:

Searching for a sub-string in each string.
Utilizing creation time of a file or directory.


Part 3: Moving the files to and from
The newls and newfind.py commands would help in identifying the files at risk or potential risk. But what to do after we have identified them?
To keep the servers safe, you would need to quarantine the files at risk, or to get them treated and fixed.
Thus, to implement this task, you are required to create an extended version of the Linux mv command as newmv.py command, which would have all the features required by your organization as compared to the traditional mv command.
The newmv.py command should have the following features:

It should allow moving files or directories from one location to another location.
It should also allow moving files or directories from multiple locations to a single location.

Options that should be available:

--one2one: to move files or directories from one location to another
--many2one: to move files or directories from multiple locations to a single location

Example:
newmv.py --one2one <source path> <destination path> 

newmv.py --many2one <source path 1> <source path 2> <source path 3> <destination path> 
In this part you will be expected to demonstrate concepts such as:

Utilizing functions of Python shutil module to move files and directories.


Part 4: Copying the files to all desired locations.
There were multiple files present in the workstations, that were not currently at risks, but were at potential risk. These files were required to be sent for security checks to improve the security levels. Thus, these files were to be copied to the directory in which the security checks were happening.
To implement this task, you are required to create an extended version of the Linux cp command as newcp.py that would have all the features required by your organization.
The newcp.py command that you create should have the following features:

It should be able to copy files from multiple locations to a single location and vice versa.
It should also be able to copy directories from a single location to multiple location.

Note: Use shutil for implementation of newcp.py. It does not support copying multiple directories to a target path.
Syntax:
newcp.py <-F or -D> <option> <source/s> <destination/s> 
Flags that should be available:

-F: To copy files
-D: To copy directories

Options to be available:

--one2many: To copy file or directory from one location to multiple locations, the first path will be treated as source and others as destinations.
--many2one: To copy multiple files at different locations to one location, the last path will be treated as destination and others as source

Example:
newcp.py -F --one2many <source file path> <destination path 1> <destination path 2>  

newcp.py -F --many2one <source file path 1> <source file path 2> <source path 3> <destination path> 

newcp.py -D --one2many <source dir path> <destination path 1> <destination path 2>  
In this part you will be expected to demonstrate concepts such as:

Copying files and directories from one location to another using the functions of Python shutil module.
