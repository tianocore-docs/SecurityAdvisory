<!--- @file
  tcg_pp_s4_issue.md for Security Advisory
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

# 21. TCG PP S4 issue

## Description:

TCG physical presence will record TCG PP flag \(if user confirmation is required\) to a variable `(TCG2_PHYSICAL_PRESENCE_FLAGS_VARIABLE/gEfiTcg2PhysicalPresenceGuid)`. This variable is locked by `EDKII_VARIABLE_LOCK_PROTOCOL`.  
In S4 resume path, the code `Tcg2PhysicalPresenceLibProcessRequest` finds it is S4 resume and return immediately. It does not call `EDKII_VARIABLE_LOCK_PROTOCOL` to lock the variable `(TCG2_PHYSICAL_PRESENCE_FLAGS_VARIABLE/ gEfiTcg2PhysicalPresenceGuid)`.

## Recommendation:

We need update `Tcg2PhysicalPresenceLibProcessRequest` to move S4 check AFTER variable lock.  
This is addressed by EDK2 GIT 7b9b576c71c71ed134f50497fd58f862109dd80b.

## Acknowledgments:

Reported by Coleman, Rusty [Rusty.Coleman@intel.com](mailto:Rusty.Coleman@intel.com).

## References:

•    USRT M1615

