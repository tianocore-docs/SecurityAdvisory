<!--- @file
  Security Advisory for issue "Stack Overflow on Corrupted BMP"

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

# 35. Stack Overflow on Corrupted BMP{#stack-overflow-on-corrupted-bmp}

## Description:

Stack overflow in corrupted bmp for EDK II may allow unprivileged user to potentially enable denial of service or elevation of privilege via local access. 

## Impact:

Denial of Service or Elevation of Privilege

## Severity:
7.4 high CVSS:3.0/AV:L/AC:L/PR:H/UI:R/S:C/C:N/I:H/A:H

## Recommendation:

EDK II Commits:

- https://github.com/tianocore/edk2/commit/89910a39dcfd788057caa5d88b7e76e112d187b5

- https://github.com/tianocore/edk2/commit/ffe5f7a6b4e978dffbe1df228963adc914451106

Patch:

- https://bugzilla.tianocore.org/attachment.cgi?id=212

## Acknowledgments:

Intel Team


## References:
CVE-2018-12181

EDK II Bugzilla [#1135](https://bugzilla.tianocore.org/show_bug.cgi?id=1135)
