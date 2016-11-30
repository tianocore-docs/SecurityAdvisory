# 2. Incorrect PKCS#1v1.5 Padding Verification for RSA Signature Check {#incorrect-pkcs-1v1-5-padding-verification-for-rsa-signature-check}


## Description:


The implementation of RSA signature verification was vulnerable to a Bleichenbacher RSA signature forgery attack when keys with a small public exponent were used.


## Recommendation:


This issue is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/14309.


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security.

