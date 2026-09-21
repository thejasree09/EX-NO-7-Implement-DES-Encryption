EX-NO-7-Implement-DES-Encryption
NAME: KIRUTIKA K R
REG NO: 212224230128
Aim:
To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

ALGORITHM:
DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
DES uses a Feistel network structure with 16 rounds of processing for encryption.
DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.
Program:
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
Output:
image
Result:
The program is executed successfully The program is executed successfully
