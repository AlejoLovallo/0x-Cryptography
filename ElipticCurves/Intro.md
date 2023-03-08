# Intro to ECC

* It is an approach to PUBLIC KEY CRYPTOGRAPHY!!!

### Resources

* https://en.wikipedia.org/wiki/Elliptic-curve_cryptography
* https://blog.cloudflare.com/a-relatively-easy-to-understand-primer-on-elliptic-curve-cryptography/

*********

### Overview

It provides a significantly more secure foundation than first generation public key cryptography systems like RSA.

* Elliptic curves are applicable for 
	* key agreement 
	* digital signatures 
	* pseudo-random generators


* Indirectamente se usan para: 
	* Encripción combinado con symmetric encryption scheme. 
	* Factorization algorithms


#### A bit of history

>The use of elliptic curves in cryptography was suggested independently by Neal Koblitz[7] and Victor S. Miller[8] in 1985. Elliptic curve cryptography algorithms entered wide use in 2004 to 2005.

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


### Applications


* At CloudFlare, we make extensive use of ECC to secure everything from our customers' HTTPS connections to how we pass data between our data centers.


************************


### Teoría

plain curve inside a finite field:

```
y^2 = x^3 + ax + b;
```



















