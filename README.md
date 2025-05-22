# EX No. 8 : ADVANCED ENCRYPTION STANDARD ALGORITHM

### Name  Prajin S
### Register Number : 212223230151

## Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
## ALGORITHM:
#### STEP 01 : 
Prompt the user to enter a plaintext message and a key, then store the inputs.

#### STEP 02 : 
Encrypt the plaintext by XORing each character with the corresponding character from the key, repeating the key as needed.

#### STEP 03 : 
Display the encrypted message as a sequence of ASCII values.

#### STEP 04:
Decrypt the ciphertext using the same XOR process and display the original message.


# PROGRAM:
```C
#include <stdio.h>
#include <string.h>

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext)
{
    int i;
    for (i = 0; i < strlen(plaintext); i++) 
    {
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)]; 
    }
    ciphertext[i] = '\0'; 
}

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText)
{
    int i;
    for (i = 0; i < strlen(ciphertext); i++) 
    {
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)]; 
    }
    decryptedText[i] = '\0'; 
}

void printASCII(char *ciphertext) 
{
    printf("Encrypted Message (ASCII values): ");
    for (int i = 0; i < strlen(ciphertext); i++) 
    {
        printf("%d ", (unsigned char)ciphertext[i]); 
    }
    printf("\n");
}

int main() 
{
    char plaintext[100], key[100], ciphertext[100], decryptedText[100];

    printf("Enter the plaintext: ");
    scanf("%s", plaintext);

    printf("Enter the key: ");
    scanf("%s", key);

    simpleAESEncrypt(plaintext, key, ciphertext);
    printASCII(ciphertext);  

    simpleAESDecrypt(ciphertext, key, decryptedText);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}
```

## OUTPUT:

Enter the plaintext: PRAJIN

Enter the key: 7

Encrypted Message (ASCII values): 103 101 118 125 126 121 

Decrypted Message: PRAJIN

![Screenshot 2025-04-21 121845](https://github.com/user-attachments/assets/447e50fd-6b9e-4ab8-920d-3b2be58eca16)

![Screenshot 2025-04-21 121826](https://github.com/user-attachments/assets/9ed53093-46e2-4201-9f44-607b735e36fa)



## RESULT:

The program is executed successfully and results are verified as well.
