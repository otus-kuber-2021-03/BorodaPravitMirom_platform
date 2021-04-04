# BorodaPravitMirom_platform
##BorodaPravitMirom Platform repository

## Домашняя работа 1
### Разобраться почему все pod в namespace kube-system восстановились после удаления.

**core-dns** - реализован как Deployment с параметром replicas: 2. При его удалении ReplicaSet восстанавливает его работу

**kube-proxy** управляется и создается Daemonset.

**kube-apiserver**, **etcd**, **kube-controller-manager**, **kube-scheduler** - запускает kubelet ноды (/etc/kubernetes/manifests/)

### Создать web-pod
Создан Dockerfile и образ залит на DockerHub. 

Создан файл манифеста содержащий в себе контейнер с собранным образом и инициализирующий контейнер(за основу взят busybox) и запущен под. Пробрасываем подключение к поду и убеждаемся в его работоспособности
```
kubectl port-forward --address 0.0.0.0 pod/web 8000:8000
```

### Запустить фронт Hipster shop и разрабораться с ошибкой
Под не запускался из-за отсутсвия переменных окружений.

