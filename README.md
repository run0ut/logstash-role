Ansible-Role Logstash for CentOS 7
=========

Role installs Logstash on CentOS 7. 

Tested on CentOS 7.9.2009 (Core).

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

* Description
  ```yml
  var: "7.14.0"
  ```

Dependencies
------------

None.

Example Playbook
----------------

The simpliest example:
```yaml
- name: Install Logstash
  roles:
    - logstash-role
```
Below is more complete example with variables.
```yaml
- name: Install Logstash
  hosts: el
  vars:
    - filebeat_elasticsearch_url: ["http://{{ hostvars['el-instance']['ansible_facts']['default_ipv4']['address'] }}:9200/"]
    - filebeat_kibana_url:  "http://{{ hostvars['k-instance']['ansible_facts']['default_ipv4']['address'] }}:5601"
    - kibana_version: "7.14.0"
  roles:
    - logstash-role
  tags: logstash
```

License
-------

MIT

Author Information
------------------

The role was created by Sergey Shadurskiy in 2022/02 as a homework during a 10-month DevOps cource on Netology online educational platform.
