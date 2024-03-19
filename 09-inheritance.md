# Process Writeup

## Name: Xin Yan Huang
## Course: APCSA
## Period: 7
## Concept: (UNIT 9)

### Context

### Challenges

#### Question 12
<p align="center">
<img src="writeup-images/apcsa-mistake-36.png" width="70%" height="70%">
</p>

#### Question 15
<p align="center">
<img src="writeup-images/apcsa-mistake-37.png" width="70%" height="70%">
</p>

#### Question 17
<p align="center">
<img src="writeup-images/apcsa-mistake-38.png" width="70%" height="70%">
</p>

Here is the hierarchy:
```
Thing (parent)
Cog (parent of Gear & child of Thing)
Gear (child of Gear)
```

Since `Thing` is the parent of `Cog`, the `Cog` class can access `Thing`'s public methods & variables with the `super` keyword. I thought `Cog` was `Gear`. The `Gear` class can't directly access `Thing`'s public methods and variables with the `super` keyword.

#### Question 19
<p align="center">
<img src="writeup-images/apcsa-mistake-39.png" width="70%" height="70%">
</p>

We have established that `me` is a Student object. `me` can't access the `yearsStudied()` method because the method is in the `Graduate` class. A parent class can't access

### Takeaways
*
