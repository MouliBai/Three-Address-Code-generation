# Three-Address-Code-generation(compute-language-compiler)
Three Address Code using lex and yacc

## This is a language developed for compiler design assignment.

*Has basic functionalities for number manipulation and boolean comparisons.

##### Main arithmetic operations.
##### Conditional statements.
##### Variables.
##### Printing the result.
##### Instructions.


## Main arithmetic operations.
> The main arithmetic operations available are +, -, *, /, %.


## Conditional statements.
> This programming language supports various conditional operations like <, >, ==. <=, >=.
It also supports assigning direct boolean values in the form of keywords 'True' and 'False'.


## Variables.
> The variables can be assigned from [a-z] and [A-Z]. The symbol table implementation involves
a simple symbol table of 52 rows. And a simple hashing algorithm to fill in according to the 
ascending value of the variables is used. There is only one data type, i.e integer.
The result of a conditional statement can also be stored inside a variable.


## Printing the result.
> The results can be print using the 'print' statement followed by an expression or an identifier.


## Instructions.
> Basically there are two scripts included remove.sh and complie.sh.
They contain the necessary codes for cleaning up and compiling the codes respectively.
The output or the intermediate code representation is generated to the file program.txt
and the result can be seen in the command line itself.


```
./remove.sh
./compile.sh
./calc<input.in

or 

___________TO COMPLIE___________

yacc -d first_cal.y
lex first_cal.l
gcc -g lex.yy.c y.tab.c -o calc
./calc<input.in 

cat program.txt

___________TO REMOVE___________

rm calc
rm lex.yy.c
rm y.tab.c
rm y.tab.h

> program.txt



```
> Inorder to run compile a program seperately, follow the instructions inside compile.sh. The result (Three address code) can be viewed inside the program.txt file. Compiling a program will only evaluate your program.


## Three address code generation.
> The three address code generation is maintained by using the following structure,
```
struct threeADD
{
	char result[10];
	char operand_1[10];
	char operand_2[10];
	char operator[10];
} quadraple[50];

```

## ##OUTPUT OF THE PROGRAM

##### Sample program
```
a=10+5/5+5+2*1 != 8;
b = 5%2;
c = a==b;
print c;
print 500;
```
##### Output (Evaluation)
```
1
500
```
##### Output (Three address code)
```
_k0 := 5 / 5
_k1 := 10 + _k0
_k2 := _k1 + 5
_k3 := 2 * 1
_k4 := _k2 + _k3
_k5 := _k4 != 8
a := _k5  
_k7 := 5 % 2
b := _k7  
_k9 := a == b
c := _k9
Cprint c
Cprint 500

```
