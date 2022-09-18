# Probilities as the columns
heads (0) ;tails (1)

Probabilty of Single portion = 1/Summation of all portions
That will be in case ``1 : 4 ==> 1/5 ==> 0.20``
So respectively;
for 1 : 4 :: 0.20 : 0.80

The Total probaility should be 1 in case of a vector.

![image](https://user-images.githubusercontent.com/90497253/190912220-6c8e1d67-41a5-4d9f-b709-9768f4456836.png)

This is how it is done..

**Here coefficients (scalars) must satisfy certain properties:

1.Each coefficient is non-negative.

2.The summation of coefficients is 1.

## Creating a random probablistic State in-between range (1,101) using Python code.
```python

my_state = [0,0,0,0]
normalization_factor = 0 # this will be the summation of four values

# we pick for random values between 0 and 100
from random import randrange
while normalization_factor==0: # the normalization factor cannot be zero
    for i in range(4):
        my_state[i] = randrange(101) # pick a random value between 0 and (101-1)
        normalization_factor += my_state[i]
        
print("the random values before the normalization",my_state)

# normalize each value
for i in range(4): my_state[i] = my_state[i]/normalization_factor
    
print("the random values after the normalization",my_state)  

#  find their summation
sum = 0
for i in range(4): sum += my_state[i]

print("the summation is",sum)
```
