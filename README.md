Role Name
=========

Create user accounts according to a YAML manifest.

Controls:
  - username and UID
  - groupname and GID
  - homedir creation
  - GECOS field (typically full user name)
  - shell
  - SSH public key deployment to `.ssh/authorized_keys`

Sets a default password and enforces password change on the first login.

Requirements
------------

Role Variables
--------------

`manifest_path`: YAML file containing user definitions (see `molecule/default/users.yml`)
`def_pw_path`: YAML file containing default user password and salt (see `molecule/default/def_pw.yml`)

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
