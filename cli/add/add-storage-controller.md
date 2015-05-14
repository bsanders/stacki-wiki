## add storage controller

### Usage

`stack add storage controller {scope} [adapter=int] [arrayid=string] [enclosure=int] [hotspare=int] [raidlevel=int] [slot=int]`

### Description

Add a storage controller configuration to the database.

### Arguments

* `{scope}`

   Zero or one argument. The argument is the scope: a valid os (e.g.,
	'redhat'), a valid appliance (e.g., 'compute') or a valid host
	(e.g., 'compute-0-0). No argument means the scope is 'global'.


### Parameters
* `[adapter=int]`

   Adapter address.
* `[arrayid=string]`

   The 'arrayid' is used to determine which disks are grouped as part
	of the same array. For example, all the disks with arrayid of '1' will
	be part of the same array. Arrayids must be integers starting at 1
	or greater. If the arrayid is 'global', then 'hotspare' must
	have at least one slot definition (this is how one specifies a global
	hotspare).
	In addition, the arrays will be created in arrayid order, that is,
	the array with arrayid equal to 1 will be created first, arrayid
	equal to 2 will be created second, etc.
* `[enclosure=int]`

   Enclosure address.
* `[hotspare=int]`

   Slot address(es) of the hotspares associated with this array id. This
	can be a comma-separated list (like the 'slot' parameter). If the
	'arrayid' is 'global', then the specified slots are global hotspares.
* `[raidlevel=int]`

   RAID level. Raid 0, 1, 5, 6 and 10 are currently supported.
* `[slot=int]`

   Slot address(es). This can be a comma-separated list meaning all disks
	in the specified slots will be associated with the same array

### Examples

* `stack add storage controller compute-0-0 slot=1 raidlevel=0 arrayid=1`

   The disk in slot 1 on compute-0-0 should be a RAID 0 disk.

* `stack add storage controller compute-0-0 slot=2,3,4,5,6 raidlevel=6 hotspare=7,8 arrayid=2`

   The disks in slots 2-6 on compute-0-0 should be a RAID 6 with two
	hotspares associated with the array in slots 7 and 8.


