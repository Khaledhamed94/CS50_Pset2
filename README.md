# CS50_Pset2

#include <stdio.h>
#include <cs50.h>
#include <stdlib.h> // for atoi
#include <string.h> // for strlen
#include <ctype.h>



int main(int argc, string argv[])
{
    if (argc == 2)
    {
        string key = argv[1] ;
        int i, j, k, n = 0;
        for(i = 0; i < strlen(key); i++)
        {
            j = key[i] ;
            if (!(isalpha(j)))
            {
                return 1;
            }
        }

        string plain = get_string("plaintext: ") ;
        printf("ciphertext: ") ;

        for(i = 0; i < strlen(plain); i++)
        {
            k = plain[i] ;
            if (n == strlen(key)) // for keywords less than plaintext
            {
                n = 0 ;
            }
            j = key[n] ;

            if (j > 64 && j < 91)  // for making A = 0 , B = 1 , etc
            {
                j = j - 65 ;
            }

            else if (j > 96 && j < 123)  // for making a = 0 , b = 1 , etc
            {
                j = j - 97 ;
            }

            if (k > 64 && k < 91) // enciphering Capital Letters
            {
                k = k + j;
                if (k > 90) // for returning from Z to A
                {
                    k = (k - 90) + 65 ;
                    printf("%c", k) ;
                }

                else
                {
                     printf("%c", k) ;
                }

                n++ ;
            }

            else if (k > 96 && k < 123)  // enciphering lower Letters
            {
                k = k + j;
                if (k > 122)  // for returning from z to a
                {
                    k = (k - 122) + 97 ;
                    printf("%c", k) ;
                }

                else
                {
                    printf("%c", k) ;
                }

                n++ ;
            }

            else
            {
                printf("%c", k);
            }
        }

        printf("\n");

    }

    else
    {
        return 1;
    }
}
