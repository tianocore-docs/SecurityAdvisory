# 22. BIOS Password

## Description:


BIOS setup driver may provide capability for admin password or user password. In Edk II sample driver - ```MdeModulePkg\Universal\DriverSampleDxe```, the password is saved to variable. However, this code in this sample driver might be copied to production code.
The ```EncodePassword``` function only uses a simple XOR with constant key to *encode* password and save to variable. The variable can be read by anyone. The malicious code to get the variable, and use XOR with this constant key to get the password easily.


## Recommendation:


The bad example in EDKII is deleted by GIT 6bfd7ea7d65af28910779b9c72ff2e5fd3a2a54e, 88f0c4e29c03600f2a45a5bd14c500049d2b09dc.

The better way to encode password is:
1.	Generate a random salt value for user.
2. Use SHA256 to hash the password and salt value.
3. Save random salt and hash to variable.


## Acknowledgements:


Reported by Matrosov, Alexander <alexander.matrosov@intel.com>.


## References:


•	USRT M1617, M1633


