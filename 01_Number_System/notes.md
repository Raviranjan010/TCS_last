# Number System — Complete Notes

## 1. Classification of Numbers

| Type | Definition | Examples |
|------|-----------|---------|
| Natural Numbers (N) | Positive integers starting from 1 | 1, 2, 3, … |
| Whole Numbers (W) | Natural + zero | 0, 1, 2, … |
| Integers (Z) | All negative, zero, positive | …−2, −1, 0, 1, 2… |
| Rational | p/q form, q ≠ 0 | 3/4, 0.5, 7 |
| Irrational | Cannot be expressed as p/q | √2, π, e |
| Prime | Exactly 2 factors (1 and itself) | 2, 3, 5, 7, 11… |
| Composite | More than 2 factors | 4, 6, 8, 9… |
| Co-prime | GCD = 1 (not necessarily prime) | (8, 9), (14, 15) |

> **1 is neither prime nor composite.**

---

## 2. Divisibility Rules

| Divisor | Rule |
|---------|------|
| 2 | Last digit is 0, 2, 4, 6, 8 |
| 3 | Sum of digits divisible by 3 |
| 4 | Last 2 digits divisible by 4 |
| 5 | Last digit 0 or 5 |
| 6 | Divisible by both 2 and 3 |
| 7 | Double last digit, subtract from rest; check if result ÷ 7 |
| 8 | Last 3 digits divisible by 8 |
| 9 | Sum of digits divisible by 9 |
| 11 | (Sum of odd-position digits) − (Sum of even-position digits) = 0 or multiple of 11 |
| 12 | Divisible by both 3 and 4 |
| 25 | Last 2 digits divisible by 25 |

---

## 3. HCF and LCM

### Definitions
- **HCF (GCD)**: Largest number that divides all given numbers.
- **LCM**: Smallest number divisible by all given numbers.

### Key Relations
- HCF × LCM = Product of two numbers (**only for two numbers**)
- HCF of fractions = HCF of numerators / LCM of denominators
- LCM of fractions = LCM of numerators / HCF of denominators
- HCF always divides LCM.

### Why it works
- Any common factor must divide into HCF by definition. LCM is the least upper bound of the factor lattice.
- The product rule HCF × LCM = a × b holds for two numbers because every prime factor is counted exactly once between HCF and LCM.

### Methods
**Euclidean Algorithm for HCF**: HCF(a, b) = HCF(b, a mod b), repeat until remainder = 0.  
Example: HCF(48, 18) → HCF(18, 12) → HCF(12, 6) → HCF(6, 0) = **6**

---

## 4. Number of Factors

If N = 2^a × 3^b × 5^c × …  
**Total factors** = (a+1)(b+1)(c+1)…

**Sum of factors** = [(2^(a+1) − 1)/(2−1)] × [(3^(b+1) − 1)/(3−1)] × …

**Product of factors** = N^(number_of_factors / 2)

**Number of odd factors**: Set power of 2 to 0, then apply formula.  
**Number of even factors** = Total factors − Odd factors.

---

## 5. Remainders

### Basic Rules
- (a + b) mod m = [(a mod m) + (b mod m)] mod m
- (a × b) mod m = [(a mod m) × (b mod m)] mod m

### Fermat's Little Theorem
If p is prime and gcd(a, p) = 1:  
**a^(p−1) ≡ 1 (mod p)**

### Euler's Theorem (Generalization)
**a^φ(n) ≡ 1 (mod n)** when gcd(a, n) = 1  
φ(n) = Euler's totient function = n × ∏(1 − 1/p) for each prime p dividing n.

### Cyclicity of Remainders
Remainders of powers cycle. Find the cycle length, then use (power mod cycle_length) to find the required remainder.

### Remainder of a^n / (a−1) = 1 (always, if a > 1)
### Remainder of a^n / (a+1):
- If n is even: remainder = 1
- If n is odd: remainder = a

---

## 6. Unit Digits (Cyclicity)

| Base digit | Cycle | Cycle length |
|-----------|-------|-------------|
| 0 | 0 | 1 |
| 1 | 1 | 1 |
| 2 | 2,4,8,6 | 4 |
| 3 | 3,9,7,1 | 4 |
| 4 | 4,6 | 2 |
| 5 | 5 | 1 |
| 6 | 6 | 1 |
| 7 | 7,9,3,1 | 4 |
| 8 | 8,4,2,6 | 4 |
| 9 | 9,1 | 2 |

**Method**: Find (exponent mod cycle_length). If result = 0, use the last digit in the cycle.

---

## 7. TCS-Specific Patterns

1. **Remainder questions** using cyclicity or Euler's theorem appear in ~40% of Number System questions.
2. **HCF/LCM of fractions** — very frequently tested; students confuse numerator/denominator placement.
3. **Unit digit of large powers** — extremely common; usually 4–7 seconds if you know cycles.
4. **Finding the largest/smallest N-digit number divisible by k** — standard TCS trap.
5. **Number of trailing zeros** in n! — TCS tests this regularly.  
   Formula: floor(n/5) + floor(n/25) + floor(n/125) + …
6. **Divisibility by 7/11/13** — TCS sometimes gives tricky 6-digit numbers.
7. **Number of factors / perfect squares among factors** — medium-hard TCS Prime level.

---

## 8. Trailing Zeros in n!

Zeros come from factors of 10 = 2 × 5. Fives are limiting.  
Count of 5s = ⌊n/5⌋ + ⌊n/25⌋ + ⌊n/125⌋ + ⌊n/625⌋ + …

Example: 100! → 20 + 4 + 0 = **24 trailing zeros**.

---

## 9. Perfect Squares, Cubes

- Perfect square ⟹ all prime exponents are **even**.
- Perfect cube ⟹ all prime exponents are **multiples of 3**.
- Number of perfect squares ≤ N: **⌊√N⌋**
- Number of perfect cubes ≤ N: **⌊N^(1/3)⌋**

---

## 10. Sum of First n Natural Numbers and Variants

- 1 + 2 + … + n = n(n+1)/2
- 1² + 2² + … + n² = n(n+1)(2n+1)/6
- 1³ + 2³ + … + n³ = [n(n+1)/2]²
