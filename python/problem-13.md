Practic - Check Network Command
Your organization is setting up a new office and they want to create exclusive networks for each of their departments. They started with assigning the network for each department. Now they want to confirm that any two systems of different departments should not be a part of the same network and should not be able to communicate with each other.
Previously, we learned how to calculate the network ID of the given IP using the IP address and the subnet mask. Now, let's try to automate the process of calculating the network id from the given IP address and CIDR, and then use it to check whether the two given IPs are on the same network or a different one.

Part 1
Write a Python module to create two functions to convert decimal to binary and vice versa:

dec2bin(decnum): A function that takes in a decimal number and returns its equivalent binary string.
bin2dec(binstr): A function that takes in a binary string and returns its decimal equivalent.


Part 2
Write a Python module to take an IP address in the format: 192.168.X.XX/XX

calculate_network_id(ip): A function that takes in an IP string and return its network ID in string format.


Part 3
Write a Python script to create a Linux command to check if the two given IPs are in the same network.
Command Syntax and output:
