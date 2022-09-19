# Probabilistic bits

In general, a probabilistic bit is in states 0 and 1 with probabilities  𝑝  and  1−𝑝 , where  𝑝  is a number between 0 and 1. Remark that if  𝑝=1  or  𝑝=0 , then the bit becomes deterministic.

![image](https://user-images.githubusercontent.com/90497253/190911504-60d0489d-1acf-45b0-bb43-cbe72790266e.png)

Matrix of 2 different unbaised coins

![image](https://user-images.githubusercontent.com/90497253/190911527-5276c5d1-52d9-4214-b46b-34016ea34b20.png)

Matrix of Same Coin tossed 2 times.

## NOTE
``In this case as we are using one euro coin and other cent
``

Convince yourself about the correctness of transitions given in the table.
Remark that there is no difference between getting heads from the one euro coin or from the one cent coin.
Therefore, one bit is enough to represent all transitions.

Python code to calculate probabilities seeing heads and tails after 10 OR 'n' coin tosses.
```python
prob_head = 1
prob_tail = 0

number_of_iterations = 10

for i in range(number_of_iterations):
    # the new probability of head is calculated by using the first row of table
    new_prob_head = prob_head * 0.6 + prob_tail * 0.3

    # the new probability of tail is calculated by using the second row of table
    new_prob_tail = prob_head * 0.4 + prob_tail * 0.7

    # update the probabilities
    prob_head = new_prob_head
    prob_tail = new_prob_tail
    # Similarly theses values are updated 'n' times in the loop.
    
# print prob_head and prob_tail
print("the probability of getting head after",number_of_iterations,"coin tosses is",prob_head)
print("the probability of getting tail after",number_of_iterations,"coin tosses is",prob_tail)
```
