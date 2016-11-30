# 19. Counter Based Authenticated Variable Issue {#counter-based-authenticated-variable-issue}

## Description:


The variable ```AuthVarKeyDatabase``` is internally used by the UEFI variable driver and was protected with a counter-based authentication attribute. The implementation used an incorrect public key to process updates to this variable.


## Recommendation:


This issue has been addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/16220.


## Credit:


Reported by Intel.


## References:


•	USRT M1290

