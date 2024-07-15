# simpleLang-code

This compiler takes SimpleLang code as input and translates it into assembly code for an 8-bit CPU. The compile function parses the SimpleLang code and emits corresponding assembly instructions based on the operations specified in the code. In this example, the SimpleLang code LOAD A, ADD B, STORE C is translated into assembly code as LDA A, ADD B, STA C.

#include <stdio.h>  
#include <string.h>  

void compile(char* code)  
{  
    char* token = strtok(code, " ");  
    
    while(token != NULL)  
    {  
        if(strcmp(token, "LOAD") == 0)  
        {  
            printf("LDA %s\n", strtok(NULL, " "));  
        }  
        else if(strcmp(token, "STORE") == 0)  
        {  
            printf("STA %s\n", strtok(NULL, " "));  
        }  
        else if(strcmp(token, "ADD") == 0)  
        {  
            printf("ADD %s\n", strtok(NULL, " "));  
        }  
        else if(strcmp(token, "SUB") == 0)  
        {  
            printf("SUB %s\n", strtok(NULL, " "));  
        }  
        
        token = strtok(NULL, " ");  
    }  
}  

int main()  
{  
    char code[] = "LOAD A\nADD B\nSTORE C\n";  
    
    compile(code);  
    
    return 0;  
}
