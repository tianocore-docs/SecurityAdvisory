<!--- @file
  EDK II  Authenticated Variable Bypass.md for Security Advisory
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

# 30. EDK II Authenticated Variable Bypass {#edk-ii-authenticated-variable-bypass}


## Description:
Logic error in MdeModulePkg in EDK II firmware may allow authenticated user to potentially bypass configuration access controls and escalate privileges via local access. 
## Impact
Elevation of Privilege
## Severity
Medium 6.7 CVSS:3.0/AV:L/AC:L/PR:H/UI:N/S:U/C:H/I:H/A:H
## Recommendation:
This address the following issue in Tianocore Bugzilla: <br>https://bugzilla.tianocore.org/show_bug.cgi?id=415



Patch to update firmware is:<br>https://bugzilla.tianocore.org/attachment.cgi?id=44 

## Acknowledgments:
This issue was discovered by Intel.
## References:
CVE-2018-3613


