<!--- @file
  dhcp_misses_boundary_check_for_network_packet.md for Security Advisory
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

# 25. DHCP misses boundary check for network packet


## Description:


The UEFI DHCP Protocol has many conventions for processing and caching incoming DHCP4/DHCP6 packets. Their current exists a check in ```PxeBcCacheDhcp4Packet``` before calling ```CopyMem()``` on two ```EFI_DHCP4_PACKET``` structs.
This check uses an ```ASSERT``` which will be compiled out for RELEASE builds of UEFI on EDK II. 

But actually, the source is from an external network, and there is no guarantee that the source Length is smaller than destination size. It might happen.


## Recommendation:


1. For this specific issue, we need remove ```ASSERT``` and use error checking.
2. clarify the rule, ```ASSERT``` can only be used for something ***never*** happen. Error check must be used for something ***might*** happen.

This is addressed by EDK2 GIT <br>
4f6b33b460226bc1a54d8af2c0f4fe195f2f04ce, 632dcfd6857b6211ce3fe9755d3c11e74ef5d4477, 471342bbefaac1c21fe7fa4e80949b552b12fbdd, a35dc6499beb0b76c340379a06dff74a8d38095a.

## Acknowledgements:
Reported by Timzen, Topher <topher.timzen@intel.com>

## References:
•	USRT M1622


