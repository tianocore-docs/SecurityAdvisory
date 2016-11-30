# 4. Overwrite from Performance Data Variable {#overwrite-from-performance-data-variable}


## Description:


The variable ```PerfDataMemAddr``` was used to hold the address of a buffer for performance data, and this variable could be arbitrarily modified by runtime software. This could cause firmware to corrupt its own code/data.


## Recommendation:


This is addressed by EDK2 SVN https://sourceforge.net/p/edk2/code/14386.


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security.


