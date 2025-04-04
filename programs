Qn 1) The lexical analyzer should ignore redundant spaces, tabs, and new lines. It 
should also ignore comments. Although the syntax specification states that identifiers 
can be arbitrarily long, you may restrict the length to some reasonable value. Develop a 
lexical Analyzer to identify identifiers, constants, and operators using the C program. 
Code: 


#include <stdio.h> 
#include <ctype.h> 
#include <string.h> 
#define MAX_IDENTIFIER_LENGTH 31 
int isValidIdentifier(char *str) { 
if (!isalpha(str[0]) && str[0] != '_') return 0; 
for (int i = 1; str[i] != '\0'; i++) { 
if (!isalnum(str[i]) && str[i] != '_') return 0; 
} 
return 1; 
} 
int isOperator(char ch) { 
return (ch == '+' || ch == '-' || ch == '*' || ch == '/'); 
} 
void lexicalAnalyzer(char *code) { 
char token[100]; 
int index = 0; 
for (int i = 0; code[i] != '\0'; i++) { 
if (isalnum(code[i]) || code[i] == '_') { 
index = 0; 
while (isalnum(code[i]) || code[i] == '_') { 
token[index++] = code[i++]; 
} 
token[index] = '\0'; 
i--; 
if (isValidIdentifier(token)) { 
printf("Identifier: %s\n", token); 
} else { 
printf("Constant: %s\n", token); 
} 
} else if (isOperator(code[i])) { 
printf("Operator: %c\n", code[i]); 
} 
} 
} 
int main() { 
char code[] = "int a = 5; b = a + 2;"; 
lexicalAnalyzer(code); 
return 0; 
} 
 
Qn2) Extend the lexical Analyzer to Check comments, dened as follows in C: 
a) A comment begins with // and includes all characters until the end of that line. 
b) A comment begins with /* and includes all characters through the next occurrence of 
the character sequence */Develop a lexical Analyzer to identify whether a given line is a 
comment or not.



Code: 
#include <stdio.h> 
#include <string.h> 
int isComment(char *line) { 
if (strncmp(line, "//", 2) == 0) return 1; 
if (strncmp(line, "/*", 2) == 0) return 2; 
return 0; 
} 
void analyzeComments(char *code) { 
for (int i = 0; code[i] != '\0'; i++) { 
if (code[i] == '/' && code[i + 1] == '/') { 
printf("Single-line comment detected\n"); 
return; 
} 
if (code[i] == '/' && code[i + 1] == '*') { 
printf("Multi-line comment detected\n"); 
return; 
} 
} 
} 
int main() { 
char code[] = "/* This is a multi-line comment */\n// This is a single-line comment"; 
analyzeComments(code); 
return 0; 
}  

 
Qn3) Design a lexical Analyzer to validate operators to recognize the operators +,-,*,/ 
using regular Arithmetic operators . 


Code: 
#include <stdio.h> 
int isOperator(char ch) { 
return (ch == '+' || ch == '-' || ch == '*' || ch == '/'); 
} 
void analyzeOperators(char *code) { 
for (int i = 0; code[i] != '\0'; i++) { 
if (isOperator(code[i])) { 
printf("Operator: %c\n", code[i]); 
} 
} 
} 
int main() { 
char code[] = "a = b + c * d / e - f;"; 
analyzeOperators(code); 
return 0; 
} 
Output: 

 
Qn 4) Design a lexical Analyzer to find the number of whitespaces and newline 
characters. 



Code: 
#include <stdio.h> 
#include <ctype.h> 
void countWhitespaces(char *code) { 
int whitespaceCount = 0, newlineCount = 0; 
for (int i = 0; code[i] != '\0'; i++) { 
if (isspace(code[i])) { 
if (code[i] == '\n') newlineCount++; 
else whitespaceCount++; 
} 
} 
printf("Whitespaces: %d, Newlines: %d\n", whitespaceCount, newlineCount); 
} 
int main() { 
char code[] = "int a = 5; \n b = a + 2; \n"; 
countWhitespaces(code); 
return 0; 
} 



 
Qn 5) Develop a lexical Analyzer to test whether a given identifier is valid or not. 
Code: 

#include <stdio.h> 
#include <ctype.h> 
#include <string.h> 
int isValidIdentifier(char *str) { 
if (!isalpha(str[0]) && str[0] != '_') return 0; 
for (int i = 1; str[i] != '\0'; i++) { 
if (!isalnum(str[i]) && str[i] != '_') return 0; 
} 
return 1; 
} 
void checkIdentifier(char *identifier) { 
if (isValidIdentifier(identifier)) { 
printf("\"%s\" is a valid identifier.\n", identifier); 
} else { 
printf("\"%s\" is not a valid identifier.\n", identifier); 
} 
} 
int main() { 
char id1[] = "var_name"; 
char id2[] = "2ndVariable"; 
checkIdentifier(id1); 
checkIdentifier(id2); 
return 0; 
} 




 
1. Implement a C program to eliminate left recursion. 


Code: 
#include <stdio.h> 
#include <string.h> 
 
void eliminateLeftRecursion(char nonTerminal, char alpha[], char beta[]) { 
    printf("Grammar after eliminating left recursion:\n"); 
    printf("%c -> %s%c'\n", nonTerminal, beta, nonTerminal); 
    printf("%c' -> %s%c' | ε\n", nonTerminal, alpha, nonTerminal); 
} 
 
int main() { 
    char nonTerminal, alpha[10], beta[10]; 
    printf("Enter non-terminal: "); 
    scanf(" %c", &nonTerminal); 
    printf("Enter left-recursive production (A -> Aα | β):\n"); 
    printf("Enter α: "); 
    scanf("%s", alpha); 
    printf("Enter β: "); 
    scanf("%s", beta); 
    eliminateLeftRecursion(nonTerminal, alpha, beta); 
    return 0; 
} 




2. Implement a C program to eliminate left factoring. 
Code: 
#include <stdio.h> 
#include <string.h> 
void eliminateLeftFactoring(char nonTerminal, char common[], char alpha[], char beta[]) { 
printf("Grammar after eliminating left factoring:\n"); 
printf("%c -> %s%c'\n", nonTerminal, common, nonTerminal); 
printf("%c' -> %s | %s | ε\n", nonTerminal, alpha, beta); 
} 
int main() { 
char nonTerminal, common[10], alpha[10], beta[10]; 
printf("Enter non-terminal: "); 
scanf(" %c", &nonTerminal); 
printf("Enter common prefix: "); 
scanf("%s", common); 
printf("Enter α (remaining part of first production): "); 
scanf("%s", alpha); 
printf("Enter β (remaining part of second production): "); 
scanf("%s", beta); 
eliminateLeftFactoring(nonTerminal, common, alpha, beta); 
return 0; 
} 




3. Implement a C program to perform symbol table operations. 


Code: 
#include <stdio.h> 
#include <string.h> 
#define SIZE 10 
struct Symbol { 
char name[20]; 
char type[10]; 
} table[SIZE]; 
int count = 0; 
void insert() { 
if (count < SIZE) { 
printf("Enter symbol name: "); 
scanf("%s", table[count].name); 
printf("Enter type: "); 
scanf("%s", table[count].type); 
count++; 
printf("Symbol inserted successfully!\n"); 
} else { 
printf("Symbol table full!\n"); 
} 
} 
void search() { 
char name[20]; 
printf("Enter symbol name to search: "); 
scanf("%s", name); 
for (int i = 0; i < count; i++) { 
if (strcmp(table[i].name, name) == 0) { 
printf("Symbol found: %s, Type: %s\n", table[i].name, table[i].type); 
return; 
} 
} 
printf("Symbol not found!\n"); 
} 
void display() { 
printf("\nSymbol Table:\n"); 
printf("Name\tType\n"); 
for (int i = 0; i < count; i++) { 
printf("%s\t%s\n", table[i].name, table[i].type); 
} 
} 
int main() { 
int choice; 
while (1) { 
printf("\n1. Insert\n2. Search\n3. Display\n4. Exit\nEnter choice: "); 
scanf("%d", &choice); 
switch (choice) { 
case 1: insert(); break; 
case 2: search(); break; 
case 3: display(); break; 
case 4: return 0; 
default: printf("Invalid choice!\n"); 
} 
} 
} 





4. All languages have Grammar. When people frame a sentence we usually say whether 
the sentence is framed as per the rules of the Grammar or Not. Similarly use the same 
ideology , implement to check whether the given input string is satisfying the grammar 
or not . 


Code: 
(Sample Grammar: S -> aSb | ab) 
#include <stdio.h> 
#include <string.h> 
#include <ctype.h> 
int checkGrammar(char str[], int left, int right) { 
if (left > right) return 0;  
if (left == right - 1 && str[left] == 'a' && str[right] == 'b')  
return 1;  
if (str[left] == 'a' && str[right] == 'b')  
return checkGrammar(str, left + 1, right - 1);  
return 0;  
} 
int main() { 
char str[100]; 
printf("Enter the input string: "); 
scanf("%s", str); 
int len = strlen(str); 
if (checkGrammar(str, 0, len - 1)) 
printf("The string satisfies the grammar.\n"); 
else 
printf("The string does not satisfy the grammar.\n"); 
return 0; 
} 




5. Write a C program to construct recursive descent parsing. 


Code: 
{For production ex:  
E  → T E'   
E' → + T E' | ε   
T  → F T'   
T' → * F T' | ε   
F  → (E) | id} 
#include <stdio.h> 
#include <string.h> 
#include <ctype.h> 
char input[100]; 
int index = 0; 
void E(); 
void E_prime(); 
void T(); 
void T_prime(); 
void F(); 
void error() { 
printf("Error in parsing!\n"); 
exit(0); 
} 
void match(char expected) { 
if (input[index] == expected)  
index++; 
else  
error(); 
} 
void E() { 
T(); 
E_prime(); 
} 
void E_prime() { 
if (input[index] == '+') { 
match('+'); 
T(); 
E_prime(); 
} 
} 
void T() { 
F(); 
T_prime(); 
} 
void T_prime() { 
if (input[index] == '*') { 
match('*'); 
F(); 
T_prime(); 
} 
} 
void F() { 
if (input[index] == '(') { 
match('('); 
E(); 
match(')'); 
} else if (isalnum(input[index])) { 
match(input[index]);  
} else { 
error(); 
} 
} 
int main() { 
printf("Enter an expression: "); 
scanf("%s", input); 
E(); 
if (input[index] == '\0') 
printf("Parsing successful!\n"); 
else 
printf("Parsing failed!\n"); 
return 0; 
} 






                                  
1. In a class of Grade 3, Mathematics Teacher asked for the Acronym PEMDAS?. All of 
them are thinking for a while. A smart kid of the class Kishore of the class says it is 
Parentheses, Exponentiation, Multiplication, Division, Addition, Subtraction. Can you 
write a C Program to help the students to understand about the operator precedence 
parsing for an expression containing more than one operator, the order of evaluation 
depends on the order of operations. 



Code: 
#include <stdio.h> 
int main() { 
    int a = 5, b = 2, c = 3, d = 4; 
    int result; 
    printf("Given Expression: %d + %d * %d - %d / %d\n", a, b, c, d, b); 
    int step1 = b * c;    
    printf("Step 1: %d * %d = %d\n", b, c, step1); 
 
    int step2 = d / b;    
    printf("Step 2: %d / %d = %d\n", d, b, step2); 
 
    int step3 = a + step1;  
    printf("Step 3: %d + %d = %d\n", a, step1, step3); 
    result = step3 - step2;  
    printf("Step 4: %d - %d = %d\n", step3, step2, result); 
    printf("Final Result: %d\n", result); 
    return 0; 
} 





2. The main function of the Intermediate code generation is producing three address 
code statements for a given input expression. The three address codes help in 
determining the sequence in which operations are actioned by the compiler. The key 
work of Intermediate code generators is to simplify the process of Code Generator. 
Write a C Program to Generate the Three address code representation for the given 
input statement. 



Code: 
#include <stdio.h> 
int tempVar = 1;   
void generateTAC(char op, char arg1[], char arg2[], char result[]) { 
printf("%s = %s %c %s\n", result, arg1, op, arg2); 
} 
int main() { 
char expr[] = "a + b * c - d";  
char t1[] = "T1", t2[] = "T2", t3[] = "T3"; 
printf("Given Expression: %s\n", expr); 
printf("Three Address Code Representation:\n"); 
generateTAC('*', "b", "c", t1);  // T1 = b * c 
generateTAC('+', "a", t1, t2);   // T2 = a + T1 
generateTAC('-', t2, "d", t3);   // T3 = T2 – d 
printf("Final Result stored in: %s\n", t3); 
return 0; 





3. Write a C program for implementing a Lexical Analyzer to Count the number of 
characters, words, and lines . 




Code: 
#include <stdio.h> 
int main() { 
char ch; 
int characters = 0, words = 0, lines = 0; 
char lastChar = ' '; 
printf("Enter text (Press Ctrl + D to stop input in Linux/Mac or Ctrl + Z in Windows):\n"); 
while ((ch = getchar()) != EOF) { 
characters++;  
if (ch == '\n') 
lines++;  
if ((ch == ' ' || ch == '\n' || ch == '\t') && (lastChar != ' ' && lastChar != '\n' && lastChar != '\t')) { 
words++; 
} 
lastChar = ch;  
} 
if (lastChar != ' ' && lastChar != '\n' && lastChar != '\t') 
words++; 
printf("\nLexical Analysis:\n"); 
printf("Characters: %d\n", characters); 
printf("Words: %d\n", words); 
printf("Lines: %d\n", lines); 
return 0; 
} 




4. Write a C Program for code optimization to eliminate common subexpression. 


Code: 
#include <stdio.h> 
int main() { 
int a = 5, b = 3, c = 2, x, y, z; 
x = (a * b) + (a * b);   
y = (b + c) * (a * b);   
z = (a * b) + c;         
printf("Before Optimization:\n"); 
printf("x = (a * b) + (a * b) = %d\n", x); 
printf("y = (b + c) * (a * b) = %d\n", y); 
printf("z = (a * b) + c = %d\n", z); 
int temp = a * b; 
x = temp + temp; 
y = (b + c) * temp; 
z = temp + c; 
printf("\nAfter Optimization:\n"); 
printf("x = temp + temp = %d\n", x); 
printf("y = (b + c) * temp = %d\n", y); 
printf("z = temp + c = %d\n", z); 
return 0; 
} 




5. Write a C program to implement the back end of the compiler. 


Code: 
#include <stdio.h> 
#include <string.h> 
void generateAssembly(char op, char arg1[], char arg2[], char result[]) { 
switch (op) { 
case '+': printf("MOV R1, %s\nADD R1, %s\nMOV %s, R1\n", arg1, arg2, result); break; 
case '-': printf("MOV R1, %s\nSUB R1, %s\nMOV %s, R1\n", arg1, arg2, result); break; 
case '*': printf("MOV R1, %s\nMUL R1, %s\nMOV %s, R1\n", arg1, arg2, result); break; 
case '/': printf("MOV R1, %s\nDIV R1, %s\nMOV %s, R1\n", arg1, arg2, result); break; 
default: printf("Invalid Operation\n"); 
} 
} 
int main() { 
char result[] = "T1"; 
char arg1[] = "b"; 
char arg2[] = "c"; 
char op = '+'; 
printf("Three Address Code (TAC):\n"); 
printf("%s = %s %c %s\n", result, arg1, op, arg2); 
printf("\nGenerated Assembly Code:\n"); 
generateAssembly(op, arg1, arg2, result); 
return 0; 
} 







1. The lexical analyzer should ignore redundant spaces, tabs and new lines. It should 
also ignore comments. Although the syntax specification states that identifiers can be 
arbitrarily long, you may restrict the length to some reasonable value. Write a LEX 
specification file to take input C program from a .c file and count the number of 
characters, number of lines & number of words.

Input Source Program: (sample1.c)  
#include <stdio.h>  
int main()   
{      
int number1, number2, sum;  
printf("Enter two integers: ");  
scanf("%d %d", &number1, &number2);  
sum = number1 + number2;        
printf("%d + %d = %d", number1, number2, sum);  
return 0;  
} 


Code (Lex): 
%{ 
int nchar, nword, nline; 
%} 
%% 
\n { nline++; nchar++; } 
[^ \t\n]+ { nword++, nchar += yyleng; } 
. { nchar++; } 
%% 
int yywrap(void) { 
return 1; 
} 
int main(int argc, char *argv[]) { 
yyin = fopen(argv[1], "r"); 
yylex(); 
printf("Number of characters = %d\n", nchar); 
printf("Number of words = %d\n", nword); 
printf("Number of lines = %d\n", nline); 
fclose(yyin); 
} 



2. Write a LEX program to print all the constants in the given C source program file. 


Input Source Program: (sample2.c) 
#define PI 3.14    
#include<stdio.h>  
#include<conio.h>  
void main()  
{  
int a,b,c = 30;  
printf("hello");  
} 


Code (Lex): 
%{ 
#include<stdio.h> 
#include<stdlib.h> 
%} 
digit     [0-9] 
number    {digit}+    
floatnum  {digit}+\.({digit}+)? 
string    
%% 
\"([^\"]|\\\")*\" 
{number}   { printf("Integer constant: %s\n", yytext); } 
{floatnum} { printf("Floating-point constant: %s\n", yytext); } 
{string}   { printf("String constant: %s\n", yytext); } 
.          { /* Ignore other characters */ } 
%% 
int main(int argc, char *argv[]) { 
if(argc != 2) { 
printf("Usage: %s <filename>\n", argv[0]); 
return 1; 
} 
FILE *file = fopen(argv[1], "r"); 
if (!file) { 
printf("Error opening file: %s\n", argv[1]); 
return 1; 
} 
yyin = file; 
yylex(); 
fclose(file); 
return 0; 
} 
int yywrap() { 
return 1; 
} 



3. Write a LEX program to count the number of Macros defined and header files 
included in the C program. 


Input Source Program: (sample3.c) 
#define PI 3.14     
#include<stdio.h>   
#include<conio.h>  
void main()  
{  
int a,b,c = 30;  
printf("hello");  
} 



Code (Lex): 
%{ 
#include<stdio.h> 
#include<stdlib.h> 
int macro_count = 0, header_count = 0; 
%} 
macro    
\#define[ ]+[a-zA-Z_][a-zA-Z0-9_]* 
header   \#include[ ]+<[^>]+> 
%% 
{macro}   { macro_count++; } 
{header}  { header_count++; } 
.         { /* Ignore other characters */ } 
%% 
int main(int argc, char *argv[]) { 
if(argc != 2) { 
printf("Usage: %s <filename>\n", argv[0]); 
return 1; 
} 
FILE *file = fopen(argv[1], "r"); 
if (!file) { 
printf("Error opening file: %s\n", argv[1]); 
return 1; 
} 
yyin = file; 
yylex(); 
fclose(file); 
printf("Number of Macros: %d\n", macro_count); 
printf("Number of Header files: %d\n", header_count); 
return 0; 
} 
int yywrap() { 
return 1; 
} 




4. Write a LEX program to print all HTML tags in the input file.  



Input Source Program: (sample4.html)  
<html>  
<body>  
<h1>My First Heading</h1>  
<p>My first paragraph.</p>  
</body>  
</html> 



Code (Lex): 
%{  
int tags;  
%}  
%%  
"<"[^>]*>  { tags++; printf("%s \n", yytext); }  
.|\n { }  
%%  
int yywrap(void) {  
return 1; }  
int main(void)  
{  
FILE *f;  
char file[10];  
printf("Enter File Name : ");  
scanf("%s",file);  
f = fopen(file,"r");  
yyin = f;  
yylex();  
printf("\n Number of html tags: %d",tags);  
fclose(yyin);    
} 




5. Write a LEX program which adds line numbers to the given C program file and 
display the same in the standard output. 



Input Source Program: (sample5.c)  
#define PI 3.14     
#include<stdio.h>   
#include<conio.h>  
void main()  
{  
int a,b,c = 30;  
printf("hello");  
} 



Code (Lex): 
%{  
int yylineno;  
%}  
%%  
^(.*)\n printf("%4d\t%s", ++yylineno, yytext);  
%%  
int yywrap(void) {  
return 1;  
}  
int main(int argc, char *argv[]) {  
yyin = fopen(argv[1], "r");  
yylex();  
fclose(yyin);  
} 







1. Write a LEX specification file to take input C program from a .c file and count the number of 
characters, number of lines & number of words.  


Input Source Program: (sample5.c)    
#include <stdio.h>    
int main()     
{        
int number1, number2, sum;    
printf("Enter two integers: ");    
scanf("%d %d", &number1, &number2);    
sum = number1 + number2;          
printf("%d + %d = %d", number1, number2, sum);    
return 0;    
}   


Code (Lex):   
%{   
int nchar, nword, nline;   
%}   
%%   
\n { nline++; nchar++; }   
[^ \t\n]+ { nword++, nchar += yyleng; }   
. { nchar++; }   
%%   
int yywrap(void) {   
return 1;   
}   
int main(int argc, char *argv[]) {   
yyin = fopen(argv[1], "r");   
yylex();   
printf("Number of characters = %d\n", nchar);   
printf("Number of words = %d\n", nword);   
printf("Number of lines = %d\n", nline);   
fclose(yyin);   
}  




2. Write a LEX program to count the number of comment lines in a given C program and 
eliminate them and write into another file.  



Input Source File: (sample6.c)   
#include<stdio.h>    
int main()   
{   
int a,b,c; /varible declaration/   
printf(“enter two numbers”);   
scanf(“%d %d”,&a,&b);   
c=a+b;//adding two numbers   
printf(“sum is %d”,c);   
return 0;   
}  



Code (Lex):  
%{   
int com=0;   
%}   
%s COMMENT   
%%   
"/*" {BEGIN COMMENT;}   
<COMMENT>"*/" {BEGIN 0; com++;}   
<COMMENT>\n {com++;}   
<COMMENT>. {;}   
\/\/.* {; com++;}   
.|\n {fprintf(yyout,"%s",yytext);}   
%%   
void main(int argc, char *argv[])   
{   
if(argc!=3)   
{   
printf("usage : a.exe input.c output.c\n");   
exit(0);   
}   
yyin=fopen(argv[1],"r");   
yyout=fopen(argv[2],"w");   
yylex();   
printf("\n number of comments are = %d\n",com);   
}   
int yywrap()   
{   
return 1;   
}  
 





3. Write a LEX program to identify the capital words from the given input. 



Code (Lex):  
%%   
;   
[A-Z]+[\t\n ] { printf("%s is a capital word\n",yytext); }   
.    
%%   
int main( )    
{   
printf("Enter String :\n");   
yylex();   
}   
int yywrap( )   
{   
return 1;   
}  






4. Write a LEX Program to check the email address is valid or not.  


Code (Lex):  
%{  
#include <stdio.h>  
#include <string.h>  
%}  
%%  
[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,} { printf("Valid email: %s\n", yytext); }  
. ;  
%%  
int main() {  
printf("Enter email address: \n");  
yylex();  
return 0;  
}  
int yywrap() {  
return 1;  
}  




5. Write a LEX Program to convert the substring abc to ABC from the given input string. 



Code (Lex):  
%{  
#include <stdio.h>  
%}  
%%  
abc { printf("ABC"); }  
.   { printf("%s", yytext); }  
%%  
int main() {  
printf("Enter text: \n");  
yylex();  
return 0;  
}  
int yywrap() {  
return 1;  
}  




6. The Company ABC runs with employees with several departments. The Organization 
manager had all the mobile numbers of employees. Assume that you are the manager and need 
to verify the valid mobile numbers because there may be some invalid numbers present. 
Implement a LEX program to check whether the mobile number is valid or not. 




Code (Lex): 
%%  
[1-9][0-9]{9} {printf("\nMobile Number Valid\n");}  
.+ {printf("\nMobile Number Invalid\n");}  
%%  
int main()  
{  
printf("\nEnter Mobile Number : ");  
yylex();  
printf("\n");  
return 0;  
}  
int yywrap()  
{ } 




7. Implement Lexical Analyzer using LEX or FLEX (Fast Lexical Analyzer).  The program 
should separate the tokens in the given C program and display with appropriate caption. 


Input Source Program: (sample7.c)  
#include<stdio.h>   
void main()  
{  
int a,b,c = 30;   
printf("hello");  
} 



Code (Lex): 
digit [0-9]  
letter [A-Za-z]  
%{  
int count_id,count_key;  
%}  
%%  
(stdio.h|conio.h) { printf("%s is a standard library\n",yytext); }  
(include|void|main|printf|int) { printf("%s is a keyword\n",yytext); count_key++; }  
{letter}({letter}|{digit})*  { printf("%s is a identifier\n", yytext); count_id++; }  
{digit}+  { printf("%s is a number\n", yytext); }  
\"(\\.|[^"\\])*\"  { printf("%s is a string literal\n", yytext); }  
.|\n {  }  
%%  
int yywrap(void) {  
return 1;  
}  
int main(int argc, char *argv[]) {  
yyin = fopen(argv[1], "r");  
yylex();  
printf("number of identifiers = %d\n", count_id);  
printf("number of keywords = %d\n", count_key);  
fclose(yyin);  
} 





8. In a class, an English teacher was teaching the vowels and consonants to the students. She 
says “Vowel sounds allow the air to flow freely, causing the chin to drop noticeably, whilst 
consonant sounds are produced by restricting the air flow”. As a class activity the students are 
asked to identify the vowels and consonants in the given word/sentence and count the number of 
elements in each. Write an algorithm to help the student to count the number of vowels and 
consonants in the given sentence. 


Code (Lex): 
%{  
int vow_count=0;  
int const_count =0;  
%}  
%%  
[aeiouAEIOU] {vow_count++;}  
[a-zA-Z] {const_count++;}  
%%  
int yywrap(){}  
int main()  
{  
}  
printf("Enter the string of vowels and consonants:");  
yylex();  
printf("Number of vowels are:  %d\n", vow_count);  
printf("Number of consonants are:  %d\n", const_count);  
return 0;  




9. Keywords are predefined, reserved words used in programming that have special meanings to 
the compiler. Keywords are part of the syntax and they cannot be used as an identifier. In 
general there are 32 keywords. The prime function of Lexical Analyser is token Generation. 
Among the 6 types of tokens, differentiating Keyword and Identifier is a challenging issue. Thus 
write a LEX program to separate keywords and identifiers. 


Input Source File(sample8.c): 
#include<stdio.h>   
void main()  
{  
int a,b,c = 30;   
printf("hello");  
} 




Code (Lex): 
digit [0-9]  
letter [A-Za-z]  
%{  
int count_id,count_key;  
%}  
%%  
(stdio.h|conio.h) { printf("%s is a standard library\n",yytext); }  
(include|void|main|printf|int) { printf("%s is a keyword\n",yytext); count_key++; }  
{letter}({letter}|{digit})*  { printf("%s is a identifier\n", yytext); count_id++; }  
{digit}+  { printf("%s is a number\n", yytext); }  
\"(\\.|[^"\\])*\"  { printf("%s is a string literal\n", yytext); }  
.|\n {  }  
%%  
int yywrap(void) {  
return 1;  
}  
int main(int argc, char *argv[]) {  
yyin = fopen(argv[1], "r");  
yylex();  
printf("number of identifiers = %d\n", count_id);  
printf("number of keywords = %d\n", count_key);  
fclose(yyin);  
} 





10. Write a LEX program to recognise numbers and words in a statement. Pooja is a small girl 
of age 3 always fond of games. Due to the pandemic, she was not allowed to play outside. So her 
mother designs a gaming event by showing a flash card. Pooja has to separate the numbers in 
one list and words in another list shown in the flash card. 



Code (Lex): 
%{ 
#include <stdio.h> 
#include <stdlib.h> 
#include <ctype.h> 
int words = 0, numbers = 0; 
%} 
%% 
[0-9]+ {  
printf("NUMBER: %s\n", yytext); 
numbers++; 
} 
[a-zA-Z]+ {  
printf("WORD: %s\n", yytext); 
words++; 
} 
[ \t\n] ;  /* Ignore whitespace */ 
. ;  /* Ignore other characters */ 
%% 
int main() { 
printf("Enter a statement:\n"); 
yylex(); 
printf("\nTotal Words: %d\n", words); 
printf("Total Numbers: %d\n", numbers); 
return 0; 
} 
int yywrap() { 
return 1; 
} 





1. Write a LEX program to identify and count positive and negative numbers. 




Code (Lex): 
%{ 
#include <stdio.h> 
int pos_count = 0, neg_count = 0; 
%} 
%% 
[+-]?[0-9]+(\.[0-9]+)? { 
    if(yytext[0] == '-')  
        neg_count++; 
    else  
        pos_count++; 
} 
\n  { printf("Positive Numbers: %d\nNegative Numbers: %d\n", pos_count, neg_count); } 
.   ;  
%% 
int main() { 
    printf("Enter numbers (Ctrl+D to stop):\n"); 
    yylex(); 
    return 0; 
} 
int yywrap() { 
    return 1; 
} 
 




2. A networking company wants to validate the URL for their clients. Write a LEX program to 
implement the same. 



Code (Lex): 
%%  
((http)|(ftp))s?:\/\/[a-zA-Z0-9](.[a-z])+(.[a-zA-Z0-9+=?]) {printf("\nURL Valid\n");}  
.+ {printf("\nURL Invalid\n");}  
%%  
void main()  
{  
printf("\nEnter URL : ");  
yylex();  
printf("\n");  
}  
int yywrap()  
{  
} 






3. School management wants to validate DOB of all students. Write a LEX program to  
implement it. 




Code (Lex): 
%{ 
#include <stdio.h> 
%} 
%% 
((0[1-9])|([1-2][0-9])|(3[0-1]))\/((0[1-9])|(1[0-2]))\/(19[0-9]{2}|2[0-9]{3}) { 
printf("Valid DoB: %s\n", yytext); 
} 
.* { 
printf("Invalid DoB: %s\n", yytext); 
} 
%% 
int main() { 
printf("Enter DOB (DD/MM/YYYY) to validate (Ctrl+D to stop):\n"); 
yylex(); 
return 0; 
} 
int yywrap() { 
return 1; 
} 





4. Write a LEX program to check whether the given input is digit or not. 




Code (Lex): 
%{ 
#include <stdio.h> 
%} 
%% 
[0-9]+ { printf("\nValid digit\n"); } 
.* { printf("\nInvalid digit\n"); } 
%% 
int yywrap() {  
return 1;  
} 
int main() {  
printf("Enter input (Ctrl+D to stop):\n"); 
yylex();  
return 0;  
} 





5. A School student was asked to do basic mathematical operations. Implement a LEX program 
to implement the same. 



Code (Lex): 
%{ 
#include <stdio.h> 
#include <stdlib.h> 
#undef yywrap 
#define yywrap() 1   
int f1 = 0, f2 = 0; 
char oper; 
float op1 = 0, op2 = 0, ans = 0; 
void eval();  
%} 
DIGIT [0-9] 
NUM {DIGIT}+(\.{DIGIT}+)? 
OP [*/+-] 
%% 
{NUM} {  
if (f1 == 0) {  
op1 = atof(yytext);  
f1 = 1;  
} else {  
op2 = atof(yytext);  
f2 = 1;  
} 
} 
{OP} {  
oper = yytext[0];  
} 
\n {  
if (f1 && f2) { 
eval();  
printf("Result: %.2f\n", ans); 
f1 = f2 = 0; // Reset for next input 
} 
} 
%% 
void eval() { 
switch(oper) { 
case '+': ans = op1 + op2; break; 
case '-': ans = op1 - op2; break; 
case '*': ans = op1 * op2; break; 
case '/':  
if (op2 != 0)  
ans = op1 / op2;  
else  
printf("Error: Division by zero\n");  
break; 
default:  
printf("Invalid operator\n"); 
} 
} 
int main() { 
printf("Enter arithmetic expression (e.g., 5 + 3). Press Enter to evaluate:\n"); 
yylex(); 
return 0; 
} 





6. Write a LEX program to accept string starting with vowel. 



Code (Lex): 
%{ 
#include <stdio.h> 
%} 
%% 
^[AEIOUaeiou][a-zA-Z]* { printf("Valid String: %s\n", yytext); } 
.* { printf("Invalid String: %s\n", yytext); } 
%% 
int main() { 
printf("Enter a string (Ctrl+D to stop):\n"); 
yylex(); 
return 0; 
} 
int yywrap() { 
return 1; 
} 









7. Write a LEX program to find the length of the longest word. 



Code (Lex): 
%{ 
#include <stdio.h> 
#include <string.h> 
int max_length = 0; 
char longest_word[100]; // Assuming words won't exceed 100 characters 
%} 
%% 
[a-zA-Z]+ { 
int len = strlen(yytext); 
if (len > max_length) { 
max_length = len; 
strcpy(longest_word, yytext); 
} 
} 
[^a-zA-Z]+ { /* Ignore non-word characters */ } 
%% 
int main() { 
printf("Enter text (Ctrl+D to stop):\n"); 
yylex(); 
printf("Longest Word: %s (Length: %d)\n", longest_word, max_length); 
return 0; 
} 
int yywrap() { 
return 1; 
} 






8. Write a LEX program to count the frequency of the given word in a given sentence. 



Code (Lex): 
%{ 
#include <stdio.h> 
#include <string.h> 
int count = 0; 
char target[100];  // Word to search for 
%} 
%% 
[a-zA-Z]+ {  
if (strcmp(yytext, target) == 0) {  
count++;  
} 
} 
.|\n { /* Ignore other characters */ } 
%% 
int main() { 
printf("Enter the word to search: "); 
scanf("%s", target);   
printf("Enter the sentence (Ctrl+D to stop):\n"); 
yylex();   
printf("The word '%s' appears %d times.\n", target, count); 
return 0; 
} 
int yywrap() { 
return 1; 
} 







9. Write a LEX code to replace a word with another word in a file. 




Code (Lex): 
%{ 
#include <stdio.h> 
#include <string.h> 
char old_word[100], new_word[100]; // Words for replacement 
%} 
%% 
[a-zA-Z]+ {  
if (strcmp(yytext, old_word) == 0) {  
printf("%s", new_word);  // Replace old word with new word 
} else { 
printf("%s", yytext); // Print the word as it is 
} 
} 
. { printf("%c", yytext[0]); } // Print other characters (punctuation, spaces, etc.) 
%% 
int main() { 
printf("Enter the word to be replaced: "); 
scanf("%s", old_word); 
printf("Enter the new word: "); 
scanf("%s", new_word); 
printf("Enter the file content (Ctrl+D to stop):\n"); 
yylex(); // Process the file 
return 0; 
} 
int yywrap() { 
return 1; 
} 





10. Write a LEX program to recognize a word and relational operator. 



Code (Lex): 
%{ 
#include <stdio.h> 
%} 
%% 
[a-zA-Z_][a-zA-Z0-9_]* { printf("Word: %s\n", yytext); } 
(<=|>=|==|!=|<|>) { printf("Relational Operator: %s\n", yytext); } 
[ \t\n] { /* Ignore whitespace */ } 
. { printf("Other: %s\n", yytext); } // Print other symbols if needed 
%% 
int main() { 
printf("Enter input (Ctrl+D to stop):\n"); 
yylex(); 
return 0; 
} 
int yywrap() { 
return 1; 
}
