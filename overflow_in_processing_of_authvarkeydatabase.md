<!--- @file
  overflow_in_processing_of_authvarkeydatabase.md for Security Advisory
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
