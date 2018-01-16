<!--- @file
  bios_password.md for Security Advisory
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

# 22. BIOS Password

## Description:

BIOS setup driver may provide capability for admin password or user password. In Edk II sample driver - `MdeModulePkg\Universal\DriverSampleDxe`, the password is saved to variable. However, this code in this sample driver might be copied to production code.  
The `EncodePassword` function only uses a simple XOR with constant key to _encode_ password and save to variable. The variable can be read by anyone. The malicious code to get the variable, and use XOR with this constant key to get the password easily.

## Recommendation:

The bad example in EDKII is deleted by GIT 6bfd7ea7d65af28910779b9c72ff2e5fd3a2a54e, 88f0c4e29c03600f2a45a5bd14c500049d2b09dc ..87f04621ad4069c3b2994bc217971d1c5a53fa82.

The better way to encode password is:  
1.    Generate a random salt value for user.  
2. Use SHA256 to hash the password and salt value.  
3. Save random salt and hash to variable.

## Acknowledgments:

Reported by Matrosov, Alexander [alexander.matrosov@intel.com](mailto:alexander.matrosov@intel.com).

## References:

•    USRT M1617, M1633

