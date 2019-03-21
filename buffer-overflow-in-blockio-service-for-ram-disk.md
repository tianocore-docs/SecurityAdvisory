<!--- @file
  Security Advisory for issue "Buffer Overflow in BlockIo service for RAM disk"

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

# 36. Buffer Overflow in BlockIo service for RAM disk{#buffer-overflow-in-blockio-service-for-ram-disk}

## Description:

Buffer overflow in BlockIo service for EDK II may allow an unauthenticated user to potentially enable escalation of privilege, information disclosure and/or denial of
service via network access. 

## Impact:

Escalation of Privilege, Information Disclosure and/or Denial of service

## Severity:
7.5 (High) - CVSS:3.0/AV:N/AC:H/PR:N/UI:R/S:U/C:H/I:H/A:H

## Recommendation:

EDK II Commits:

- https://github.com/tianocore/edk2/commit/fccdb88022c1f6d85c773fce506b10c879063f1d
- https://github.com/tianocore/edk2/commit/38c9fbdcaa0219eb86fe82d90e3f8cfb5a54be9f

Patch:

- https://bugzilla.tianocore.org/attachment.cgi?id=233

## Acknowledgments:

Intel Team


## References:
CVE-2018-12180

EDK II Bugzilla [#1134](https://bugzilla.tianocore.org/show_bug.cgi?id=1134)

