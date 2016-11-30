# 10. Heap Overflow in UpdateVariable {#heap-overflow-in-updatevariable}


## Description:


The ```UpdateVariable``` function performed a copy first and then checked the size. This may be too late.
	

## Recommendation:


This is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/14323.


## Acknowledgments:


Reported by the Advanced Threat Research Team at Intel Security.


