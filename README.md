# kube-ansible

#### How to use

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes  --become --become-method=sudo
```

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t join_worker -l k8s-test-worker1
```