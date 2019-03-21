<!--- @file
  Security Advisory for issue "PartitionDxe and Udf Buffer Overflow"

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

# 34. PartitionDxe and Udf Buffer Overflow{#partitiondxe-and-udf-buffer-overflow}

## Description:

Buffer overflow in system firmware for EDK II may allow unauthenticated user to potentially enable escalation of privilege and/or denial of
service via network access.

## Impact

Escalation of privilege and/or denial of service

## Severity
8.7 (High) - CVSS:3.0/AV:N/AC:H/PR:N/UI:N/S:C/C:N/I:H/A:H

## Recommendation:

EDK II Commits:

- https://github.com/tianocore/edk2/commit/4df8f5bfa28b8b881e506437e8f08d92c1a00370
- https://github.com/tianocore/edk2/commit/b9ae1705adfdd43668027a25a2b03c2e81960219
- https://github.com/tianocore/edk2/commit/5c0748f43f4e1cc15fdd0be64a764eacd7df92f6
- https://github.com/tianocore/edk2/commit/89f75aa04a97293a8ed9db2a90851a5053730cf5
- https://github.com/tianocore/edk2/commit/3b30351b75d70ea65701ac999875fbb81a89a5ca

Patch:

- https://bugzilla.tianocore.org/attachment.cgi?id=224

## Acknowledgments:

Intel Team


## References:
CVE-2019-0160

EDK II Bugzilla [#828](https://bugzilla.tianocore.org/show_bug.cgi?id=828)

