# 26. SmmCore comm buffer check has TOCTOU issue



## Description:


A SMM communication buffer is used for data exchange between the SMM component and the non-SMM component. The malicious non-SMM component may generate a malicious SMM communication buffer to attack the SMM component.
In order to resist this attack, the SMM component need validate the SMM communication buffer before use it. The validation need cover if the SMM communication buffer overlaps with the SMRAM.
The data to be validated should be copied into SMRAM as local variable to avoid Time-Of-Check/Time-Of-Use attack. If the data is not copied into SMRAM, the validation can be bypassed.

For example, a malicious software may let an Application Processor (AP) be outside SMRAM, and only let a Bootstrap Processor (BSP) be inside SMRAM. After the BSP performs the check for the communication buffer, the AP modified the communication buffer. Then when the BSP uses the communication buffer later, the BSP is attacked and the check is actually bypassed.

See ```MdeModulePkg/Core/PiSmmCore/PiSmmCore.c```:
The function ```InternalIsBufferOverlapped``` and ```SmmIsBufferOutsideSmmValid``` are the checker. They validate ```gSmmCorePrivate->CommunicationBuffer``` and ```gSmmCorePrivate->BufferSize```

However these data are outside SMRAM, the malicious code may modify them after check.
So below code may still get wrong ```gSmmCorePrivate->CommunicationBuffer```.


## Recommendation:


We need copy ```gSmmCorePrivate->CommunicationBuffer``` and ```gSmmCorePrivate->BufferSize``` to be a local variable, then check and use them, finally sync local variable back to outside SMRAM.
	

This is addressed by EDK2 GIT eaae7b33b1cf6b9f21db1636f219c2b6a8d88afd.


## Acknowledgments:


Reported by Yao, Jiewen <jiewen.yao@intel.com>


## References:


•	USRT M1636


