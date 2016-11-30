# 3. UEFI Variable “Reinstallation” {#uefi-variable-reinstallation}


## Description:


It had been possible to call the ```SetVariable``` API at runtime on a variable that did not have ```RUNTIME_ACCESS``` permission, causing a new variable with the same name/GUID to be created. It was possible for this new variable to be used instead of the original, protected variable.


## Recommendation:


This issue is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/13156.


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security.
