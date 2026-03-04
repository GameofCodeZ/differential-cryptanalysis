# Differential Cryptanalysis of a Toy Block Cipher

## Introduction

Cryptography is essential for securing digital communication and protecting sensitive information. A secure cryptographic algorithm should resist various forms of cryptanalysis. One powerful technique used to analyze block ciphers is **Differential Cryptanalysis**, which studies how differences in plaintext inputs affect the differences in ciphertext outputs.

This project demonstrates differential cryptanalysis on a **toy block cipher** implemented using a simple **Substitution–Permutation Network (SPN)**. By analyzing how controlled differences in plaintext propagate through the cipher, we can observe statistical patterns in the resulting ciphertext differences.

The goal of this project is to illustrate how differential cryptanalysis can reveal weaknesses in poorly designed cryptographic algorithms.

---

## Objective

The main objectives of this project are:

- Implement a simple toy block cipher based on a substitution–permutation network.
- Generate pairs of plaintext inputs with a fixed difference.
- Encrypt both plaintexts using the toy cipher.
- Analyze the resulting ciphertext differences.
- Identify statistical biases that may indicate weaknesses in the cipher.

---

## Toy Cipher Design

The cipher implemented in this project is a simplified **Substitution–Permutation Network (SPN)** consisting of the following components:

### 1. Substitution Layer (S-box)
A nonlinear substitution box replaces input bits with different output bits to introduce confusion.

### 2. Permutation Layer
Bits are rearranged across positions to spread changes throughout the block, providing diffusion.

### 3. Key Mixing
The plaintext is combined with a secret key using an XOR operation.

### Cipher Structure

Plaintext  
↓  
XOR with Key  
↓  
Substitution (S-box)  
↓  
Permutation  
↓  
XOR with Key  
↓  
Ciphertext

Block size used in this experiment: **8 bits**

---

## Differential Cryptanalysis Method

Differential cryptanalysis analyzes how differences between two plaintext inputs propagate through the cipher.

Steps performed in this project:

1. Generate a random plaintext value.
2. Create a second plaintext with a fixed input difference.
3. Encrypt both plaintexts using the toy cipher.
4. Compute the ciphertext difference.
5. Repeat the process many times.
6. Count how frequently each ciphertext difference occurs.

If certain output differences occur more frequently than others, this indicates a **bias** that could be exploited by attackers.

---

## Experiment Setup

- Plaintext block size: **8 bits**
- Number of trials: **5000**
- Fixed plaintext difference applied using XOR
- Ciphertext differences recorded and analyzed

---

## Results

The experiment generates many plaintext pairs and analyzes the frequency distribution of ciphertext differences.

Example output:

Ciphertext Difference : Frequency

00000001 : 312  
00000110 : 498  
00001010 : 142  
00001111 : 623  

The frequency distribution reveals that some ciphertext differences occur more often than others, indicating a non-uniform distribution.

---

## Visualization

A bar chart is generated to visualize the frequency of ciphertext differences. If the cipher behaved like a perfectly random function, all differences would occur with roughly equal probability.

However, observable peaks in the graph indicate structural patterns that could be exploited through differential cryptanalysis.

---

## Technologies Used

- Python
- Google Colab / Jupyter Notebook
- Matplotlib for visualization

---

## Conclusion

This project demonstrates the basic principle of **differential cryptanalysis** using a simple toy block cipher. By analyzing how input differences affect output differences, it is possible to detect statistical biases in the cipher. Although the cipher used in this experiment is intentionally simplified, the same principles apply to real-world cryptographic analysis and highlight the importance of careful cipher design.

---

---
