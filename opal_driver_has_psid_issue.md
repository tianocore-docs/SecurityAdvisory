<!--- @file
  opal_driver_has_psid_issue.md for Security Advisory
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

# 24. OPAL driver has PSID issue


## Description:


EDKII open source has OPAL driver at ```SecurityPkg\Tcg\Opal```. It includes a feature named PSID. PSID is a hard driver specific key which is used to revert to factory default mode. This PSID value should be kept as secret.
Current EDKII OPAL driver does not clear PSID in memory after use. The secret value is left in stack, or global variable memory without clear.
Technically, a malicious program may search memory and find out the PSID in memory, if user inputs the PSID value in BIOS.


## Recommendation:


1.	To fix this specific issue, OPAL driver should call ```ZeroMem()``` to clear PSID in memory after it is used.
2.	As generic rule, if a password or other secret is used in a driver, this driver should call ```ZeroMem()``` to clear secret in memory after it is used.


This is addressed by EDK2 GIT e92ddda2b547f0b952935abaf44fd72e97dbf755..4e3b05a49f454bc257252ae9090421e3c8447737, 
bee13c00218f3ed3118d8d87683c11b31ca04564, 01dd077315c6759c94af9af4232f8318db13cf8d. 


## Acknowledgments:


Reported by Yao, Jiewen <jiewen.yao@intel.com>.


## References:


•	USRT M1619


