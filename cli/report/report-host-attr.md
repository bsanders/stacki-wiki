## report host attr

### Usage

`stack report host attr [host] [attr=string] [pydict=bool]`

### Description

Report the set of attributes for hosts.

### Examples

* `stack report host attr compute-0-0`

   Report the attributes for compute-0-0.

* `stack report host attr compute-0-0 pydict=true`

   Report the attributes for compute-0-0 as a python dictionary suitable
	for input to rocks report script.

* `stack report host attr compute-0-0 attr=Kickstart_Lang`

   Output value of the attribute called Kickstart_Lang for node
        compute-0-0.


### Related
[report script](report-script)


