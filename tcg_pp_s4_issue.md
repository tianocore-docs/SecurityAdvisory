# 21. TCG PP S4 issue



## Description:


TCG physical presence will record TCG PP flag (if user confirmation is required) to a variable ```(TCG2_PHYSICAL_PRESENCE_FLAGS_VARIABLE/gEfiTcg2PhysicalPresenceGuid)```. This variable is locked by ```EDKII_VARIABLE_LOCK_PROTOCOL```.
In S4 resume path, the code ```Tcg2PhysicalPresenceLibProcessRequest``` finds it is S4 resume and return immediately. It does not call ```EDKII_VARIABLE_LOCK_PROTOCOL``` to lock the variable ```(TCG2_PHYSICAL_PRESENCE_FLAGS_VARIABLE/ gEfiTcg2PhysicalPresenceGuid)```.


## Recommendation:


We need update ```Tcg2PhysicalPresenceLibProcessRequest``` to move S4 check AFTER variable lock.
This is addressed by EDK2 GIT 7b9b576c71c71ed134f50497fd58f862109dd80b, fb4f55dd8cede4aad14848e2dd260d2d36365f0c.


## Acknowledgements:


Reported by Coleman, Rusty <Rusty.Coleman@intel.com>.


## References:


•	USRT M1615
