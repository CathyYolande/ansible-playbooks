# create_multiple_users.yml
---
- name: Create multiple users on Ansible managed servers
  hosts: all
  become: yes

  vars_files:
    - users.yml

  tasks:
    - name: Ensure multiple users are present
      user:
        name: "{{ item.name }}"
        state: "present"
        #groups: "{{ item.groups }}"
        create_home: yes
        shell: "/bin/bash"
        password: "{{ item.password }}"
      loop: "{{ users }}"
