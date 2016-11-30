# 15. Buffer Overflows in Capsule Update {#buffer-overflows-in-capsule-update}


## Description:


During capsule update processing, a loop will continue adding arbitrarily many values from the capsule ```(Fvb->NumBlocks)```. After summation, the final value is multiplied by a static size and used to calculate
 

the size of allocation. This allocation, upon integer overflow, can be small, while the loop that copies
data based on values from the capsule will copy a large amount of data.
Additionally, the ```CapsuleCoalesce``` function also contained an integer overflow during summation of the size of the image and descriptor. This also results in a small allocation but a large copy.

## Recommendation:


These issues are addressed by SVN  https://sourceforge.net/p/edk2/code/15136 and  https://sourceforge.net/p/edk2/code/15137.

## Acknowledgements:


Reported by Corey Kallenberg, Xeno Kovah, John Butterworth, and Sam Cornwell of the MITRE Corporation.


## References:


• CERT/CC VU#552286