# Ansible Role: Swapfile

[![Build Status](https://travis-ci.org/sjinks/ansible-role-swapfile.svg?branch=master)](https://travis-ci.org/sjinks/ansible-role-swapfile)

This role configures a swapfile.

## Requirements

Sufficient disk space to hold the swap file.

## Role Variables

  * `swapfile_path`: full path to the swap file to create (e.g.: `/swapfile`); when empty, no swap file will be created
  * `swapfile_size_mib`: the size of the swap file (MiB); when negative or zero, no swap file will be created
  * `swapfile_use_dd`: `False` (default) if use `fallocate` to create the file, `True` to use `dd`
  * `swapfile_swappiness`: if not `False`, set the value of `vm.swappiness` to this value
  * `swapfile_vfs_cache_pressure`: if not `False`, set the value of `vm.vfs_cache_pressure` to this value

## Dependencies

None.

## Usage

```
- hosts: all
  roles:
    - sjinks.swapfile
```

or

```
- hosts: all
  roles:
    - { role: sjinks.swapfile, swapfile_location: /swap, swafile_size_mib: 1024 }
```

## License

MIT, see LICENSE file.
