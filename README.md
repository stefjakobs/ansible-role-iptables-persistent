iptables-persistent
===================

manage iptables and ip6tables rules.

Requirements
------------

Ansible 2.2+ on a Debian-based system

Role Variables
--------------

    iptables_persistent_ipv4: Dictionary of chains and rules
    iptables_persistent_ipv6: Dictionary of chains and rules

Dependencies
------------

None

Example Playbook
----------------

    - hosts: myserver
      roles:
      - role: iptables-persistent
        iptables_persistent_ipv4:
          'INPUT':
          - comment: 'allow http traffic'
            protocol: tcp
            destination_port: 80
            jump: ACCEPT
          - comment: 'drop all other traffic'
            policy: DROP
        iptables_persistent_ipv6: "{{ iptables_persistent_ipv4 }}"

License
-------

MIT
