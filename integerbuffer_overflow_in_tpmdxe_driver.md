# 12. Integer/Buffer Overflow in TpmDxe Driver {#integer-buffer-overflow-in-tpmdxe-driver}


## Description:


The ```MeasureVariable ``` function calculated the sum of many fields. This could lead to an integer overflow that resulted in a small allocation of memory and a large copy.

## Recommendation:


This is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/14396.


## Acknowledgments:


Reported by the Advanced Threat Research Team at Intel Security.

