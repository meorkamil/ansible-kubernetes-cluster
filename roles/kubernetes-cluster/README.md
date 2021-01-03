# Role Name

kubernetes-cluster

## Configuration

Below are the example for running this ansible role

playbook.yml

  ```  
    - name: Kubernetes Cluster Installation
      hosts: kube-node #including master node
      roles:
        - role: kubernetes-cluster
          user: kubeadmin # default user is kubeadmin
  ```

ansible.cfg:

  ```  
    [defaults]
    remote_user=sysadmin
    host_key_checking=false
    inventory=inventory

    [privilege_escalation]
    become=true
    become_method=sudo
    become_user=root
    become_ask_pass=false
  ```

inventory:

  ```  
    [master-node]
    master

    [worker-node]
    worker1
    worker2

    [kube-node:children]
    master-node
    worker-node
 ```
## Author Information

Algojo (Meor Muhammad Kamil).
