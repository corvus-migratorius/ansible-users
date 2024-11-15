ansible-users
=========

Create user accounts according to a YAML manifest.

Controls:
  - username and UID
  - groupname and GID
  - homedir creation
  - GECOS field (typically full user name)
  - shell
  - SSH public key deployment to `.ssh/authorized_keys`
  - account expiration
  - memory, swap and CPU allocation limits via user slices

Check out [corvus-migratorius/ansible-disk-quotas](https://github.com/corvus-migratorius/ansible-disk-quotas) for controlling non-root filesystem quotas.

Requirements
------------

- systemd
- openssh

Role Variables
--------------

`manifest_path`: a YAML file containing user definitions (see `molecule/default/users.yml` for an example)

`users`: a list of objects mirroring the YAML structure expected by `manifest_path`; takes precedence over it

`common_memory_max`: e.g. `"500M"`, optional

`common_swap_max`: e.g. `"2G"`, optional

`common_cpu_quota`: e.g. `"100%"`, optional

Dependencies
------------

Example Playbook
----------------

```yaml
- role: genlab.users
  manifest_path: "users.yml"
  def_pw_path: "def_pw.yml"
```

License
-------

BSD

Author Information
------------------

corvus-migratorius@proton.me
masayganova@gmail.com
