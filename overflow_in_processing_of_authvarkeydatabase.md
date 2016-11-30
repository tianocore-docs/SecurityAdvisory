# 18. Overflow in Processing of AuthVarKeyDatabase {#overflow-in-processing-of-authvarkeydatabase}


## Description:


When the UEFI Variable ```AuthVarKeyDatabase``` is used, it may be possible to overflow a statically allocated buffer.

## Recommendation:


The variable ```AuthVarKeyDatabase``` is an authenticated variable. Its contents may not be changed without access to an authorized private key. This limits the severity of the issue.
EDK2 maintainers have assessed that this issue violates the threat model and does not require explicit mitigation. This issue requires an attacker to introduce inconsistency into internal data structures in the variable storage area. The EDK2 architecture requires internal data structures to be protected in implementation. An attacker capable of bypassing this protection may introduce many other inconsistencies. EDK2 SVN https://sourceforge.net/p/edk2/code/16227 added a comment to the source file in order to clarify this.


## Acknowledgments:


Reported by Rafal Wojtczuk from Bromium and Corey Kallenberg from MITRE.


## References:


•	USRT M1246
