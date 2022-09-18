# Playing with Matrixes
We need to actually make a function that takes probabilistic operator and a probabilistic state, and then returns the new probabilistic state i.e. `Simple Matrix Multiplication`.

Let's assume a situation: Some conditions are provided::
Probabilistic_Operators
whenever she gets a `head`, one euro is flipped;

whenever she gets a `tail`, one cent is flipped; and

Start with flipping one euro giving `head` from nowhere

![image](https://user-images.githubusercontent.com/90497253/190912821-7e784470-62be-4f3d-a8e4-df9e3b8feee3.png)

She starts with State 0; That is Head while State 1 represents Tail.

![image](https://user-images.githubusercontent.com/90497253/190912922-5752cfd6-3ab6-445f-b05a-89c8dffdcf9d.png)

Whole concept of Probablistic Operaters (explained through a single photograph)

## Stochastic Matrix
each entry non-negative; the summattion of each entry in each column is equal to 1.

## Transition probability
Finding transition probability from example `the second state to the third state` in a 3*3 Matrix is shown below.

It justs points to 3.2 element of the matrix 

## Function in Python
```python
def linear_evolve(operator,state):
    newstate=[]
    for i in range(len(operator)): # for each row
        # we calculate the corresponding entry of the new state
        newstate.append(0) # we set this value to 0 for the initialization
        for j in range(len(state)): # for each element in state
            newstate[i] = newstate[i] + operator[i][j] * state[j] # summation of pairwise multiplications
    return newstate # return the new probabilistic state
# Example shown below....
# operator for the test
B = [
    [0.4,0.6,0],
    [0.2,0.1,0.7],
    [0.4,0.3,0.3]
]

# state for test
v = [0.1,0.3,0.6]

newstate = linear_evolve(B,v)
print(newstate)
```
