# CS254Final-Project
Protocols tested in Proverif and Cryptoverif 

In our final paper, we only discuss the protocols NSPK, NSPK-Lowe-corrected, Diffie-Hellman, and Otis Rees. However, through our working project, we did model other algorithms in ProVerif and CryptoVerif, and we have also uploaded those to this repository! 

This repository includes ProVerif models of both TLS 1.2 (tls12.pv) and TLS 1.3 (tls13NemeiraRaph.pv), along with their shared cryptographic definitions in tls-lib.pvl. Both models fail to fully verify in ProVerif. For TLS 1.2, several secrecy and authentication queries fail, especially those involving finish messages and key agreement. This reflects known limitations of symbolic tools like ProVerif in modeling probabilistic behaviors, negotiated cipher suites, and low-level cryptographic details like padding and MAC structure. TLS 1.3 fares slightly better, but still fails certain client-server correspondence queries, likely due to similar abstraction issues in modeling early key derivation and ephemeral secrets.

IMPORTANT: For CryptoVerif, multiple models—including NSPK-Crypto.pcv and DHCryptoNemeiraRaph.ocv-compile and run as expected in the online version and on Linux environments. However, they consistently fail on macOS systems, including ours. Despite aligning closely with official examples, CryptoVerif fails to parse or recognize standard syntax when run locally. We have not identified the exact cause of these errors, but we rely on verified behavior from official documentation and online runs to interpret expected results in our project discussion.


Credits:

- Otway-Rees, NSPK_proverif adapted from official proverif documentation and tools
- Tls1.2, Tls1.3 adapted from @Inria-Prosecco's code. Modified to give suitable results.
- DH.pv adapted from @darrenldl's code. Modified to give suitable results.
- DH.ocv and NSPK.pcv manually worked through using cryptoverif documentation. 
