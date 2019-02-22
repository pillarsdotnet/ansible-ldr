Loader
======

Loads variables, packages, pips, and other roles.

Role Variables
--------------

Set in [`defaults`](defaults/main.yml):
- `ldr_os_patterns`
  Ordered list of operating-system strings used to generate filenames for [include_vars](https://docs.ansible.com/ansible/latest/modules/include_vars_module.html#include-vars-module).

Set in an included `vars/os` file:
- `ldr_os_pips`
  Ordered list of python-packages to be installed.
- `ldr_os_pkgs`
  Ordered list of os-packages to be installed.
- `ldr_os_roles`
  Ordered list of roles to be invoked for every instance.

Override in a [`group_vars`](../../group_vars) file:
- `ldr_pip_enable`
  Set to `true` to install `ldr_os_pips` and `ldr_app_pips`; defaults to `false`.
- `ldr_pkg_enable`
  Set to `true` to install `ldr_os_pkgs` and `ldr_app_pkgs`; defaults to `false`.
- `ldr_role_enable`
  Set to `true` to apply `ldr_os_roles` and `ldr_app_roles`; defaults to `false`.
- `ldr_app_pips`
  Ordered list of python-packages to be installed for a particular application tag.
- `ldr_app_pkgs`
  Ordered list of os-packages to be installed for a particular application tag.
- `ldr_app_roles`
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
