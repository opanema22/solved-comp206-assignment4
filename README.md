Download Link: https://assignmentchef.com/product/solved-comp206-assignment4
<br>



<strong>Ex. 1 —    A Simple Interger Calculator </strong>

In this exercise, you will create a C program to implement a simple integer calculator.

Your calculator should accept three arguments as input, x, op, y, where x and y are integers and op is one of the operators +, -, *, / to perform the corresponding arithmetic operations.

1.Use vi to create a C program source file simplecalc.c

2.The program should include a comment section at the beginning that describes its purpose (couple of lines), the author (your name), your department, a small “history” section indicating what changes you did on what date.

<h1>/∗ ∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗ ∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗</h1>

<em>Program to           implement a simple            calculator</em>

<em>∗ Author                            Dept .                                     Date                             Notes</em>

<em>∗ Joseph D Comp. Science . Feb 10 2020 I n i t i a l version . </em><em>∗ Joseph D Comp. Science . Feb 11 2020 Added error handling .</em>

<h1>∗/</h1>

The code should be properly indented for readability as well as contain any additional comments required to understand the program logic.

3.The source code should be compilable by (exactly) using the command gcc -o simplecalc simplecalc.c

4.<strong> </strong>Your program should accept the three arguments mentioned above as its input. If the user does not pass this argument, you should display an error message and terminate with error code 1.

$ ./simplecalc

Error: usage is simplecalc &lt;x&gt; &lt;op&gt; &lt;y&gt;

$ echo $?

5.<strong> </strong>Your program performs simple arithmetic operations on the input as indicated by the operator and displays the output. You should use a switch statement to decide which operator to execute. You will loose 2 points if you do not use the switch. If the user enters one of the operators not listed above, print an error message and terminate with error code 2. Successfull execution of the program should result in a return code of 0 from the program.

$ ./simplecalc 5 + 3

8

$ echo $?

0

$ ./simplecalc 5 – 3

2

$ ./simplecalc 5 * 3

15

$ ./simplecalc 5 / 3

1

$ ./simplecalc 5 @ 3

@ not a valid operator

$ echo $?

2

<strong>Ex. 2 —                         A C Program to implement Caesar’s Cipher(11 Points)</strong>

In this exercise, you will create a C program to implement a basic version of Caesar’s cipher.

<a href="https://en.wikipedia.org/wiki/Caesar_cipher">https://en.wikipedia.org/wiki/Caesar_cipher</a>

The object of Caesar’s cipher is to replace each letter in the alphabet with another letter that is ‘X’ offset away from it to scramble the message.

For example consider the following sample output

$ ./caesarcipher 3 abcdefghijklmnopqrstuvwxyz defghijklmnopqrstuvwxyzabc

Here we asked the program to set an offset of 3, and typed the following line and pressed enter

$ ./caesarcipher 3 abcdefghijklmnopqrstuvwxyz

At which point, it changed each letter in the input line with the letter that is 3 letters to its right.

defghijklmnopqrstuvwxyzabc

As a result, a got replaced with d and so forth. Towards the end of the alphabets, you have to “wrap around”. In the above example, There is no alphabet 3 letters to the right of x, so it wrapped around to a and so forth. You can “decrypt” the message by running the program with the proper offset in the opposite direction, as shown below.

$ ./caesarcipher -3 defghijklmnopqrstuvwxyzabc abcdefghijklmnopqrstuvwxyz Here, we started with program with an offset -3 which asked the program to shift the letters to the left and the entered the original encrypted line.

$ ./caesarcipher -3

defghijklmnopqrstuvwxyzabc

To which it responded with the decrypted message.

abcdefghijklmnopqrstuvwxyz

1.Use vi to create a C program source file caesarcipher.c

2.<strong> </strong>The program should include a comment section at the beginning that describes its purpose (couple of lines), the author (your name), your department, a small “history” section indicating what changes you did on what date. The code should be properly indented for readability as well as contain any additional comments required to understand the program logic.

3.The source code should be compilable by (exactly) using the command gcc -o caesarcipher caesarcipher.c .

4.<strong> </strong>Your program should accept an integer argument as its option for the user to indicate the offset. If the user does not pass this argument, you should display an error message and terminate with error code 1.

$ ./caesarcipher

Error: usage is caesarcipher &lt;offset&gt;

$ echo $? 1

5.<strong> </strong>Your program should use the offset to shift the letters typed in a line either to the right.

$ ./caesarcipher 5 this is a secret message ymnx nx f xjhwjy rjxxflj

or to the left.

$ ./caesarcipher -5 this is a secret message ocdn dn v nzxmzo hznnvbz

6.<strong> </strong>The program should be able to read multiple lines, encrypting and displaying one line at a time, till it runs out of input/reaches EOF (can be simulated by pressing CTRL+D at the keyboard input in an empty line). If you are using the tester script, you shouldn’t have to do CTRL+D (if you do, there is an issue with your implementation). The program should terminate with return code 0 for any sucessfull execution.

$ ./caesarcipher 5 this is a secret message ymnx nx f xjhwjy rjxxflj delete after reading ijqjyj fkyjw wjfinsl

$ echo $?

0

7.<strong> </strong>The program should only encrypt lowercase english alphabets (a-z) and should merely print any other letters, numbers, white space characters, etc., as is.

$ ./caesarcipher 6

Hello there! How is COMP206?

Hkrru znkxk! Huc oy COMP206?