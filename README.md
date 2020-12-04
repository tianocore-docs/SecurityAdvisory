<!--- @file
  README.md for Security Advisory
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

<img src="media/TianocoreTitlePageLogo.jpg" width="300" />

### {{ book.title }}

{% if book.draft %}
** DRAFT FOR REVIEW **
{% else %}
** {{ book.version }} **
{% endif %}

** {{ gitbook.time|date('MM/DD/YYYY hh:mm:ss') }} **

{% if book.udkrelease %}
** {{ book.udkrelease }} **
{% endif %}

This document will list briefings on each security issue found and give a description, a recommendation on a solution, an acknowledgment that the solution is validated and references.


### Acknowledgements

Redistribution and use in source (original document form) and 'compiled'
forms (converted to PDF, epub, HTML and other formats) with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code (original document form) must retain the
   above copyright notice, this list of conditions and the following
   disclaimer as the first lines of this file unmodified.

2. Redistributions in compiled form (transformed to other DTDs, converted to
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

Copyright (c) 2017-2019, Intel Corporation. All rights reserved.


### Process
_(short form)_

1. Security Bugs reported through: [How to report a Security Issue](https://github.com/tianocore/tianocore.github.io/wiki/Reporting-Security-Issues)
2. The issue is evaluated
3. Determine if a Security issue
4. Determine Module
5. Fix and Validate issue
6. If Security, Update Security Advisory (This Document)

### Revision History

| Revision   | Revision History   | Date        |
| ---------- | ------------------ | --------------- |
| .002.0       | Initial release.<BR> Logs 1 - 19  | Jan 9, 2015  |
| | | |
| .003.0       | Logs for 20-26    | Nov 29, 2016  |
| | | |
| .003.1       | Logs for 21-26 <BR>-  Fix more for DHCP issue, feedback from Phoenix.<BR>-  Fix Smm Variable GetInfo function issue, discovered by release test.<BR>-  Fix GIT hash info, which incorrect stated before. logs 21, 22, 23, 24, 25, 26                                  |  Dec 19, 2016|
| | | |
| .004.0 | Log 27 - Update<BR>Update Gitbook Template | Jan 11, 2018 |
| .005.0 | Log 28  Update  |July 10, 2018  |
| .006.0  | Log 29 Update  | Sept 19, 2018  |
| .007.0  | Log 30 & 31 Update  | Oct 12, 2018  |
| .008.0 | Log 32-40  Update | Mar 21, 2019 |
| .009.0 | Log 41  Update | May 10, 2019 |
|   |   |  |

