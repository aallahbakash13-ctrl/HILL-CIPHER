# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a python program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
key=[[17,17,5],[21,18,21],[2,2,19]]
invkey=[[4,9,15],[15,17,6],[24,0,17]]

text=input("Enter text:").upper()

while len(text)%3!=0:
    text+="X"

print("Simulation of Hill Cipher")
print("Padded message :",text)

encrypt=""
for i in range(0,len(text),3):
    p=[ord(text[i])-65,ord(text[i+1])-65,ord(text[i+2])-65]
    for j in range(3):
        s=0
        for k in range(3):
            s+=key[j][k]*p[k]
        encrypt+=chr((s%26)+65)

print("Encoded message :",encrypt)

decrypt=""
for i in range(0,len(encrypt),3):
    c=[ord(encrypt[i])-65,ord(encrypt[i+1])-65,ord(encrypt[i+2])-65]
    for j in range(3):
        s=0
        for k in range(3):
            s+=invkey[j][k]*c[k]
        decrypt+=chr((s%26)+65)

print("Decoded message :",decrypt)
```

## OUTPUT
<img width="1915" height="911" alt="Screenshot 2026-07-22 210255" src="https://github.com/user-attachments/assets/f3de63cd-4be2-40c4-bf6b-e3e18b5c61f8" />


## RESULT
The program is successfully verified and completed
