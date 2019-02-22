Common
======

Tasks that are common to all instances, regardless of type.

Role Variables
--------------

Set in [`defaults`](defaults/main.yml):
- `common_os_patterns`
  Ordered list of operating-system strings used to generate filenames for [include_vars](https://docs.ansible.com/ansible/latest/modules/include_vars_module.html#include-vars-module).

Set in an included `vars/os` file:
- `common_os_pips`
  Ordered list of python-packages to be installed.
- `common_os_pkgs`
  Ordered list of os-packages to be installed.
- `common_os_roles`
  Ordered list of roles to be invoked for every instance.

Override in a [`group_vars`](../../group_vars) file:
- `common_pips_enable`
  Set to `true` to install `common_os_pips` and `common_app_pips` via [common](roles/common/pip.yml) role; defaults to `false`.
- `common_pkgs_enable`
  Set to `true` to install `common_os_pkgs` and `common_app_pkgs` via [common](roles/common/package.yml) role; defaults to `false`.
- `common_roles_enable`
  Set to `true` to apply `common_os_roles` and `common_app_roles` via [common](roles/common/main.yml) role; defaults to `false`.
- `common_app_pips`
  Ordered list of python-packages to be installed for a particular application tag.
- `common_app_pkgs`
  Ordered list of os-packages to be installed for a particular application tag.
- `common_app_roles`
  Ordered list of roles to be invoked for a particular application tag.


Dependencies
------------

- Reads os-specific vars from the `vars/os` top-level directory.
- Invokes other roles as configured.

Example Playbook
----------------

See [`ansible-master/site.yml`](/GSASecOps/ansible-master/blob/master/site.yml)

Author Information
------------------

Robert August Vincent II  
*(pronounced "Bob" or "Bob-Vee")*  
Security Operations Division  
Office of the Chief Information Security Officer  
U.S. General Services Administration  
Contractor - Team Valiant  
