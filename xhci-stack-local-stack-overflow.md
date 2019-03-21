<!--- @file
  Security Advisory for "XHCI stack local stack overflow"

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

# 37. XHCI stack local stack overflow {#xhci-stack-local-stack-overflow}

## Description:

Stack overflow in XHCI for EDK II may allow an unauthenticated user to potentially enable denial of service via local access. 

## Impact:

Denial of Service

## Severity:
Medium 4.0 CVSS:3.0/AV:L/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:L
## Recommendation:

EDK II Commits:

- https://github.com/tianocore/edk2/commit/acebdf14c985c5c9f50b37ece0b15ada87767359
- https://github.com/tianocore/edk2/commit/72750e3bf9174f15c17e78f0f117b5e7311bb49f

## Acknowledgments:

Microsoft


## References:
CVE-2019-0161

EDK II Bugzilla [#973](https://bugzilla.tianocore.org/show_bug.cgi?id=973)

