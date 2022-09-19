# Coin System

## Fair Coin

If our coin is fair, then the probabilities of getting Heads and Tails are equal:
`
p = 0.5
`
## Simulating a FairCoin in Python in range of 100,1000,10000 & 100000 respectively.
```python
from random import randrange

for experiment in [100,1000,10000,100000]:
    heads = tails = 0
    for i in range(experiment):
        if randrange(2) == 0: heads = heads + 1
        else: tails = tails + 1
    print("experiment:",experiment)
    print("heads =",heads,"  tails = ",tails)
    print("the ratio of #heads/#tails is",(round(heads/tails,4)))
    
```
OUTPUT
```
experiment: 100
heads = 47   tails =  53
the ratio of #heads/#tails is 0.8868

experiment: 1000
heads = 477   tails =  523
the ratio of #heads/#tails is 0.912

experiment: 10000
heads = 4915   tails =  5085
the ratio of #heads/#tails is 0.9666

experiment: 100000
heads = 50144   tails =  49856
the ratio of #heads/#tails is 1.0058
```
## Biased Coin

## Simulating a Baisedcoin Python in range of 100,1000,10000 & 100000 respectively.
```python
from random import randrange

# let's pick a random number between {0,1,...,99}
# it is expected to be less than 60 with probability 0.6
# and greater than or equal to 60 with probability 0.4

for experiment in [100,1000,10000,100000]:
    heads = tails = 0
    for i in range(experiment):
        if randrange(100) <60: heads = heads + 1 # with probability 0.6, can be changed accordingly
        else: tails = tails + 1 # with probability 0.4
    print("experiment:",experiment)
    print("heads =",heads,"  tails = ",tails)
    print("the ratio of #heads/#tails is",(round(heads/tails,4)))
```
OUTPUT
```
experiment: 100
heads = 63   tails =  37
the ratio of #heads/#tails is 1.7027

experiment: 1000
heads = 579   tails =  421
the ratio of #heads/#tails is 1.3753

experiment: 10000
heads = 5973   tails =  4027
the ratio of #heads/#tails is 1.4832

experiment: 100000
heads = 60271   tails =  39729
the ratio of #heads/#tails is 1.5171
```
We can clearly see the difference.
## Doing the same using a function in Python.

```python
from random import randrange
N = 101
B = randrange(N+1)
def biased_coin(N,B):
    from random import randrange
    random_number = randrange(N)
    if random_number < B:
        return "Heads"
    else:
        return "Tails"
total_tosses = 500
the_number_of_heads = 0
for i in range(total_tosses):
    if biased_coin(N,B) == "Heads":
        the_number_of_heads = the_number_of_heads + 1

my_guess =  the_number_of_heads/total_tosses        
real_bias = B/N
error = abs(my_guess-real_bias)/real_bias*100 

print("my guess is",my_guess)
print("real bias is",real_bias)
print("error (%) is",error)
```



