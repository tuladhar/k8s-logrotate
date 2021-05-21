# k8s-logrotate
Ansible playbook to setup logrotate for on-prem Kubernetes master/worker nodes.

## Usage

Step 1. Create hosts inventory with your K8s nodes

File: hosts.ini
```
[k8s-nodes]
k8s-worker-1 10.0.0.1
k8s-worker-2 10.0.0.2
k8s-worker-2 10.0.1.3
```

Step 2. Run the ansible playbook
```
$ ansible-playbook -i hosts.ini k8s-logrotate.yaml
```

Step 3. Verify the logrotate files
```
$ cd /etc/logrotate.d
$ ls -lh
-rw-r--r--  1 root root  192 May 21 14:51 allcontainerlogs
-rw-r--r--  1 root root  186 May 21 14:51 allpodlogs
```
