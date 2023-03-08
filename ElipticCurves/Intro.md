# Intro to ECC

* It is an approach to PUBLIC KEY CRYPTOGRAPHY!!!

### Resources

* https://en.wikipedia.org/wiki/Elliptic-curve_cryptography
* https://blog.cloudflare.com/a-relatively-easy-to-understand-primer-on-elliptic-curve-cryptography/
* https://avinetworks.com/glossary/elliptic-curve-cryptography/
* https://www.keyfactor.com/blog/elliptic-curve-cryptography-what-is-it-how-does-it-work/
* https://www.geeksforgeeks.org/blockchain-elliptic-curve-cryptography/


* NOT ADD : https://blog.boot.dev/cryptography/elliptic-curve-cryptography/

*********

### Overview

It provides a significantly more secure foundation than first generation public key cryptography systems like RSA.

* Elliptic curves are applicable for 
	* key agreement 
	* digital signatures 
	* pseudo-random generators


* Indirectly they are used for:  
	* Encription combined with ymmetric encryption scheme. 
	* Factorization algorithms


#### A bit of history

>The use of elliptic curves in cryptography was suggested independently by Neal Koblitz and Victor S. Miller in 1985. Elliptic curve cryptography algorithms entered wide use in 2004 to 2005.

* For later elliptic-curve-based protocols, the base assumption is that finding the discrete logarithm of a random elliptic curve element with respect to a publicly known base point is infeasible: this is the **"elliptic curve discrete logarithm problem" (ECDLP)**. 

* The security of elliptic curve cryptography depends on the ability to compute a point multiplication and the inability to compute the multiplicand given the original and product points. The size of the elliptic curve, measured by the total number of discrete integer pairs satisfying the curve equation, determines the difficulty of the problem.


### Famous EC or Cryptographic schemes


* ECDH: Diffie-Hellman for key exchange
* ECDSA: For Digital Signature. Eliptic Curve Digital Signature Algorithm.
* EdDSA: Edwards curve Digital Signature Algorithm is based on Schnorr signature and uses twisted Edwars curves.


Dato de color: 

>The U.S. National Security Agency (NSA) allows their use for protecting information classified up to top secret with 384-bit keys.


#### Comparative against RSA

>The primary benefit promised by elliptic curve cryptography is a smaller key size, reducing storage and transmission requirements,[6] i.e. that an elliptic curve group could provide the same level of security afforded by an RSA-based system with a large modulus and correspondingly larger key: for example, a 256-bit elliptic curve public key should provide comparable security to a 3072-bit RSA public key.

* It has a smaller key size and ability to manintain security

* ECC creates keys that are more difficult.

* The table below shows the sizes of keys needed to provide the same level of security.
	* Example: an ECC key of 384 bits == RSA of 7680 bits

```
RSA Key Length (bit)
1024
2048
3072
7680
15360

ECC Key Length (bit)
160
224
256
384
521
```

* ECC is quicker and use less memory than RSA

* RSA use both integers (prime numbers) for key generation, ECC the public key is a point on the curve, and the private key is an integer.

* ECC has smaller ciphertexts, keys, and signatures and faster generatios of keys and signatures.
* Lower latency 
* It computes signatures in two stages

* Size: it translates into more power for smaller, mobile devices.

Disadvantage of ECC:

* Uneasy to securely implement. 
* RSA is much more simpler. 
* Side channel attacks
* Twist security attacks


### Applications


* At CloudFlare, we make extensive use of ECC to secure everything from our customers' HTTPS connections to how we pass data between our data centers.


************************


### Theory

* A plain curve inside a finite field:

```
y^2 = x^3 + ax + b;
```

Components: 


1. ECC Keys: 

* Private key: private key creation is as simple as safely producing a random integer in a specific range. Any integer in the field represents a valid ECC private key.

* Public keys: EC points, which are pairs of integer coordinates x, and y that lie on a curve. 


2. Generator Point: Pre-defined EC point called generator point G (base point) for EC over finite fields, which can generate any other position in its subgroup over the eliptic curve by multiplying G from some integer in the range [0...r]


The number r is referred to as the "ordering" of the cyclic subgroup.

##### Properties

Horizontal symmetry: Any point on the curve can be reflected over the x axis and remain the same curve.

Any non-vertical line will intersect the curve in at most three places.

Any two points on a curve can be dotted together to get a new point.

Point addition: given two points P and Q on an elliptic curve, there is a third point R such that P + Q = R.

***

Trick: 

>It turns out that if you have two points, an initial point "dotted" with itself n times to arrive at a final point, finding out n when you only know the final point and the first point is hard.

* Elliptic curve cryptography is based on the discrete logarithm problem.

System definition: 

>An elliptic curve cryptosystem can be defined by picking a prime number as a maximum, a curve equation and a public point on the curve. A private key is a number priv, and a public key is the public point dotted with itself priv times. Computing the private key from the public key in this kind of cryptosystem is called the elliptic curve discrete logarithm function. This turns out to be the Trapdoor Function we were looking for.


### Usage in cryptography

* Elliptic curve cryptography typically relies on the Elliptic Curve Discrete Logarithm Problem (ECDLP), which states that it is hard to solve for x if we know y = g^x mod p where g is some known integer and p is prime. 

* Therefore, if we choose our parameters g and p carefully, it should be difficult for someone who doesn’t know the secret exponent x to compute x given y (or vice versa).


### Applications

* Diffie-Hellman: The basic public-key cryptosystem suggested for secret key sharing is the Diffie-Hellman protocol. If A (Alice) and B (Bob) initially agree on a given curve, field size, and mathematical type. They then distribute the secret key in the following manner. We can see that all we need to build the Diffie-Hellman protocol is scalar multiplication.

* ECDSA: ECC is one of the most widely utilized digital signature implementation approaches in cryptocurrencies. In order to sign transactions, both Bitcoin and Ethereum use the field inverse multiplication, but also arithmetic multiplication, inverse function, and modular operation.

* Online application: ECC is not limited to cryptocurrencies. It is an encryption standard that will be utilized by most online apps in the future due to its reduced key size and efficiency. Most commonly used in cryptocurrencies such as Bitcoin and Ethereum, along with single-way encryption of emails, data, and software.

* Blockchain Application: The cryptocurrency Bitcoin employs elliptic curve cryptography. Ethereum 2.0 makes heavy use of elliptic curve pairs with BLS signatures, as stated in the IETF proposed BLS specification, to cryptographically ensure that a specific Eth2 validator has really verified a specific transaction. 

>ECC allows resource-constrained systems like smartphones, embedded computers, and cryptocurrency networks to use ~10% of the storage space and bandwidth required by RSA.


















