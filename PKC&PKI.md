# Public Key Cryptography (Asymmetric cryptography)

### Resources

* https://en.wikipedia.org/wiki/Public-key_cryptography

***************


### A bit of history

* 1977: Both RSA and Diffie-Hellman key exchange algorithm were introduced. **Security based on theory of numbers**. 

* They were able to enable secure communication between two parties without a shared secret.

* Early public-key systems based their security on the assumption that it is difficult to factor a large integer composed of two or more large prime factors.

* For later elliptic-curve-based protocols, the base assumption is that finding the discrete logarithm of a random elliptic curve element with respect to a publicly known base point is infeasible: this is the **"elliptic curve discrete logarithm problem" (ECDLP)**. 

* The security of elliptic curve cryptography depends on the ability to compute a point multiplication and the inability to compute the multiplicand given the original and product points. The size of the elliptic curve, measured by the total number of discrete integer pairs satisfying the curve equation, determines the difficulty of the problem.


>Modern cryptography is founded on the idea that the key that you use to encrypt your data can be made public while the key that is used to to decrypt your data can be kept private.


Algorithms that are easy in one direction and hard the other are called **Trap door functions**. 


