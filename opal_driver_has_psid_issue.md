# 24. OPAL driver has PSID issue


## Description:


EDKII open source has OPAL driver at ```SecurityPkg\Tcg\Opal```. It includes a feature named PSID. PSID is a hard driver specific key which is used to revert to factory default mode. This PSID value should be kept as secret.
Current EDKII OPAL driver does not clear PSID in memory after use. The secret value is left in stack, or global variable memory without clear.
Technically, a malicious program may search memory and find out the PSID in memory, if user inputs the PSID value in BIOS.


## Recommendation:


1.	To fix this specific issue, OPAL driver should call ```ZeroMem()``` to clear PSID in memory after it is used.
2.	As generic rule, if a password or other secret is used in a driver, this driver should call ```ZeroMem()``` to clear secret in memory after it is used.


This is addressed by EDK2 GIT e92ddda2b547f0b952935abaf44fd72e97dbf755..4e3b05a49f454bc257252ae9090421e3c8447737, bb3411ef286b3002d922e3785aa7a718417448f6..cb930ec304395404d10adb7946449df1adf1de7f.


## Acknowledgments:


Reported by Yao, Jiewen <jiewen.yao@intel.com>.


## References:


•	USRT M1619


