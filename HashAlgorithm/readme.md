


These are all the files for the Hashing Algorithm (system) for my Project. 

To use the hashing algorithm, you:
1. call RBAhashalgorithm.py, which produces a CSV file with all the files and their respective 50-character hashes.
2. modify any files (for demonstration purposes)
3. call RBATestHashedCsv.py, which does the exact same thing but outputs the files and their hashes into a different CSV file.
4. call compare_hashes.py, which reads both the files names and identifies (prints) any files with a differing hash between files, thus allowing to check the integrity of files and whether they have been modified in any way or not.

   
The parameters of both RBAhashalgorithm.py and RBATestHashedCsv.py are:

Usage: python3 RBAhashalgorithm.py [hashing_algorithm] [salt_set]

where,

[hashing_algorithm] = XOR or SHA -> Specificies the type of hashing algorithm we want to use. This allows the MTD implementation to change the hashing algorithm simply and effectively. 

[salt_set] = "salt1", "randomvalue", ... etc. -> is the 'name' of the salt we are using. This can be any value, and simply maps to a salt in a secure file. Think of this as the value in a (value):(key) pair, where you put in the value and the program will find the salt, or if not found it will create a new 50-character salt and store that value:salt into the secure file for future use. 
This allows the MTD implementation to change the salt used during hashing simply and effectively, thus increasing the security. 

In this way, we can vary/change both the hashing algorithm and the salt we are using for the hashing of our files in our filesystem. 

Some Notes: 
1. When using the XOR hashing algorithm, the program takes a fair amount of time to complete (~10 seconds).
2. The directory which is recursively scanned and has all its files hashed is hardcoded into RBAhashalgorithm.py and RBATestHashedCsv.py. If it needs changing, it will have to be changed under the assignment statement 'directory = "..."'. 
