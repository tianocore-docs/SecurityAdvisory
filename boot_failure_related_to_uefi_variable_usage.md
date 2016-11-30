# 14. Boot Failure Related to UEFI Variable Usage {#boot-failure-related-to-uefi-variable-usage}


## Description:


When certain UEFI variables were corrupted, various code would ```ASSERT```, preventing successful boot.


## Recommendation:


This is addressed by the following EDK2 SVN https://sourceforge.net/p/edk2/code/ commits: 13203, 13297, 13323, 14029, 15330, 15336,
15386, 15407, 15357, 15393, 15401, 15340, 15388, 15338, 15328, 15329, 15334, 15405, 15416, 15360,
15339, 15404, 15426, 15337, 15333, 15385, 15356, 15376, 15385, 15391, 15351, 15544, 15545, 15909,
15910, 15977


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security and Corey Kallenberg, Xeno Kovah, John Butterworth, and Sam Cornwell of the MITRE Corporation.

## References:


•	CERT/CC VU#758382

