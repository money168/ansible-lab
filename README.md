# ansiblelab


paybook設定主機群組或使用者.

Example:
---
- hosts: '{{ hosts }}'
  remote_user: '{{ user }}'

  tasks:
     - ...

ansible-playbook release.yml --extra-vars "hosts=vipers user=starbuck"  
