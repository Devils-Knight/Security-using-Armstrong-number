# Security-using-Armstrong-number
This project is based on creating an Encrypting and Decrypting algorithm using armstrong number and mapping color's rgb into matrix <br>
Along with this there is also implementation of
- Multithreading(threads, join, daemon)
- File handlinig(open, seek file pointer, chunking)
- Abstract base class 

## Implementaion
For faster Encryption and Decryption file chunking and threading is done on the target file.<br>
![image](implementation_approach.png)<br>
###  Encryption process :
1. Take the file(any) which needs to be Encrypted
2. File is divided into 4 chunks, each chunk undergo encryption at the same time using threading
3. Numeric key is created using _Armstrong_ number and the _Passphrase_ given by user for encryption.
4. Creating a rgb color with Numeric key, And maping(r,g,b) it into _16x16_ matrix.
5. Encryption process is divided into 2 steps:
    * Encrypting every byte of data by taking XOR with the nummeric key 
    * Dividing the encrypted byte into nibbles of 4-4 bits(0-15) and formulating them into rows and columns and returning the value placed in the color matrix using these rows and columns.
6. Repeating the above process for every byte and then storing them into an encryted file. 

###  Decryption process :
1. Take the file(any) which needs to be Decrypted
2. File is divided into 4 chunks, each chunk undergo decryption at the same time using threading
3. Numeric key is created using _Armstrong_ number and the _Passphrase_ given by user for decryption.
4. Creating a rgb color with Numeric key, And maping(r,g,b) it into _16x16_ matrix.
5. Decryption process is divided into 2 steps:
    * Finding the encrypted byte in color matrix and finding the row and column associated with it, each of them represent nibble of 4-4 bit(0-15) and then combining them to create that encrypted byte.
    * Which then is Decrypted by taking XOR with the nummeric key.     
6. Repeating the above process for every byte and then storing them into a file.
7. After the process is completed the original file will be retrieved.
<br>
#### The Complexity for both the processes is O(n) and with threading, this is a very fast and secure process.<br><br>

# Thank you  
















