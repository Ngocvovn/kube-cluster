# kube-cluster

Create a K8S cluster with 1 control plane and 2 worker nodes.

1. Create a file called `hosts` and add access credentials to that file. 
 ```
[control_plane]
control1 ansible_host=control_plane_ip ansible_user=root 

[workers]
worker1 ansible_host=worker_1_ip ansible_user=root
worker2 ansible_host=worker_2_ip ansible_user=root

[all:vars]
ansible_python_interpreter=/usr/bin/python3

 ```
 2. `ansible-playbook -i hosts ~/kube-cluster/initial.yml`

 3. `ansible-playbook -i hosts ~/kube-cluster/kube-dependencies.yml`

 4. `ansible-playbook -i hosts ~/kube-cluster/control-plane.yml`

 5. `ansible-playbook -i hosts ~/kube-cluster/workers.yml`
