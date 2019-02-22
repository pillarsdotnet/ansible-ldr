Common
======

Tasks that are common to all instances, regardless of type.

Role Variables
--------------

Set in [`defaults`](defaults/main.yml):
- `common_os_patterns`
  Ordered list of operating-system strings used to generate filenames for [include_vars](https://docs.ansible.com/ansible/latest/modules/include_vars_module.html#include-vars-module).

Set in an included [`os_vars`](../../os_vars) file:
- `os_pips`
  Ordered list of python-packages to be installed.
- `os_pkgs`
  Ordered list of os-packages to be installed.
- `os_roles`
  Ordered list of roles to be invoked for every instance.

Override in a [`group_vars`](../../group_vars) file:
- `common_pips_enable`
  Set to `true` to install `os_pips` and `group_pips` via [common](roles/common/pip.yml) role; defaults to `false`.
- `common_pkgs_enable`
  Set to `true` to install `os_pkgs` and `group_pkgs` via [common](roles/common/package.yml) role; defaults to `false`.
- `common_roles_enable`
  Set to `true` to apply `os_roles` and `group_roles` via [common](roles/common/main.yml) role; defaults to `false`.
- `group_pips`
  Ordered list of python-packages to be installed for a particular role.
- `group_pkgs`
  Ordered list of os-packages to be installed for a particular role.
- `group_roles`
  Ordered list of roles to be invoked for a particular kind of instance.


Dependencies
------------

- Reads os-specific vars from the [`os_vars`](../../os_vars) top-level directory.
- Invokes other roles as configured in [`group_vars`](../../group_vars).

Example Playbook
----------------

See [`site.yml`](../../site.yml)

Author Information
------------------

Robert August Vincent II  
*(pronounced "Bob" or "Bob-Vee")*  
Security Operations Division  
Office of the Chief Information Security Officer  
U.S. General Services Administration  
Contractor - Team Valiant  
