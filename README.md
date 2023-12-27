# kube-ansible

#### How to use

```bash
ansible-playbook -i inventory/k8s-servers.ini preinstall.yml  --become --become-method=sudo
```