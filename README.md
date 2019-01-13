# AES_IMPLEMENTATION

Advanced Encryption Standard is based on the Rijndael cipher developed by two Belgian cryptographers, Joan Daemen and Vincent Rijmen. Rijndael is a family of ciphers with different key and block sizes. 

For AES, 3 members of Rijndael has been selected, each with a block size of 128 bits and key sizes 128, 192 and 256 bits.

AES is the most advanced encryption scheme that encrypts the data such that the data is safe from any hacker or malicious person and is difficult for them to decrypt with #"negligible success probability".

AES takes input message and divides it into blocks of size 16 bytes. Padding is done if the message length is not a multiple of 16. Each block undergoes number of transformations that is equal to number of AES rounds that depends on the key length. Each transformation comprises of mainly 4 functions: subBytes(), shiftRows, mixColumns(), addRoundKey().

#IMPLEMENTATION DETAILS OF AES

The AES encryption process is done in following steps:

1. keyExpansion() : During a simple encryption, one might XOR key with the message. But an adversary can get the message back by just XORing back with the cipher text. So, in AES, key is expanded depending upon the initial key length and number of AES rounds as shown below. If number of AES rounds are 10 then 10 different keys are required for encryption of a block.

KEY LENGTH (Bytes) |   AES ROUNDS  |  KEY EXPANSION SIZE(Bytes)
-------------------|---------------|----------------------------
  128              |       10      |          176
  196              |       12      |          208
  256              |       14      |          240
  
2. AddRoundKey() : This function just XOR all the elements of block with the sub key from the expanded key in every AES round. It is beneficial as it helps to increase the security. Also, if a key is not added in any round with the block, then the block does not depend on the key that will have serious security problems and it would be an unkeyed permutation.

3. SubBytes() : The function uses S-box in order to substitute values into the block. S-box are the basic component of symmetric key algorithm and essential part of block cipher. The more complex a S-box is, the stronger the encryption will be.

4. ShiftRows() : Transformation in the state matrix by rotating the last three rows by different offsets.

5. MixColumns() : The MixColumn is based on Galois field arithmetic and basically is matrix multiplication of state matrix with galois matrix.


REFERENCES -
1) AES standard - http://csrc.nist.gov/publications/fips/fips197/fips-197.pdf
2) NIST example algorithms - http://csrc.nist.gov/groups/ST/toolkit/examples.html for evaluation of implemetation
3) Securecoding - https://wiki.sei.cmu.edu/confluence/display/c/SEI+CERT+C+Coding+Standard
4) Confusion and Diffusion - https://en.wikipedia.org/wiki/Confusion_and_diffusion
5) Confusion and diffusion - https://www.cse.ust.hk/faculty/cding/CSIT571/SLIDES/confdiffu.pdf
6) Attacks- https://www.rsaconference.com/writable/presentations/file_upload/cryp-203.pdf
7) Miscellaneous - http://ieeexplore.ieee.org/document/4735012/
8) Related-key boomerang attacks - https://eprint.iacr.org/2008/438.pdf
9) Crypto coding practices - https://cryptocoding.net/index.php/Coding_rules
10) Access based cache attacks - https://eprint.iacr.org/2010/594.pdf
