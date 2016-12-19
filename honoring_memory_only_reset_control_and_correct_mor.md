# 20. Honoring Memory Only Reset Control and correct MOR spec implementation



## Disclosure Time line


* July 2015 – Initial notification to affected parties (this document)
* Mid-September 2015 - Patches committed to open source, as needed
* January 2016 – Public advisories added to open source projects, as needed



**NOTE:** *Disclosure plan has been updated in revision 1.2 to allow 6 months before public disclosure, as
requested. Product and open source updates should nonetheless strive to address the issue more rapidly,
if possible.*

This disclosure plan is designed to enable affected parties sufficient time to deploy mitigation for these
issues prior to any planned public disclosure.



## Background




In EDK II source code, some infrastructure exists for the Memory Overwrite Request (MOR) capability,
which allows an OS to request that memory be cleared upon reboot (see the TCG Platform Reset Attack
Mitigation Specification Version 1.00, Revision .92 or later). Revision 1.00 is strongly encouraged,
including implementation of detecting an orderly OS shutdown to prevent unnecessary memory clear
operations. This is a standard published by the Trusted Computing Group and required by some
operating systems, such as Microsoft Windows.


The EDK II infrastructure for this capability is implemented in the ```SecurityPkg```, as described in page 15 of
A Tour Beyond BIOS: Implementing TPM2 Support in EDKII. This generic code can signal to the platform
that there must be a ‘clear’ operation, but the underlying platform implementation of the memory clear
is often in closed source platform and SI-vendor specific code. In the case of EDK II, the signal is
implemented with a UEFI variable. EDK II provides code to initialize, set, and reset the variable, but there
also needs to be platform-specific code to honor the signal and perform the clear operation.


## Issue -1 


We have discovered that, on some platforms, the signal to clear memory is not honored. This could be
because the platform-specific code to do the clear is not implemented or because the firmware fails to
invoke this code correctly. If the MOR signal is not honored, Cold Boot attacks may be able to more
easily reveal encryption keys or other secrets from OS runtime.


### Recommendation -1


Firmware developers who base code on EDK II should review their implementation for this issue and
correct it, if needed. Where changes to open source are needed, Intel is recommending an embargo
according to the timeline above.

Here is some sample code for an EDKII-style PEI Platform code that can do the clear:
```javascript
Status = VariableServices->PeiGetVariable (
          PeiServices,
          EfiMemoryOverwriteControlVariable,
          &gEfiMemoryOverwriteControlDataGuid,
          NULL,
          &VarSize,
          &MemoryOverwriteReq
          );
if (!EFI_ERROR(Status)) {
// Set a Bit to tell Memory reference code to zeroize memory w/ hardware engine
// or perform the zeroize operation in software
}```

The actual clear operation will depend upon the platform type, so the above example only has a placeholder
within the non-error path to insert the appropriate codes.

Implementation on Quark http://comments.gmane.org/gmane.comp.bios.edk2.devel/7022 


> **NOTE TO PUBLICATIONS:**  Need to decide if we should await MinnowBoard Max applying HSD 216056  this fix (Fixed in Release 91 of MinnowBoard MAX) now that the 1/16 embargo from USRT has passed.   Also, maybe replace above code sample w/ the Galileo impl?



## Issue – 2



**Document**<br>
  
> **TCG Platform Rest Attack Mitigation Specification** <br>
  Secification Version 1.00 <br>
  Revision 1.00<br>
  May 15, 2008<br>
  Pulished <br>

Reads on having the implementation do the following:
> **SetVariable may be modified to disallow deletion of this UEFI variable, and to disallow a change in its attributes** <br>

this was not the case in the MOR driver for the last several years.  

**Repro steps:**
1. Set BIOS /BIOS/Intel advanced menu/TPM configuration/Current TPM device = dTPM 2.0 
2. Set BIOS /BIOS/Boot maintenance menu/Secure boot configuration/Attempt Secure boot = checked 
3. Restart the system
4. Run the command 'setvar MemoryOverwriteRequestControl -guid E20939BE-32D4-41BE-A150-897F85D49829 -nv -bs -rt = 01' in EFI_shell
5. Run the command 'dmpstore -b -d -guid E20939BE-32D4-41BE-A150-897F85D49829' in EFI_shell
6. result should could be a failure



### Recommendation – 2
This gap was addressed along w/ the implementation of the new feature described in https://msdn.microsoft.com/en-us/library/windows/hardware/mt270973(v=vs.85).aspx in the EDKII implementation 

MORLOCK2 checked in at EDK2 SVN  https://sourceforge.net/p/edk2/code/19690

Recommend implementations pick up the above patch.


## Acknowledgments


This first issue was initially reported by Jeremiah Cox of Microsoft Corporation.  Second issue was reported both by Intel internal testing and Jeremiah Cox of Microsoft Corporation.


## References


USRT Advisory M1412: Memory-Overwrite-Request
	(MOR) support

Secure MOR Implementation https://msdn.microsoft.com/en-us/library/windows/hardware/mt270973(v=vs.85).aspx

The TCG Platform Reset Attack Mitigation Specification Version 1.00, Revision .92 or later. Revision 1.00
(http://www.trustedcomputinggroup.org/resources/pc_client_work_group_platform_reset_attack_miti
gation_specification_version_10 ).

Windows 8 Logo requirements
http://download.microsoft.com/download/A/D/F/ADF5BEDE-C0FB-4CC0-A3E1-
B38093F50BA1/windows8-hardware-cert-requirements-system.pdf.

A Tour Beyond BIOS with the UEFI TPM2 Support in EDKII
https://firmware.intel.com/sites/default/files/resources/A_Tour_Beyond_BIOS_Implementing_TPM2_Support_in_EDKII.pdf

Cold Boot Attacks
	https://citp.princeton.edu/research/memory/
