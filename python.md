# Python
| [edit](https://github.com/eecsmap/eecsmap.github.io/edit/main/python.md) | [home](https://eecs.pro) | [Jupyter Note](https://github.com/eecsmap/eecsmap.github.io/blob/main/python.ipynb) | [download Jupyter note](https://eecs.pro/python.ipynb)

## Reading

### books
- [Problem Solving with Algorithms and Data Structures Using Python. Release 3.0 by Miller B.N., Ranum D.L. (z-lib.org).pdf](https://github.com/eecsmap/eecsmap.github.io/files/8311951/Problem.Solving.with.Algorithms.and.Data.Structures.Using.Python.Release.3.0.by.Miller.B.N.Ranum.D.L.z-lib.org.pdf)



### Simulate Probability Problem

```python3
# A is guilty, P(A) = 0.01
# B is detected, P(B|A) = 0.8, P(B|~A) = 0.1
# what is P(A|B)

import random

def simulate():
    is_guilty = random.random() < 0.01
    is_detected = random.random() < (0.8 if is_guilty else 0.1)
    return is_guilty, is_detected

n = 1000000
na = 0
nb = 0
nab = 0
for i in range(n):
    is_guilty, is_detected = simulate()
    if is_guilty: na += 1
    if is_detected: nb += 1
    if is_guilty and is_detected: nab += 1
print('P(A) = ', na / n)
print('P(B) = ', nb / n)
print('P(A|B) = ', nab / nb)
```
