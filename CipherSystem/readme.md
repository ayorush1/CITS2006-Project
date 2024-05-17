These are all the files for the Cipher System for my Project. The Cipher System is used through the RBAencryption.py and RBAdecryption.py files. 

The parameters of both the functions are:
Usage: python3 RBAencryption.py [ciphersystem] [cipherkeyset]

where,

[ciphersystem] = XOR, DES, VIG, RC4 -> Specificies the type of encryption scheme we want to use. This allows the MTD implementation to change the cipher system (encryption used) simply and effectively. Limited to these four. 

[cipherkeyset] = "keyset1", "randomvalue", ... etc. -> is the 'name' of the key we are using. This can be any value, and simply maps to a key in a secure file. Think of this as the value in a (value):(key) pair, where you put in the value and the program will find the key, or if not found it will create a new 50-character key and store that value:key into the secure file for future use. 
This allows the MTD implementation to change the key used for encryption and decryption (symmetric) simply and effectively. 

In this way, we can vary/change both the cipher system and the keys we are using for file system encryption/decryption.

Some Notes: 
1. The VIG and DES only works for alphanumeric inputs (files opened with "r" access), as VIG is a poly-alphabetic cipher. I was so close to getting the DES to work with binary data, but due to its complexity and time-limits I only managed to get it to be 100% successful with "r" data (not binary data).

The XOR and RC4 ciphers can work with binary data and can encrypt or decrypt almost any file, including images (such as in the example directory attached!).


2. The directory that will be recursively scanned and have its files encrypted is hardcoded into RBAencryption.py and RBAdecryption.py under the assignment 'directory = "..."'. If you want to change the directory you might need to change it in the code. 
 
