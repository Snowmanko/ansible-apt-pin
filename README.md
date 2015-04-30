apt-pin
=======

Creates APT preferences pin files.

Example Playbook
----------------

```
- hosts: all
  roles:
    - role: ssilab.apt-pin
      apt_pins:
        - default: 'release v=14.04,l=Ubuntu'
          priority: 1000
        - source: 'release o=Debian,a=unstable,c=main'
          pin_rest: true
          priority: 200
          packages:
            - pattern: '*zookeeper*'
              priority: 1001
```

Here we're specifying that packages should come from the Ubuntu 14.04 repo
by default, except for Zookeeper packages which should come from Debian unstable.
The `priority` and `pin_rest` values listed are the same as the defaults and can
be left out.

License
-------

BSD. See LICENSE.
