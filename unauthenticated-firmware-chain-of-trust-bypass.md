<!--- @file
  unauthenticated-firmware-chain-of-trust-bypass.md for Security Advisory
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


# 29. Unauthenticated Firmware Chain-of-Trust Bypass {#unauthenticated-firmware-chain-of-trust-bypass}


## Description:
Platform sample code firmware included with 4th Gen Intel® Core™ Processor (Haswell), 5th Gen Intel® Core™ Processor (Broadwell), 6th Gen Intel® Core™ Processor (Skylake), 7th Gen Intel® Core™ Processor (Kaby Lake) and 8th Gen Intel® Core™ Processor (Coffee Lake and Cannon Lake)  contains a logic error allowing physical attacker to bypass firmware authentication.
## Impact
Elevation of Privilege

## Severity
High - 7.6 CVSS:3.0/AV:P/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H


## Recommendation:
Intel recommends that end-users contact their system manufacturers for updated system firmware.

## Acknowledgments:
The issue was reported by Trammell Hudson

## References:
CVE-2018-12169

