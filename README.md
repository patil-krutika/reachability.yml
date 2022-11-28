# reachability.yml
---
- name: check server reachability
  hosts: 192.168.1.83
  tasks:
    - command: ping -c3 
      ignore_errors: true
      register: output
    - meta: end_host
      when: output.rc != 0
