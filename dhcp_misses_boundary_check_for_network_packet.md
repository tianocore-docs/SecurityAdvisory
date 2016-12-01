# 25. DHCP misses boundary check for network packet


## Description:


The UEFI DHCP Protocol has many conventions for processing and caching incoming DHCP4/DHCP6 packets. Their current exists a check in ```PxeBcCacheDhcp4Packet``` before calling ```CopyMem()``` on two ```EFI_DHCP4_PACKET``` structs.
This check uses an ```ASSERT``` which will be compiled out for RELEASE builds of UEFI on EDK II. 

But actually, the source is from an external network, and there is no guarantee that the source Length is smaller than destination size. It might happen.


## Recommendation:


1. For this specific issue, we need remove ```ASSERT``` and use error checking.
2. clarify the rule, ```ASSERT``` can only be used for something *never* happen. Error check must be used for something *might* happen.

This is addressed by EDK2 GIT 4f6b33b460226bc1a54d8af2c0f4fe195f2f04ce, 632dcfd6857b6211ce3fe9755d3c11e74ef5d447.

Acknowledgements:
Reported by Timzen, Topher <topher.timzen@intel.com>

References:
•	USRT M1622


