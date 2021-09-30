## Purpose

The following code shows how to run an ansible ad-hoc-command. This is useful to run a simple command on a number of servers without the nessacity of creating a playbook first.

## Code

```bash
ansible -m fetch -a 'src=/var/log/auth.log dest=/tmp/authlogs/{{inventory_hostname}} flat=yes' -i ~/repos/inventory/inventory-ansible.py kunden
```

## Example

```bash
┌─[12:22:29]-[:)]-[fschneider@frank]-[/home/fschneider/repos/bas/ (master)]
└──> ansible -m fetch -a 'src=/var/log/auth.log dest=/tmp/authlogs/{{inventory_hostname}} flat=yes' -i ~/repos/inventory/inventory-ansible.py kunden

Server1 | CHANGED => {
    "changed": true,
    "checksum": "68a00e3299bcd669fdcac5f556e135751f4b1183",
    "dest": "/tmp/authlogs/Server1",
    "md5sum": "48fd3a9b4438cd0ea5ff4775485c081b",
    "remote_checksum": "68a00e3299bcd669fdcac5f556e135751f4b1183",
    "remote_md5sum": null
}
Server2 | CHANGED => {
    "changed": true,
    "checksum": "c45e8041ee53103ed5d89ce23415a8a02894d207",
    "dest": "/tmp/authlogs/Server2",
    "md5sum": "54ef7882012c432fca53f496e8c4212f",
    "remote_checksum": "c45e8041ee53103ed5d89ce23415a8a02894d207",
    "remote_md5sum": null
}
Server3 | CHANGED => {
    "changed": true,
    "checksum": "d33b2fc277b9331e7ae79fc61c429d2cc2d22828",
    "dest": "/tmp/authlogs/Server3",
    "md5sum": "2bbc346bb603621a118f94a4ac118b90",
    "remote_checksum": "d33b2fc277b9331e7ae79fc61c429d2cc2d22828",
    "remote_md5sum": null
}
Server4 | FAILED! => {
    "changed": false,
    "file": "/var/log/auth.log",
    "msg": "unable to calculate the checksum of the remote file"
}
Server5 | CHANGED => {
    "changed": true,
    "checksum": "5b5d8a00ed87866f84b74c01b13f15cf500edaf9",
    "dest": "/tmp/authlogs/Server5",
    "md5sum": "bfebfcff36634296d867a39aac195d21",
    "remote_checksum": "5b5d8a00ed87866f84b74c01b13f15cf500edaf9",
    "remote_md5sum": null
}
[...]
```

## Additional notes

- The `-i` in the command shows ansible which inventory to use
  - [Introduction to inventories](https://docs.ansible.com/ansible/2.3/intro_inventory.html)
  - [Build your own](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)