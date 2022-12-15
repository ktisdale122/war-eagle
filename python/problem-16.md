Practice - Directory Stats Command
You are required to create a Linux command to display the statistical data of a directory based on the number of files, directories, and type of files it contains.
The implementation of creation of the command is divided into two parts:

Part 1
Create a Python module with a function get_dir_stats(path) that takes in the path of the directory as an input and returns some statistical data about the directory. The data returned should contain:

Number of files in the directory
Number of directories in the directory
Frequency of all the existing file formats.

For example: if the directory at /home/Documents/my-dir contains 3 directories and 2 files both of which are of type .md, the result should look something like:

Part 2:
Write a Python script to create a Linux command pwdstat that uses the function created in the module in Part 1. It should display the statistics of the directory path provided as the command argument.
Command syntax and output:
