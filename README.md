Role Name
=========

NCLU role to configure Cumulus Switches version 3.2+

Requirements
------------

Minimum of Ansible 2.3 and Cumulus Linux 3.2 releases.

Role Variables
--------------

Variable    | Description | Type | Default
------------|-------------|------|--------
`cl_license` | Cumulus license in a string format | String | ``
`commands` | Commands to run for all nclu devices | Array | `[]`
`group_commands` | Commands to run for all nclu devices to be used in group vars | Array | `[]`
`switchd_commands` | Commands that will restart switchd on nclu devices | Array | `[]`
`switchd_group_commands` | Commands that will restart switchd on nclu devices to be used in a group vars | Array | `[]`

Dependencies
------------

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - cumulus-nclu
      vars:
         - cumulus_nclu:
             switchd_commands:
               - add interface swp49 breakout 4x
             commands:
               - add hostname {{ ansible_hostname }}
               - add interface swp1 ip address 192.168.0.1/24
             cl_license: 'rocketturtle:102u309uofewauj'
             cumulus_license_file: /var/tmp/cl_license

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
