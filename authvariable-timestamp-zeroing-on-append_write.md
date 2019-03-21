<!--- @file
  Security Advisory for issue "AuthVariable Timestamp Zeroing on APPEND_WRITE"
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

# 40. AuthVariable Timestamp Zeroing on APPEND_WRITE{#authvariable-timestamp-zeroing-on-append_write}

## Description:

Logic issue in variable service module for EDK II/UDK2018/UDK2017/UDK2015 may allow an authenticated user to potentially
enable escalation of privilege, information disclosure and/or denial of service via local access. 

## Impact:

Escalation of Privilege, Information Disclosure and/or Denial of Service

## Severity:
Medium 6.7 CVSS:3.0/AV:L/AC:L/PR:H/UI:N/S:U/C:H/I:H/A:H
## Recommendation:

EDK II commits:

- [master] https://github.com/tianocore/edk2/commit/b7dc8888f31402f410c53242839271ba3b94b619
- [UDK2018] https://github.com/tianocore/edk2/commits/348d9f7a078cf8893a803bc4e90abefb3126344a
- [UDK2017] https://github.com/tianocore/edk2/commits/5c693e581e6ab2c8e9daac170616d867272399d9
- [UDK2015] https://github.com/tianocore/edk2/commits/2bfddc064b1cd1f4539350bff1473a9c371865d8

## Acknowledgments:

Intel Team


## References:
CVE-2018-3613

EDK II Bugzilla [#415](https://bugzilla.tianocore.org/show_bug.cgi?id=415)

