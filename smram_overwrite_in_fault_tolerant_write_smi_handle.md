# 7. SMRAM Overwrite in Fault Tolerant Write SMI Handler {#smram-overwrite-in-fault-tolerant-write-smi-handler}


## Description:


The function ```SmmFaultTolerantWriteHandler``` did not correctly validate inputs. This could result in an overwrite of SMRAM.

## Recommendation:


This issue is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/13518 and https://sourceforge.net/p/edk2/code/13763.


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security.

