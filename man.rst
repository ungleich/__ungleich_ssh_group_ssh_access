cdist-type__ungleich_ssh_group_ssh_access(7)
============================================
ungleich GmbH <cdist--@--ungleich.ch>


NAME
----
cdist-type__ungleich_ssh_group_ssh_access - Manage ssh access for groups


DESCRIPTION
-----------
This cdist type grants access to a certain user for a certain number of people
(= a group).

Groups are resembled by directories below $__files/ssh_group/<name>.
Every file in this directory ending with .pub will be added to the
remote user's authorized_keys file.


REQUIRED PARAMETERS (MULTIPLE)
------------------------------
group
    Specify groups to grant/deny access to.


OPTIONAL PARAMETERS
-------------------
state
    present or absent, defaults to present

user
    Select user to operate on. Defaults to object id.


EXAMPLES
--------

--------------------------------------------------------------------------------
# grant access to group teralytics, user root
__ungleich_ssh_group_ssh_access root --group adminstaff --state present

# grant access to group energy, user vpn
__ungleich_ssh_group_ssh_access vpn --group vpnusers --state present

# grant access to group energy and teralytics, user vpn
__ungleich_ssh_group_ssh_access vpn --group groupa --group groupb --state present

# Remove access to vpn for some other group
__ungleich_ssh_group_ssh_access vpn --group other --state absent
--------------------------------------------------------------------------------


SEE ALSO
--------
:strong:`cdist-type`(7)


AUTHORS
-------
ungleich GmbH <cdist--@--ungleich.ch>


COPYING
-------
Copyright \(C) 2014-2017 ungleich GmbH (www.ungleich.ch).
You can redistribute it and/or modify it under the terms of the
GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option)
any later version.
