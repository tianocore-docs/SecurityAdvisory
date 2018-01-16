<!--- @file
  smmcore_comm_buffer_check_has_toctou_issue.md for Security Advisory
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

Because the `BufferSize` is moved to SMRAM by SmmCore, the SMM driver should not check the address for the BufferSize.	

This is addressed by EDK2 GIT eaae7b33b1cf6b9f21db1636f219c2b6a8d88afd, 62016c1e898434a0326f658912b1e7e0a9c5575e.


## Acknowledgments:


Reported by Yao, Jiewen <jiewen.yao@intel.com>


## References:


•	USRT M1636


