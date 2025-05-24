## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.
## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)

## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


## PROGRAM :-

~~~
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main() {
 char message[100]; // Array to store the message
 int key;
 printf("Enter the message to encrypt: ");
 fgets(message, sizeof(message), stdin); // Read input from the user
 // Remove trailing newline from fgets
 message[strcspn(message, "\n")] = '\0';
 printf("Enter the Caesar Cipher key (an integer): ");
 scanf("%d", &key); // Read the key from the user
 // Encryption logic (directly in main)
 for (int i = 0; message[i] != '\0'; i++) {
 char c = message[i];
 if (c >= 'A' && c <= 'Z') {
 message[i] = ((c - 'A' + key) % 26 + 26) % 26 + 'A';
 } else if (c >= 'a' && c <= 'z') {
 message[i] = ((c - 'a' + key) % 26 + 26) % 26 + 'a';
 }
 }
 printf("Encrypted Message: %s\n", message);
 // Decryption logic (directly in main)
 for (int i = 0; message[i] != '\0'; i++) {
 char c = message[i];
 if (c >= 'A' && c <= 'Z') {
 message[i] = ((c - 'A' - key) % 26 + 26) % 26 + 'A';
 } else if (c >= 'a' && c <= 'z') {
 message[i] = ((c - 'a' - key) % 26 + 26) % 26 + 'a';
 }
 }
 printf("Decrypted Message: %s\n", message);
 return 0;
}
~~~

## OUTPUT :-

![447240152-2bbcf2d0-5f6a-4cbb-9470-2c8b61c9659e](https://github.com/user-attachments/assets/84ed54d1-95c8-4413-ab06-600bb2c60119)
## RESULT:
The program is executed successfully
