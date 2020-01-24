ANSIBLE-ROLE-GROUPS
===================

Ansible role add/remove linux group


## Howto use this role?
This role need to be include in a playbook. 

Call this **Galaxy** role  like this:

````bash
ansible-galaxy install -r requirements.yml 
````

Inside requirements.yml
````yaml
# from GitHub, overriding the name and specifying a specific tag
- src: redbeard28.groups
````

More info => [Ansible Docs](https://docs.ansible.com/ansible-container/roles/access.html)

## Requirements

 * Ansible 2.9+


Role Variables
--------------

```yaml
---
mygroups:
  - { name: 'toto', gid: 1000 , state: 'present' }
  - { name: 'tata', state: 'present' }
  - { name: 'titi', state: 'absent' }
```

First line define a group with a specefic gid.
Second line define a group with leting the system to generate the gid.


| Paramter | Choices/Defaults                  | Comments                                                       | Mandatory |
|:--------:|-----------------------------------|----------------------------------------------------------------|-----------|
| gid      |                                   | Optional GID to set for the Group                              | No
| name     |                                   | Namle of the group to manage                                   | Yes       |
| state    | absent or present← default| Whether the group should be present or not on the remote host. | Yes        |

Dependencies
------------

none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: redbeard28.groups, tags: mytags }


Molecule testing framework
--------------------------

You can use molecule to test this role.
```bash
image=debian tag="buster" molecule converge 
image=debian tag="buster" molecule verify 
```

Author Information
------------------

Jeremie CUADRADO[¹](mailto:info@redbeard-consulting.fr) from Redbeard-Consulting
