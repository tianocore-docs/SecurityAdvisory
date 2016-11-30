# 8. SMRAM Overwrite in SmmVariableHandler {#smram-overwrite-in-smmvariablehandler}


## Description:


The function SmmVariableHandler did not correctly validate inputs. This could result in an overwrite of SMRAM.


## Recommendation:


This issue is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/13486 and https://sourceforge.net/p/edk2/code/13534


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security.
