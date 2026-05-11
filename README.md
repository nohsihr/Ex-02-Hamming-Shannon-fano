# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Software Required:
  Google colab
# Theory
# Huffman coding:

Huffman coding works by assigning shorter codes to more frequently
occurring characters and longer codes to less frequent characters.

# Program:

```
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
# Calculation:

<img width="611" height="852" alt="image" src="https://github.com/user-attachments/assets/ff171c52-6d07-419b-99b8-82862e7d2851" />

<img width="652" height="888" alt="Screenshot 2026-02-08 180305" src="https://github.com/user-attachments/assets/6f8db3d2-09e0-4cd8-a41d-242f61add7ca" />

<img width="537" height="827" alt="image" src="https://github.com/user-attachments/assets/72ecb973-8348-4145-a62b-9d875c5f3b37" />


# Output

<img width="963" height="473" alt="Screenshot 2026-02-08 175020" src="https://github.com/user-attachments/assets/d30ebe49-d880-446b-ad4d-6e6b4d209bcd" />

# Results:
Huffman and Shannon-Fano coding methods were implemented on the provided source. Calculations for average codeword length, entropy, variance, redundancy, and coding efficiency have been carried out successfully and verified.
