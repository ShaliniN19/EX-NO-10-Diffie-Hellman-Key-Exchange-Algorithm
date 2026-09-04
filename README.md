# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm
## NAME: SHALINI N
## REG NO: 212224040305

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:

```
#include <stdio.h>

long long powerMod(long long base, long long exponent, long long modulus)
{
    long long result = 1;

    while (exponent > 0)
    {
        result = (result * base) % modulus;
        exponent--;
    }

    return result;
}

int main()
{
    long long p, g, a, b;
    long long publicA, publicB;
    long long secretA, secretB;

    printf("Enter prime number (p): ");
    scanf("%lld", &p);

    printf("Enter primitive root (g): ");
    scanf("%lld", &g);

    printf("Enter private key of Alice: ");
    scanf("%lld", &a);

    printf("Enter private key of Bob: ");
    scanf("%lld", &b);

    publicA = powerMod(g, a, p);
    publicB = powerMod(g, b, p);

    secretA = powerMod(publicB, a, p);
    secretB = powerMod(publicA, b, p);

    printf("\nPublic key of Alice: %lld", publicA);
    printf("\nPublic key of Bob: %lld", publicB);
    printf("\nShared secret key calculated by Alice: %lld", secretA);
    printf("\nShared secret key calculated by Bob: %lld", secretB);

    if (secretA == secretB)
        printf("\nKey Exchange Successful!\n");
    else
        printf("\nKey Exchange Failed!\n");

    return 0;
}
```


## Output:

<img width="1398" height="678" alt="image" src="https://github.com/user-attachments/assets/4546fb9d-96fb-4571-b90d-8a31019b09cf" />



## Result:
  The program is executed successfully

