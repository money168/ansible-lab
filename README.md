# ansiblelab




extra-vars:  
playbook設定主機群組或使用者.
---
- hosts: '{{ hosts }}'  
  remote_user: '{{ user }}'  
  
  tasks:
     - ...

ansible-playbook release.yml --extra-vars "hosts=vipers user=starbuck"  


service:
---
 - name: Start service httpd, if not started  
  ansible.builtin.service:  
    name: httpd  
    state: started  

- name: Stop service httpd, if started  
  ansible.builtin.service:  
    name: httpd  
    state: stopped  

- name: Restart service httpd, in all cases  
  ansible.builtin.service:  
    name: httpd  
    state: restarted  

- name: Reload service httpd, in all cases  
  ansible.builtin.service:  
    name: httpd  
    state: reloaded  

- name: Enable service httpd, and not touch the state  
  ansible.builtin.service:  
    name: httpd  
    enabled: yes  

- name: Start service foo, based on running process /usr/bin/foo  
  ansible.builtin.service:  
    name: foo  
    pattern: /usr/bin/foo  
    state: started  

- name: Restart network service for interface eth0  
  ansible.builtin.service:  
    name: network  
    state: restarted  
    args: eth0  
    
