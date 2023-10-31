# Prac
#include <stdio.h>
#include<ctype.h>
int main() {
    char text[500], ch;
    int key, i;
    printf("Enter a message to encrypt: ");
    scanf("%s", text); 
    for (i = 0; text[i] != '\0'; ++i) {
        ch = text[i];
        if (isalnum(ch)) {
            if (islower(ch)) {
                ch = (ch - 'a' + 3) % 26 + 'a';
       }
            if (isupper(ch)) {
                ch = (ch - 'A' + 3) % 26 + 'A';
            }
            if (isdigit(ch)) {
                ch = (ch - '0' + 3) % 10 + '0';
            }
        }
        else {
            printf("Invalid Message");
        }
        text[i] = ch;
    }
    printf("Encrypted message: %s", text);
   return 0;
}
