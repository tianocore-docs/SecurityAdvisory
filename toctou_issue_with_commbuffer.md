# 6. TOCTOU Issue with CommBuffer {#toctou-issue-with-commbuffer}


## Description:


Values from CommBuffer could be changed by DMA, running in parallel with SMM, leading to a buffer overflow during a memory copy operation.

## Recommendation:


This issue is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/14325 and https://sourceforge.net/p/edk2/code/14379.


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security.

