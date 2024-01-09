# kube-ansible

#### How to use

For Install kubernetes you need some preinstall task, for preinstall follow these steps

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t preinstall
```

After that you should install prerequired packages for kubernetes:

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t k8s
```

For initialize kubernetes, follow these steps: (It's for new cluster)

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t init_k8s
```

For join master(s) node to cluster, follow these steps:

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t join_master
```

For join worker(s) node to cluster, follow these steps:

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t join_worker
```

And also you can limit your task to specific host:

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t join_worker -l k8s-test-worker1
```

Finaly you should run postinstall task:

```bash
ansible-playbook -i inventory/k8s-servers.ini kubernetes.yml  --become --become-method=sudo -t postinstall
```
