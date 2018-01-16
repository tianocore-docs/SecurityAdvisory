<!--- @file
  buffer_overflow_in_variable_reclaim.md for Security Advisory
  Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

-->

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


 
