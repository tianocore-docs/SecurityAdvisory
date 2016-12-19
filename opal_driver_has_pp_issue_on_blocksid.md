# 23. OPAL driver has PP issue on BlockSid



## Description:


EDKII open source has OPAL driver at ```SecurityPkg\Tcg\Opal```. It includes a feature named ```BlockSid```, which is defined in ****TCG Physical Presence and TCG OPAL BlockSid specification****.
The TCG PP spec defines PP opcode to enable/disable``` BlockSid```, which may need user confirmation. However, current EDKII OPAL driver just uses a normal variable ```(OPAL_EXTRA_INFO_VAR_NAME/gOpalExtraInfoVariableGuid)``` to store the BlockSid enable/disable.
This driver does not follow TCG recommendation to use PP process to request user confirmation on BlockSid state change.
Also this variable is NOT locked. It means any one can overwrite this variable and bypass BlockSid operation.


## Recommendation:


We had better follow TCG PP specification, and implement TCG storage operation (96~101). So that:
1.	User confirmation is needed when BlockSid state is changed. (This follows TCG PP spec)
2.	This BlockSid state is still saved into variable, but the variable is locked via ```EDKII_VARIABLE_LOCK_PROTOCOL``` (This makes sure no malicious code may modify BlockSid enable/disable state.)

This is addressed by EDK2 GIT e92ddda2b547f0b952935abaf44fd72e97dbf755..4e3b05a49f454bc257252ae9090421e3c8447737, 
bee13c00218f3ed3118d8d87683c11b31ca04564, 01dd077315c6759c94af9af4232f8318db13cf8d.


## Acknowledgments:


Reported by Yao, Jiewen <jiewen.yao@intel.com>.


## References:


*	USRT M1620
*	TCG PC Client Platform Physical Presence Interface Specification
*	TCG Storage Feature Set: Block SID Authentication

