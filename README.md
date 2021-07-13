# ofed
=========

Installs OFED via Mellanox Repositories

# Requirements

None

# Role Variables
--------------

Please see `defaults/main.yml`.

* `ofed_repository_url` Gives a URL to the repository holding the OFED driver packages. Defaults to the [Mellanox public package repository](https://linux.mellanox.com/public/repo/mlnx_ofed)
* `ofed_version` Specifies the OFED driver version to be installed, default is `latest`
* `ofed_target_release` Specifies the Linux distribution for the install of the OFED drivers, default is `rhel7.8`
 
# Dependencies

None

# Example Playbook

## Default settings

```
    - hosts: servers
      tasks:
        - include_role: stackhpc.ofed
```

## Using custom settings

These settings will install the OFED drivers from a local repository, and target version and the RHEL8.3 release

```
    - hosts: servers
      vars:
        ofed_repository_url: http://repo.local
        ofed_version: '5.2-2.2.0.0'
        ofed_target_release: rhel8.3
      tasks:
        - include_role: stackhpc.ofed
```

## Disable kernel update

This should skip the kernel updates:

```
    - hosts: servers
      vars:
        ofed_update_kernel: false
      tasks:
        - include_role: stackhpc.ofed
```

License
-------

Apache

Author Information
------------------

Will Szumski
