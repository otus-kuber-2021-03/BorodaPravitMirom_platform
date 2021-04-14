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

## Домашняя работа 2
### Почему ReplicaSet не обновляет запущенные поды
Replicaset не следит за соответсвие подов шаблону, только за количество запущенных реплик

### Написать ReplicaSet  и Deployment для frontend и payment 
Созданы yaml файлы с описанием 

### Написать blue-green и reverse обновление с параметрами maxUnavailable maxSurge
Созданы yaml файлы с описанием, bg - paymentservice-deployment-bg, reverse - paymentservice-deployment-reverse

### Probes
Добавлен в  frontend-deployment

### DaemonSet Node-Exporter
Создан yaml node-exporter-daemonset

### DaemonSet на master
Добавлен параметр tolerations в node-exporter-daemonset
#Test

## Домашняя работа 3
### Task01
Создан сервисный аккаунт Боб с правами cluster-admin
Создан сервисный аккаунт Dave без прав
### Task02
Создан ns promhetheus
Создан сервисный аккаунт carol
Создана роль в кластере и предоставлена всем сервисным аккаунтам в ns prometheus
### Task03
Создан ns dev
Создан сервисный jane аккаунт с правам админа в рамках ns dev
Создан сервисный аккаунт ken с правами на просмотр в рамках ns dev

## Домашняя работа 4

###Применить statefulset

Применил minio-statefulset.yaml

###Применить service

Применил minio-headless-service.yaml

###Создать secret

Создал secret обявил их в statefulset

