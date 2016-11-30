# 17. Buffer Overflow in Variable Reclaim {#buffer-overflow-in-variable-reclaim}


## Description:


The Reclaim function that performs garbage collection on the UEFI variable storage area in flash contained a bug that allowed it to search beyond the bounds of the variable storage area. In this circumstance, a buffer overflow may occur. This may result in elevation of privilege or denial of service.

NOTE: This issue would not normally be exposed. In order to exploit this issue, a separate vulnerability must allow modification of the variable storage area and regions after it, normally stored on SPI flash.

However, because the existing implementation depended upon data outside the variable store, this was considered a security issue and mitigated in code that is intended to be used in production.

## Recommendation:	


The issue was initially reported in ```FSVariable.c```, which is not intended for use in production. EDK2 SVN https://sourceforge.net/p/edk2/code/16217 and https://sourceforge.net/p/edk2/code/16218 introduce comments to clarify that the code is not intended for production use.

Updates to the Reclaim function in ```MdeModulePkg``` and ```SecurityPkg``` in EDK2 were made in EDK2 SVN https://sourceforge.net/p/edk2/code/16280.


## Acknowledgments:


Reported by Rafal Wojtczuk from Bromium and Corey Kallenberg from MITRE.


## References:


•	CERT/CC VU#533140
•	USRT M1247


 
