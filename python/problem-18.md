practice_text_file_analyser_v1
Write a python program to perform the following tasks: ​

Read the contents of a file ​
Analyze the contents and generate a report
Write the stat data dictionary to json file​

The function will take file content as the parameter and return a report, i.e., a dictionary with the following results ​with keys and data

longest_word: Longest word in the file
longest_word_length: Length of the longest word in the file
longest_para: Longest paragraph in words​
longest_para_length: Length of the longest paragraph in words​
shortest_para: Shortest paragraph in words​
shortest_para_length: Length of the shortest paragraph in words​
total_paras_count: total number of paragraphs ​

Write the stats into {{filename}}_stats.json file.​ {{filename}} to be replaced with the same file that is to read
You have to use the file file_to_analyse.txt to test your solution for its working.
The solution should be working with any textfiles.
The program should not crash with unexpected errors
