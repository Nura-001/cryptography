
### CT #1: Practicing Number Theory

Name: Nurjahan Akter Student ID: It23045 Course: Cryptography (4115) Topic: Practicing Number Theory

### 1\. Introduction to Number Theory

Number Theory is a branch of mathematics that deals with integers and their properties. It plays an important role in cryptography because many encryption algorithms depend on prime numbers, modular arithmetic, GCD, and modular exponentiation.



### 2\. Divisibility

An integer `a` divides an integer `b` if there exists an integer `k` such that:

b=a\\times k

Notation:

a\\mid b

Example:

4\\mid 20

Because:

20=4\\times5

### 3\. Prime and Composite Numbers

Prime Number: A number greater than 1 that has exactly two positive divisors: 1 and itself.

Examples: 2, 3, 5, 7, 11, 13.

Composite Number: A number greater than 1 that has more than two positive divisors.

Examples: 4, 6, 8, 9, 10, 12.

Note: 0 and 1 are neither prime nor composite.

### 4\. Fundamental Theorem of Arithmetic

Every integer greater than 1 can be expressed uniquely as a product of prime numbers.

Example:

60=2^2\\times3\\times5

### 5\. Greatest Common Divisor (GCD)

GCD is the greatest positive integer that divides two or more integers without leaving a remainder.

Example:

GCD(24,36)=12

### Euclidean Algorithm

The Euclidean Algorithm is used to calculate the GCD of two integers.

Formula:

a=bq+r

Where:

* `a` = Dividend

* `b` = Divisor

* `q` = Quotient

* `r` = Remainder

Example: Find GCD(36, 24)

36=24\\times1+1224=12\\times2+0

Therefore:

GCD(36,24)=12

Python Code:

```python
def gcd(a, b):
    while b != 0:
        a, b = b, a % b
    return a

print(gcd(36, 24))
```

Output:

```text
12
```

### 6\. Least Common Multiple (LCM)

LCM is the smallest positive integer that is divisible by both given integers.

Formula:

LCM(a,b)=\\frac{|a\\times b|}{GCD(a,b)}

Example:

LCM(12,18)=36

Python Code:

```python
def lcm(a, b):
    if a == 0 or b == 0:
        return 0
    return abs(a*b)//gcd(a,b)

print(lcm(12,18))
```

Output:

```text
36
```

### 7\. Extended Euclidean Algorithm

The Extended Euclidean Algorithm calculates GCD and also finds two integers `x` and `y` satisfying:

ax+by=GCD(a,b)

This equation is known as Bézout's Identity.

Example:

30(-1)+18(2)=6

Therefore:

GCD(30,18)=6

Python Code:

```python
def extended_gcd(a, b):
    if b == 0:
        return a, 1, 0

    g, x1, y1 = extended_gcd(b, a % b)

    x = y1
    y = x1 - (a // b) * y1

    return g, x, y

print(extended_gcd(30,18))
```

### 8\. Modular Arithmetic

Modular arithmetic deals with the remainder after division by a positive integer called the modulus.

Notation:

a\\bmod n=r

Example:

17\\bmod5=2

Because 17 divided by 5 leaves a remainder of 2.

### Congruence

Two integers are congruent modulo `n` if their difference is divisible by `n`.

a\\equiv b\\pmod n

Example:

17\\equiv5\\pmod{12}

Because:

17-5=12

### Modular Arithmetic Operations

Addition:

(a+b)\\bmod n

Subtraction:

(a-b)\\bmod n

Multiplication:

(a\\times b)\\bmod n

Python Code:

```python
print((17+8)%5)
print((17-5)%12)
print((7*9)%11)
```

### 9\. Modular Multiplicative Inverse

The modular inverse of `a` modulo `n` is a number `x` satisfying:

a\\times x\\equiv1\\pmod n

A modular inverse exists if:

GCD(a,n)=1

Example:

3\\times5=1515\\bmod7=1

Therefore:

3^{-1}\\bmod7=5

Python Code:

```python
def mod_inverse(a, n):
    g, x, y = extended_gcd(a, n)

    if g != 1:
        return None

    return x % n

print(mod_inverse(3,7))
```

Output:

```text
5
```

### 10\. Modular Exponentiation

Modular exponentiation calculates the remainder of a large power.

Formula:

a^e\\bmod n

Example:

2^{10}\\bmod1000=24

### Fast Modular Exponentiation

Fast modular exponentiation uses the Square-and-Multiply method.

It reduces computational time from to modular multiplications.

Python Code:

```python
def fast_modular_power(base, exp, mod):
    result = 1
    base = base % mod

    while exp > 0:
        if exp % 2 == 1:
            result = (result * base) % mod

        base = (base * base) % mod
        exp = exp // 2

    return result

print(fast_modular_power(2,10,1000))
```

Output:

```text
24
```

### 11\. Euler's Totient Function

Euler's Totient Function, represented by , counts the number of positive integers less than or equal to `n` that are relatively prime to `n`.

Two numbers are relatively prime if their GCD is 1.

Formula for a prime number:

\\phi(p)=p-1

For two distinct prime numbers:

\\phi(pq)=(p-1)(q-1)

General formula:

\\phi(n)=n\\prod_{p\\mid n}\\left(1-\\frac1p\\right)

Example:

\\phi(9)=6

The numbers relatively prime to 9 are:

1, 2, 4, 5, 7, 8.

Python Code:

```python
def euler_phi(n):
    result = n
    p = 2

    while p*p <= n:
        if n % p == 0:
            while n % p == 0:
                n //= p
            result -= result // p
        p += 1

    if n > 1:
        result -= result // n

    return result

print(euler_phi(9))
```

Output:

```text
6
```

### 12\. Fermat's Little Theorem

Fermat's Little Theorem states that if `p` is a prime number and `a` is not divisible by `p`, then:

a^{p-1}\\equiv1\\pmod p

Example:

2^6=6464\\bmod7=1

Therefore:

2^6\\equiv1\\pmod7

Python Code:

```python
a = 2
p = 7

print(pow(a, p-1, p))
```

Output:

```text
1
```

### 13\. Euler's Theorem

Euler's Theorem states that if:

GCD(a,n)=1

Then:

a^{\\phi(n)}\\equiv1\\pmod n

Example:

\\phi(10)=43^4=8181\\bmod10=1

Therefore:

3^4\\equiv1\\pmod{10}

Relationship: Fermat's Little Theorem is a special case of Euler's Theorem when the modulus is prime.

### 14\. Chinese Remainder Theorem (CRT)

The Chinese Remainder Theorem is used to solve a system of simultaneous modular equations.

Example:

x\\equiv2\\pmod3x\\equiv3\\pmod5

The solution is:

x=8

Verification:

8\\bmod3=28\\bmod5=3

Therefore, the answer is 8 modulo 15.

Python Code:

```python
def crt(r1, m1, r2, m2):
    k = ((r2-r1) * mod_inverse(m1,m2)) % m2
    return (r1 + m1*k) % (m1*m2)

print(crt(2,3,3,5))
```

Output:

```text
8
```

### 15\. Prime Number Checking

A prime number has exactly two positive divisors.

We can check primality by testing divisors up to the square root of the number.

Python Code:

```python
def is_prime(n):
    if n < 2:
        return False

    for i in range(2, int(n**0.5)+1):
        if n % i == 0:
            return False

    return True

print(is_prime(17))
print(is_prime(21))
```

Output:

```text
True
False
```

### 16\. Sieve of Eratosthenes

The Sieve of Eratosthenes is an efficient algorithm for finding all prime numbers up to a given limit.

Python Code:

```python
def sieve(n):
    prime = [True] * (n+1)
    prime[0] = prime[1] = False

    for i in range(2, int(n**0.5)+1):
        if prime[i]:
            for j in range(i*i, n+1, i):
                prime[j] = False

    return [i for i in range(2,n+1) if prime[i]]

print(sieve(30))
```

Output:

```text
[2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```

### 17\. Application of Number Theory in Cryptography: RSA

RSA is a public-key cryptographic algorithm based on number theory.

It uses two keys:

* Public Key: Used for encryption.

* Private Key: Used for decryption.

### RSA Key Generation Steps

Step 1: Select two distinct prime numbers.

p=61,\\quad q=53

Step 2: Calculate:

n=p\\times q=3233

Step 3: Calculate Euler's Totient Function.

\\phi(n)=(p-1)(q-1)\\phi(n)=60\\times52=3120

Step 4: Select public exponent `e`.

e=17

Such that:

GCD(e,\\phi(n))=1

Step 5: Calculate private exponent `d`.

d=e^{-1}\\bmod\\phi(n)d=2753

### RSA Encryption

C=M^e\\bmod n

### RSA Decryption

M=C^d\\bmod n

Python Code:

```python
p = 61
q = 53

n = p*q
phi = (p-1)*(q-1)

e = 17
d = pow(e, -1, phi)

message = 65

cipher = pow(message, e, n)
decrypted = pow(cipher, d, n)

print("Public Key:", (n,e))
print("Private Key:", (n,d))
print("Encrypted:", cipher)
print("Decrypted:", decrypted)
```

Note: Small prime numbers are used only for educational demonstrations. Real RSA requires appropriately large keys and secure implementation.

### 18\. Important Python Functions

| Function   | Purpose                |
| ---------- | ---------------------- |
| abs()      | Returns absolute value |
| %          | Calculates remainder   |
| //         | Integer division       |
| pow(a,b)   | Calculates power       |
| pow(a,b,m) | Modular exponentiation |
| range()    | Generates a sequence   |
| int()      | Converts to integer    |
| print()    | Displays output        |

### 19\. Practice Questions

* Find GCD(252, 105).

* Find LCM(18, 24).

* Apply the Extended Euclidean Algorithm to 35 and 15.

* Calculate .

* Check whether .

* Find the modular inverse of 7 modulo 26.

* Does the modular inverse of 12 modulo 18 exist?

* Calculate .

* Find , , and .

* Verify Fermat's Little Theorem for .

* Verify Euler's Theorem for .

* Solve the following using CRT:

x\\equiv1\\pmod4x\\equiv3\\pmod5

* Generate all prime numbers up to 100.

* Implement RSA encryption and decryption using Python.

### 20\. Conclusion

Number Theory is the mathematical foundation of modern cryptography. Concepts such as prime numbers, GCD, modular arithmetic, modular inverse, Euler's Totient Function, and modular exponentiation are essential for understanding cryptographic algorithms.

By practicing these mathematical concepts and implementing them in Python using Jupyter Notebook or Google Colab, we can understand how cryptographic algorithms work internally.

### References

* [Number Theory and Cryptography Workshop — GitHub](https://github.com/mnp-club/Number_Theory_and_Cryptography_Workshop?utm_source=chatgpt.com)

* [Python Official Documentation](https://docs.python.org/3/?utm_source=chatgpt.com)

* [Python Modular Exponentiation — pow()](https://docs.python.org/3/library/functions.html?utm_source=chatgpt.com#pow)

End of CT #1 Notes
