# Process Writeup

## Name: Xin Yan Huang
## Course: APCSA
## Period: 7
## Concept: 2D-Arrays (UNIT 8)

### Context
Previously, I was working on ArrayLists which is similar to arrays. Now, I am working on Unit 8 of the APCSA cirriculmn which is 2D Array. 2D means 2 dimensional. 2D arrays are similar to a regular array. The difference is that 2D arrays are an array inside of an array. This is how you would initialize a 2D array: `int[][] nums = new int[2][3];`. While an array has one square bracket after the array type, a 2D array has two square brackets.

### Challenges

#### Question 9

<p align="center">
    <img src="writeup-images/apcsa-mistake-33.png" width="70%" height="70%">
</p>

For this question, the question is asking you to return `true` if all strings in the 2D array have the length of 3. There can't be a single `String` that doesn't have the length of 3 or otherwise, we return false.

When taking upon a closer look at all three options, I eliminated `III` first because you have to return a value outside of the `for()` loop. In addition, the line that says, `return result;`, is inside the first `for()` loop. Hypotethically, if the first row of elements all have the length of 3, they would return as `true`. However, the code doesn't take into consideration about the rest of the elements in other rows. When you return a value inside a `for()` loop, the `for()` loop stops executing. Now that we stopped the `for()` loop, the rest of the elements in the other rows could not have the length of 3 which could make the boolean spit out false information.

I was now down to two options, `I` and `II`. I didn't understand the question well enough at the time of taking the test. I thought that both options looked like they were inverses which mean the same thing. However, there is a difference. At option `I`, the inner `for()` loop would return `true` after the condition, `arr[j][k].length() == 3`, is true. This condition is like the same as the condition in option `III`. We would return `true` without knowing if all elements actually have the length of 3.

The only correct answer was option `II`. Since we are looking to see if all elements have the length of 3, we can just write code that returns `false` if only one element doesn't have the length of 3.

#### Question 18

<p align="center">
    <img src="writeup-images/apcsa-mistake-34.png" width="705" height="70%">
</p>

For this question, I just randomly guessed as I didn't have enough time to complete this question. I wish that I didn't spend more time on questions that I got very confused so that I can spend more time on questions that I could get correct if I had the time. I think this is a much more simplier question than the questions that I got wrong. The question is saying that we return the index of the coloumn that has the smallest value in the 2D array. My answer choice was definitely wrong as `currentVal` is suppose to hold the value of the specific element in the 2D array. In my case, `currentVal` holds the index of the row. The variable, `result`, is suppose to hold the index of the coloumn. However, the `result` in my answer choice holds the value of the element.

The correct is:
```java
if (mat[j][k] < currentVal)
{
  currentVal = mat[j][k];
  result = k;
}
```
The `currentVal` actually stores the value of the element so we can later compare the new `currentVal` to other element's value. The `result` actually holds the value of the index of the column. `result` is being stored by the information from `k` because `k` is the index of the column. `j` is the index of the row. This is because the outer `for()` loop loops through each row which has the variable `j`. The inner `for()` loop loops through each column which has the variable `k`.

#### Question 20

<p align="center">
    <img src="writeup-images/apcsa-mistake-35.png" width="70%" height="70%">
</p>

This question caught me off guard. I should have look into the answer choices more carefully but, it is hard trying to figure out the answer in a short period of time. I forgot that `num` was a `double` variable type. My answer choice was wrong because `mat[k][num]` meant `mat[int][double]`. This is incorrect as there are no indexes that are double meaning you can't have an index of 3.23. Indexes are always whole numbers (0, 1, 2, 3, etc). With this logic, we can eliminate the rest of the options that have `[num]` since this is incorrect syntax. The correct answer was:
```java
if (num < localMin)
{
  localMin = num;
}
```
On the line that says, `for (double num : mat[k])`, it means that we are in the kth row of nth column which is basically saying we are accessing an element from this column of that row. We don't need to call the element by saying `mat[k][#]` since we are accessing elements in a for-each loop. This means that we can eliminate any option that has `mat[k][num]` or `mat[num]` in the condition. This would leave us to only looking at the inside of the condition. The other option that has `localMin = mat[k][num]` would be incorrect as you can't have an index with a `double` (decimal) value.


### Takeaways
* Take time to read the question more carefully
* Put in a little extra time to make sure you get the question correct
* Spend more time on questions that have a higher chance of getting it correct