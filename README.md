# EX-NO-7-Implement-DES-Encryption
## NAME: KIRUTIKA K R
## REG NO: 212224230128

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```
#include <stdio.h> 
#include <string.h> 
void xorCrypt(char input[], char key[], char output[], int len) 
{ 
    int keyLen = strlen(key); 
    for (int i = 0; i < len; i++) 
    { 
        output[i] = input[i] ^ key[i % keyLen]; 
    } 
 
    output[len] = '\0'; 
} 
int main() 
{ 
    char message[100]; 
    char key[100]; 
    char encrypted[100]; 
    char decrypted[100]; 
 
    printf("Enter Plain Text: "); 
    fgets(message, sizeof(message), stdin); 
    message[strcspn(message, "\n")] = '\0'; 
 
    printf("Enter Key: "); 
    fgets(key, sizeof(key), stdin); 
    key[strcspn(key, "\n")] = '\0'; 
 
    int len = strlen(message); 
    xorCrypt(message, key, encrypted, len); 
 
    printf("\nEncrypted Text (Hex): "); 
    for (int i = 0; i < len; i++) 
    { 
        printf("%02X ", (unsigned char)encrypted[i]); 
    } 
    printf("\n"); 
    xorCrypt(encrypted, key, decrypted, len); 
   printf("Decrypted Text: %s\n", decrypted); 
return 0; 
}
```
## Output:
<img width="521" height="248" alt="image" src="https://github.com/user-attachments/assets/c40dd686-d144-4798-871d-95d4c7c3fbb5" />


## Result:
The program is executed successfully 
  The program is executed successfully

