# 5. CommBuffer SMM Overwrite/Exposure {#commbuffer-smm-overwrite-exposure}


## Description:


“```CommBuffer```” is the name of a communication mechanism between runtime code and runtime SMM code. Malicious code could set the address of ```CommBuffer``` such that calls to runtime SMM code would overwrite or expose the contents of SMRAM.


## Recommendation:


This issue is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/13514, 13530, and 14292.


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security.
