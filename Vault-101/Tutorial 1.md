#CSE222 
## Problem 1
## n-stack game
This game is one-player, to be played by you. You will be given n tiles stacked on each other in a column (so that the height of the stack is n). The game move for you is as follows : break a stack of height at least 2 into two stacks. Whenever you make this move, you get a score equal to the product of the heights of the two new stacks.
 The game ends when all the stacks are of height 1. Question: Prove that no matter what moves you make over the course of the game, your total score will be the same
### Solution

$Claim$:  P(n) = n(n-1)/2 

$Proof$:
We will prove this using strong induction

$Base\,Case$
SIze of stack  = 1;
Score is 0;
Max score with stack of size k  = P(k)
Let P(k) be tr
Now, Consider P(k).
$P(k) = (k-x)*x + P(k-x).P(x)$ where x < k

Now, 
$P(k+1) =(a)*(b)+a(a-1)/2 +b(b-1)/2$
$P(k+1) =(2ab+a(a-1))/2 +(2ab+(b(b-1))/2$
![[Pasted image 20210302174104.png]]

 Therefore, P(k) is true
 
 
 
