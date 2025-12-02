# spn-linear-cryptanalysis

Linear cryptanalysis of a lightweight Substitution–Permutation Network (SPN) cipher.  
This repository contains a complete implementation of Matsui-style linear cryptanalysis against a toy 8-bit SPN cipher, including S-box analysis, key-recovery attacks, and a full academic report.

---

## Project Overview

Linear cryptanalysis exploits biased linear relations between plaintext, ciphertext, and intermediate cipher states.  
This project targets a simplified SPN cipher consisting of:

- 4-bit S-box (applied to two nibbles)
- XOR key addition per round
- Simple substitution–permutation structure
- Inverse S-box used for backward rounds

Given 256 plaintext–ciphertext pairs, the project performs:

1. Recovery of the last-round key **K₄**  
2. Recovery of the second-round key **K₃**  
3. Validation using linear bias analysis

The attack reconstructs the keys by exploiting deviations from uniform probability in the linear relation

`P3 ⊕ P5 ⊕ U*_2 ⊕ U*_6 = 0`

where `U*` are bits of the state after applying the inverse S-box in the final rounds.

---
