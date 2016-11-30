# 16. Boot Failure Related to TPM Measurements {#boot-failure-related-to-tpm-measurements}


## Description:


When UEFI Variable storage space is full, the TPM measurement driver could not support making a measurement log and would ```ASSERT```, preventing successful boot.


## Recommendation:


This is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/16281.


## Acknowledgments:


Reported by Intel


## References:


•	USRT M1248
