# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```

#include <stdio.h>

int main()
{
    int i, seed, key, plain[100], cipher[100], decrypt[100];
    int n;

    printf("Enter seed value: ");
    scanf("%d", &seed);

    printf("Enter number of characters: ");
    scanf("%d", &n);

    printf("Enter plaintext values (ASCII): ");
    for(i = 0; i < n; i++)
        scanf("%d", &plain[i]);

    printf("\nPseudo Random Numbers: ");
    for(i = 0; i < n; i++)
    {
        seed = (seed * 7 + 3) % 100;
        printf("%d ", seed);

        cipher[i] = plain[i] ^ seed;
    }

    printf("\nEncrypted text: ");
    for(i = 0; i < n; i++)
        printf("%c", cipher[i]);

    seed = 10;  // Original seed value
    printf("\nDecrypted text: ");
    for(i = 0; i < n; i++)
    {
        seed = (seed * 7 + 3) % 100;
        decrypt[i] = cipher[i] ^ seed;
        printf("%c", decrypt[i]);
    }

    return 0;
}

```
# OUTPUT:
<img width="922" height="337" alt="image" src="https://github.com/user-attachments/assets/0536f00d-67d5-4b24-8bb9-06a0ab9a60ec" />

# RESULT:
Thus, the pseudo random numbers were generated and used for encryption and decryption successfully.

