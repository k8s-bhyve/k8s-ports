1) Clone repo

```
git clone https://github.com/k8s-bhyve/k8s-ports.git /root/k8s-ports
```

2) Create overlays vars for ClonOS ports

```
echo 'OVERLAYS=/root/k8s-ports' >> /etc/make.conf
```

3) Install!

```
env BATCH=no make -C /usr/ports/sysutils/cbsd-mq-router install
env BATCH=no make -C /usr/ports/sysutils/k8s-mq-api install
```
