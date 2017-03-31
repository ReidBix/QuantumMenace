### Welcome to this Graduate Research Blog.
This is where our graduate research group will be posting any research related to our post-quantum analysis of TLS and SSL. In this blog we will be looking into various topics including post-quantum signatures, effects of quantum computing on TLS, benefits of switching to post-quantum algorithms, benefits of some post-quantum algorithms over others, and whatever other topics come up.
### Members
Reid Bixler (Researcher)

Collin Berman (Researcher)

David Evans (Professor/Advisor)

### Contact
If you have any questions or would like to contact us about the research, feel free to email anybody that is a part of the team: {rmb3yz, cmb5nh, evans}@virginia.edu

---
## What is the Quantum Menace?
### 3/31/2017

## Introduction to Post-Quantum Cryptography
[Introduction](http://pqcrypto.org/www.springer.com/cda/content/document/cda_downloaddocument/9783540887010-c1.pdf)
Quantum computers are dangerous. No, they're not going to evolve into the terminator and they're not going to cause the mystical singularity, but what they will do is give their owners and users the ability to break cryptography once considered secure.

Things such as RSA, DSA, and ECDSA rely on the difficulty of factoring large prime numbers and elliptic curves, both of which were once considered to be a hard problem to solve in polynomial time. The problem with quantum computing is that newly developed quantum algorithms such as Shor's Algorithm and Grover's Algorithm decrease the expected solution time to a reasonable polynomial time. What once would've taken longer than the age of the universe to solve may now take only a few days or even weeks. Considering the previous impossibility, there surely will exist entities willing to pay for the large time and monetary costs in order to break somebody else's system.

With the introduction of quantum computing, there surely must exist problems that are even too difficult for a quantum computer to solve. Luckily enough for many cryptographers out there, many current problems and cryptographic systems are 'quantum-resistant'.

-Hash-Based Cryptography
Examples inlcude the well-known Merkle hash-tree public-key signature system, which was built upon ideas of Lamport and Diffie.

-Code-Based Cryptography
McEliece's hidden-Goppa-code public-key encryption system is one of the few known examples of such a system.

-Lattice-Based Cryptography
These are reliant on the difficulty of solving for lattices which are used in a number of algorithms including: NTRU, Ring-LWE, or BLISS.

-Multi-variate-Quadratic-Equations Cryptography
An interesting cryptographic system relying on, surprise, multi-variate quadratic equations to protect a public-key, an example of which is Patarin's HFE-V public-key-signature system.

-Secret-Key Cryptography
The most well-known and widely used example of this would be the Daemen-Rijmen "Rijndael" cipher, otherwise named "AES" for the Advanced Encryption Standard.

### But Why Switch Now?

One of the biggest questions posed about quantum cryptography is why we need to switch over to these assumedly 'more secure' systems if even the best quantum computer out there at the moment can barely handle 10 qubits (with most breaks on RSA relying on multiple thousand). Why not simply switch over when the first sign of a quantum-attack comes along?

The problem with that is our current level of quantum cryptography is not good enough to be widely used, and a majority of systems reliant on these 'insecure' algorithms would find it very difficult to integrate quantum-resistant algorithms into their systems. Therefore there are three things that we need to consider.

1) We need to improve the efficiency of post-quantum cryptography.
2) We need time to build confidence in post-quantum cryptography.
3) We need time to improve the usability of post-quantum cryptography.

We in the security community never want to be caught off guard and are constantly trying to maintain the security of all of our communications, regardless of the required switches and changes to the systems, because the security and reliability of the system comes first. We may not ever end up needing these post-quantum cryptographic systems because a quantum computer capable of breaking RSA and DSA may never exist, but we as security researchers are not satisfied under such a strong assumption.

## Applications to TLS
[R-LWE in TLS](https://eprint.iacr.org/2014/599.pdf)
[NewHope](https://www.usenix.org/system/files/conference/usenixsecurity16/sec16_paper_alkim.pdf)

Specifically looking at SSL and TLS, there are already some existing research out there suggesting solutions to this 'Quantum Menace' for the TLS community. Things such as using Ring-LWE for post-quantum key exchange for the TLS protocol or an altered version of Ring-LWE known as BCNS which was proposed and modified in Google's own NewHope TLS research. But where do we come into this? What we have noticed in the TLS community is a severe need for 'future-proofing' the systems that we currently use. Yes, there do exist some researchers looking at potential solutions, but implementations of such systems have been rejected as being too insecure and unknown to risk putting into the new version of TLS v1.3.

We have noticed a distinct focus on very specific algorithms (mostly R-LWE), and not much analysis on the possibilities of the wide-range of post-quantum cryptographic systems. While R-LWE has some credibility to it, there has been signficant research improving and creating possibly better cryptographic systems that would maybe result in better integration into systems such as TLS. Because of this, our desire is to look at a number of quantum-secure algorithms to replace current protocols, and then present them alongside one another with the benefits and drawbacks of each, allowing for the security community to get a good idea of where the current post-quantum world is and where they can fit into the picture.

## Interesting Research Found

### BLISS, BLISS-B, and BLZZRD
[BLISS](https://eprint.iacr.org/2013/383.pdf)
[BLISS-B](https://eprint.iacr.org/2014/874.pdf)
[BLZZRD](https://eprint.iacr.org/2016/276.pdf)

One of our researchers has done some previous research along the lines of finding a fast, secure, and quantum-resistant algorithm to replace ECDSA in a system that requires small key sizes and fast key verifications. The solution found initially was BLISS, which relies on bimodal lattices with gaussians to create a signature scheme protected against quantum-attack. However, even further research has happened since the original paper was released in 2013, with improvements in speed and cache protection brought up in BLISS-B and BLZZRD respectively. While we are just mentioning these at the moment, they are being mentioned because of their relative low cost in key size compared to similar cryptographic systems. While TLS doesn't have limits on their key sizes, there are obvious drawbacks to having extremely large keys.

### PASS, PASS-2, and PASSign
[PASSign](https://eprint.iacr.org/2013/383.pdf)
Research has also been done on alternative quantum-resistant algorithms including the Partial Fourier Recovery Problem integrated into the PASS and PASS-2 algorithms. In 2013, research was done to create a practical post-quantum signature scheme known as PASSign, which relies on the hardness of recovering a ring element with small norm from an incomplete description of its Chinese remainder representation.

### Supersingular Isogeny Diffie-Hellman
[Intro to Supersingular Isogney Diffie-Hellman](http://csclub.uwaterloo.ca/~dburbani/work/friendlysidh.pdf)
Diffie-Hellman is also one of the algorithms that will be at risk once practical quantum computers become available. As an improvement, recent research suggests the applications of Isogenies and Supersingular Elliptic Curves to prevent the inherent break brought about through quantum computers. Diffie-Hellman, specifically ephemeral Diffie-Hellman (DHE), is used in the current versions of TLS and even the proposed new v1.3. While not considered insecure at the moment, we must begin to consider altering current standards or offer alternative solutions to existing ones for the possible case that quantum computers do become practical in the next few decades.

---
## Motivation
Collin and I are interested in post-quantum because of its relatively recent prominence in the computing world and the potentially drastic effects that it could have on the internet (more specifically secure connections through TLS and SSL).

We want to analyze a number of different algorithms that protect against post-quantum attacks and weigh the benefits and negatives of each in order to get a better grasp on the potential future of TLS. Our general purpose is going to be to determine how the TLS community can best protect against future quantum attacks and offer possible alternatives and options for such protection.


## Description
At the moment, we are planning to look at a number of different post-quantum capable algorithms and look at their costs for time, space, and security to weigh these algorithms against one another. We will be specifically looking into how TLS connections will be affected in each case as well as in the case that none of these changes are put into effect, with the worst possible case being completely broken TLS connections from quantum-attack.

## Other Sources
- [NewHope](https://eprint.iacr.org/2015/1092.pdf) : NewHope PostQuantum TLS Paper - Google's take on how to implement postquantum algorithms into TLS
- [Intro to Postquantum](http://pqcrypto.org/www.springer.com/cda/content/document/cda_downloaddocument/9783540887010-c1.pdf) : Introduction to PostQuantum - Why we need PQ cryptography, challenges that we may face, and general introduction to PQ</li>
- [PQCrypto](http://pqcrypto.org/) : PQCrypto.org - Great site for mining PQ sources and to get a good grasp of the current landscape for postquantum
- [BLISS](https://eprint.iacr.org/2013/383.pdf) : BLISS Paper - Bimodal Lattice Signature Scheme that was one of the best looking algorithms for postquantum in 2013
- [BLISS-B](https://eprint.iacr.org/2014/874.pdf) : BLISS-B Paper - Offers speed improvements on BLISS and other potential changes
- [BLZZRD](https://eprint.iacr.org/2016/276.pdf) : BLZZRD Paper - Offers cache protection for the Gaussians required for BLISS/BLISS-B, essentially further improved and secure BLISS-B