### Welcome to this Graduate Research Blog.
This is where our graduate research group will be posting any research related to our post-quantum analysis of TLS and SSL. In this blog we will be looking into various topics including post-quantum signatures, effects of quantum computing on TLS, benefits of switching to post-quantum algorithms, benefits of some post-quantum algorithms over others, and whatever other topics come up.
### Members
Reid Bixler (Researcher)

Collin Berman (Researcher)

David Evans (Professor/Advisor)

### Contact
If you have any questions or would like to contact us about the research, feel free to email anybody that is a part of the team: {rmb3yz, cmb5nh, evans}@virginia.edu

---
## Motivation
Collin and I are interested in post-quantum because of its relatively recent prominence in the computing world and the potentially drastic effects that it could have on the internet (more specifically secure connections through TLS and SSL).

We want to analyze a number of different algorithms that protect against post-quantum attacks and weigh the benefits and negatives of each in order to get a better grasp on the potential future of TLS. Our general purpose is going to be to determine how the TLS community can best protect against future quantum attacks and offer possible alternatives and options for such protection.


## Description
At the moment, we are planning to look at a number of different post-quantum capable algorithms and look at their costs for time, space, and security to weigh these algorithms against one another. We will be specifically looking into how TLS connections will be affected in each case as well as in the case that none of these changes are put into effect, with the worst possible case being completely broken TLS connections from quantum-attack.

## Other Sources
- https://eprint.iacr.org/2015/1092.pdf : NewHope PostQuantum TLS Paper - Google's take on how to implement postquantum algorithms into TLS
- http://pqcrypto.org/www.springer.com/cda/content/document/cda_downloaddocument/9783540887010-c1.pdf : Introduction to PostQuantum - Why we need PQ cryptography, challenges that we may face, and general introduction to PQ</li>
- http://pqcrypto.org/ : PQCrypto.org - Great site for mining PQ sources and to get a good grasp of the current landscape for postquantum
- https://eprint.iacr.org/2013/383.pdf : BLISS Paper - Bimodal Lattice Signature Scheme that was one of the best looking algorithms for postquantum in 2013
- https://eprint.iacr.org/2014/874.pdf : BLISS-B Paper - Offers speed improvements on BLISS and other potential changes
- https://eprint.iacr.org/2016/276.pdf : BLZZRD Paper - Offers cache protection for the Gaussians required for BLISS/BLISS-B, essentially further improved and secure BLISS-B