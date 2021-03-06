<!--- @file
  opal_driver_has_pp_issue_on_blocksid.md for Security Advisory
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

