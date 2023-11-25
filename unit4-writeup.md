# Process Writeup
## Name: Xin Yan Huang
## Course: APCSA
## Period: 7
## Concept: Loops (UNIT 4)

### Context
I have finished Unit 4 of APCSA which was conditionals. I am now learning loops in Unit 4. Loops are a code of block that perform the same exact instructions until a condition prevents the loop from continuing to run. Loops are helpful because we don't have to write the same block of code repeatedly. There are three types of loops that I will be talking about today: `for loop`, `while loop`, and a nested loop.
### Overview
#### `while` Loop
`While` loops execute the block of code inside until the condition is not met.

Format of a `while` loop:
```java
while (/*condition inside*/){
    // code inside
}
```
Example of a `while` loop:
```java
int x = 0
while (x < 5){
    x++
}
```
The `while` loop has two components: the condition and the code that will be performed if executed. `While` loops are helpful when you don't know how many times you want the code to run.

#### `for` loop
`For` loops has four components: the initialization, condition, incrementation, and the code that will be performed if executed. Initialization is when the starting value of the loop variable gets set up and also runs on the first loop. The condition part is when the condition is evaluated to be either true or false. If false, the loop stops. If true, the code inside the for loop will be executed. Lastly, incrementation is next. Incrementation is when the loop variable is incremented by a certain number. However, this last part doesn't need to increment. The loop variable can be subtracted, multiplied, or divided by a number.

Format of a `for` loop:
```java
for (/*initialization; condition; incrementation*/){
    // code here
}
```
The initialization and condition part have to be followed by a semicolon (;) or there would be an error because the computer won't know what is going on.

Example of a `for` loop:
```java
for (int i = 0; i <= 10; i++){
  System.out.print(i + " ");
}
```
`For` loops are helpful when you do know the exact amount of times you want the code to run.

#### Nested Loops
Nested loops is a `for` loop inside a `for` loop.

Format of a nested `for` loop:
```java
for (/*initialization; condition; incrementation*/){
    // code here
    for (/*initialization; condition; incrementation*/){
        // code here
    }
}
```
The inner loop that is inside the outer loop should be indented for better readability. We start at the outer loop. If the outer loop is true the code for the outer loop if any, will be executed as well as the inner `for` loop. When the inner loop is done executing, incrementation at the outer loop occurs which restarts the outer loop getting executed.

### Challenges
I took the Unit 4 exam to check my ability to understand loops. I got a lot of questions wrong so, we are going over them to help me understand why the correct answer is the correct answer.

#### Question 2
<p align="center">
    <img src="/workspaces/apcsa/apcsa-writeups/writeup-images/apcsa-mistake-13.png" width="70%" height="70%">
</p>

#### Question 4
<p align="center">
    <img src="/workspaces/apcsa/apcsa-writeups/writeup-images/apcsa-mistake-14.png" width="70%" height="70%">
</p>

#### Question 16
<p align="center">
    <img src="/workspaces/apcsa/apcsa-writeups/writeup-images/apcsa-mistake-15.png" width="70%" height="70%">
</p>

I didn't have enough time to work on question 16. I quickly chose one of the options.

Since this is a `while` loop, the loop can run either once or multiple times. First, we look at the condition `x < 10 || (x % 4) != 0`. We can perform short circuit evaluation

#### Question 19
<p align="center">
    <img src="/workspaces/apcsa/apcsa-writeups/writeup-images/apcsa-mistake-16.png" width="70%" height="70%">
</p>

For this question, I did the calculations correct but I didn't pay enough attention to understand what `result = str.substring(index, index + 1) + result;` meant.

We see that `String str` is the original string and `String result` is the new string that will be formed. First, we look at the initialization. Integer `i` is being set equal to 0. Second, we have to evaluate the condition which is true because 0 is less than 6 (`str.length()`). Third, we look at the code that is inside the `for` loop. Integer `index` is being declared and set equal to this expression: `(i + 3) % str.length();`. Fourth, we have to calculate this expression to find out which letter will be added to `String result`. We start off with `(i + 3)`. Right now, `i` is equal to 0. 0 plus 3 equals 3. Now, we do `3 % str.length()`. 3 modulo 6 is 3 because there is 3 remaining. Fifth, we look into the next line. `String result` gets added by `str.substring(index,index + 1)` and `result`. Since `result` is added before `str.substring(index,index + 1)`, the previous letter will be pushed towards the back. We start at the third index because of 3 (i + 3) modulo 6. The next indices would be 4 and 5 which the letters are `l` and `t`. The output right now is `tlu`. When `i` is incremented to 3, the integer `index` will now be 0 because `(3 + 3) % str.length()` is 0. We know the next letters would be `e` and `s` because the `for` loop can only run 6 times according to the condition. The most current letter would be `s`. Now, `s` would be first since previous letters go towards the end of the string. The final output would be: `sertlu`.

A great tip that I got from my classmate is to execute the last condition before the condition evaluates to false. This would have save so much time.

The last condition that is true is when `5 is less than 6 (str.length())`. When we do calculations, `index` will be 2 because `(5 + 3)` equates to 8 and `8 % str.length()` equates to 2. The letter of the second index is `s`. Letter `s` would be the first letter of the string because the newer letters are closer to the front. There is only one option with letter `s` at the front. This is a brillant technique to tackle these types of problems.

#### Question 20
<p align="center">
    <img src="/workspaces/apcsa/apcsa-writeups/writeup-images/apcsa-mistake-17.png" width="70%" height="70%">
</p>

For this question, I read `sum *= a` as `sum *= b`. We are not multiplying `sum` by `b` everytime `b` increments.

We start off with `a` equal to 1. In the inner loop, `sum` will be multiplied by `a` three times. Integer `sum` will still be 1 since one times one equals to 1. Now, the inner loop doesn't get executed and `a` increments to 2. This time, the inner loop will only run two times. The `sum` will now be 4. In the first time, `sum` gets multiplied by 2 making `sum` equal to 2. In the second time, `sum` gets multiplied by 2 again making `sum` equal to 4. The inner loop doesn't run and `a` increments to 3. The inner loop will run 1 time since b is already at 3 and the loop doesn't run if `b` is greater than or equal to 4. Finally, `sum` will be multiplied by 3 making the `sum` equal to 12. Here is a more visual respresentation of what I am talking about:
``` java
a   b   sum
// when a = 1
1   1   1
    2   1
    3   1

// when a = 2
2   2   2
    3   4

// when a = 3
3   3   12
```

### Takeaways
* If applicable, start with the last possible condition that is true
* Truly understand what the line of code does before you try to find the answer
