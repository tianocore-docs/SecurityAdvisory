<!--- @file
  boot_failure_related_to_uefi_variable_usage.md for Security Advisory
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

# 14. Boot Failure Related to UEFI Variable Usage {#boot-failure-related-to-uefi-variable-usage}


## Description:


When certain UEFI variables were corrupted, various code would ```ASSERT```, preventing successful boot.


## Recommendation:


This is addressed by the following EDK2 SVN https://sourceforge.net/p/edk2/code/ commits: 13203, 13297, 13323, 14029, 15330, 15336,
15386, 15407, 15357, 15393, 15401, 15340, 15388, 15338, 15328, 15329, 15334, 15405, 15416, 15360,
15339, 15404, 15426, 15337, 15333, 15385, 15356, 15376, 15385, 15391, 15351, 15544, 15545, 15909,
15910, 15977


## Acknowledgments:


Reported by the Advanced Threat Research team at Intel Security and Corey Kallenberg, Xeno Kovah, John Butterworth, and Sam Cornwell of the MITRE Corporation.

## References:


•	CERT/CC VU#758382

