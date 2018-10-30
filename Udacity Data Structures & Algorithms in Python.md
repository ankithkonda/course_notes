### Notes from Udacity Data Structures & Algorithms in Python Course


#### Efficiency/Complexity
How well are you using your computer resources

Think of it as space + time  
time: "how long your code takes to run"  
space: "how much storage/memory does the code need"  

notation:  

Big O notation - O([algebraic expression])  

e.g. O(n), O(2n), O(log(n)) or O(1) == O(0n+1)

n = length of the input to the function

Calculate TIME effecieny example - 

```

1  function decode(input): 
2    create output string
3    for each letter in input
4      get new_letter from letter's location in cipher
5      add new_letter to output
5    return output 

```

`lines: 2, 5`  
Creating an output string and returning an output string only happens once.  
`O(2)`

`lines: 3`  
There needs to be a computation to get each letter for 1 iteration of the loop.  
`O(n + 2)`

`lines: 4, 5`  
Both lines inside the for loop need to run once for every letter in the input.
Since n is the length of the input and 2 is the number of times it needs to run    
`O(3n + 2)`

`lines: 3`  
To get the actual value of the letter from the cipher (assuming that the datastructure of the cipher is a list), we need to check all 26 possible on every letter (length of alphabet)  
`O(3n + 26n + 2)` -> `O(29n+2)`


So if input had 10 letters, then calculation is - 

```
O(2n+2)
n = 10
29n + 2 = y
y = 292
effeiency = y * time it takes for computer to run 1 line of code
```

Since the efficieny can be any of - `O(n + 2)` `O(3n + 2)` `O(29n+2)`

We can approxmiate it down to just `O(n)` - Some number of computations must be performed for EACH letter in the input.

If we look at the worst case (where a letter needs to be checked 26 times in the cipher) we get - `O(29n+2)`

average case - `O(16n+2)`

So for APPROXIMATION Regardless of the best case or average case, it's still going to resolve to Big O of n - `O(n)` in linear time


Calculate TIME effecieny example - 

For example if you need to copy the input string 3 times in the code, then its just -  
`O(3n)`
