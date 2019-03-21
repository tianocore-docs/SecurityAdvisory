<!--- @file
  Security Advisory for issue "Unlimited FV Recursion"
  Copyright (c) 2019, Intel Corporation. All rights reserved.<BR>

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

# 39. Unlimited FV Recursion{#unlimited-fv-recursion}

## Description:

Stack overflow in DxeCore for EDK II may allow an unauthenticated user to potentially enable escalation of privilege, information disclosure and/or denial of
service via local access. 

## Impact:

Escalation of Privilege, Information Disclosure and/or Denial of Service

## Severity:
High 7.1 - CVSS:3.0/AV:P/AC:H/PR:N/UI:N/S:C/C:H/I:H/A:H
## Recommendation:

EDK II commits:

- https://github.com/tianocore/edk2/commit/0a0d5296e448fc350de1594c49b9c0deff7fad60

## Acknowledgments:

Intel Team


## References:
CVE-2018-12183

EDK II Bugzilla [#1126](https://bugzilla.tianocore.org/show_bug.cgi?id=1126) [#1137](https://bugzilla.tianocore.org/show_bug.cgi?id=1137)

