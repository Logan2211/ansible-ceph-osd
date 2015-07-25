# Ansible role: Ceph OSD

This role bootstraps Ceph OSD(s).
It can bootstrap dockerized Ceph OSD(s).

# Requirements

Nothing, it runs out of the box.

# Role variables

Have a look at: `defaults/main.yml`.

## Mandatory variables

Choose between the following scenario to configure your OSDs, **choose only one**:

* `journal_collocation`
* `raw_multi_journal`
* `osd_directory`

Then:

* `devices`
* `raw_journal_devices` (**only if** you activated `raw_multi_journal`)
* `osd_directories` (**only if** you activated `osd_directory`)

# Dependencies

The role `leseb.ceph-common` must be installed.

# Example Playbook

```
- hosts: servers
  remote_user: ubuntu
  roles:
     - { role: leseb.ceph-osd }
```

# License

Apache

# Author Information

This role was created by [Sébastien Han](http://sebastien-han.fr/).
