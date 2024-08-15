# Домашнее задание к занятию «Что такое DevOps. СI/СD»

### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в GitHub и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw.
   2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите сверху название занятия, ваши фамилию и имя;
      - в каждом задании добавьте решение в требуемом виде — текст, код, скриншоты, ссылка.
      - для корректного добавления скриншотов используйте [инструкцию «Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
      - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
   4. После завершения работы над домашним заданием сделайте коммит `git commit -m "comment"` и отправьте его на GitHub `git push origin`.
   5. Для проверки домашнего задания в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем GitHub.
   6. Любые вопросы по выполнению заданий задавайте в чате учебной группы или в разделе «Вопросы по заданию» в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!

---

### Задание 1

**Что нужно сделать:**

1. Установите себе jenkins по инструкции из лекции или любым другим способом из официальной документации. Использовать Docker в этом задании нежелательно.
2. Установите на машину с jenkins [golang](https://golang.org/doc/install).
3. Используя свой аккаунт на GitHub, сделайте себе форк [репозитория](https://github.com/netology-code/sdvps-materials.git). В этом же репозитории находится [дополнительный материал для выполнения ДЗ](https://github.com/netology-code/sdvps-materials/blob/main/CICD/8.2-hw.md).
3. Создайте в jenkins Freestyle Project, подключите получившийся репозиторий к нему и произведите запуск тестов и сборку проекта ```go test .``` и  ```docker build .```.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

скрин настроек
![img1](https://github.com/igoryanich94/dzDevOps_Netology/blob/main/img/img.png)
результат
```
Started by user admin
Running as SYSTEM
Building in workspace /var/lib/jenkins/workspace/DZSvetikovIA
The recommended git tool is: NONE
No credentials specified
Cloning the remote Git repository
Cloning repository https://github.com/igoryanich94/dzDevOps_Netology.git
 > git init /var/lib/jenkins/workspace/DZSvetikovIA # timeout=10
Fetching upstream changes from https://github.com/igoryanich94/dzDevOps_Netology.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/igoryanich94/dzDevOps_Netology.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/igoryanich94/dzDevOps_Netology.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
Avoid second fetch
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 223dbc3f489784448004e020f2ef224f17a7b06d (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 223dbc3f489784448004e020f2ef224f17a7b06d # timeout=10
Commit message: "Update README.md"
First time build. Skipping changelog.
[DZSvetikovIA] $ /bin/sh -xe /tmp/jenkins10447997208658840044.sh
+ /usr/local/go/bin/go test .
ok  	github.com/netology-code/sdvps-materials	0.005s
+ docker build . -t ubuntu-bionic:8082/hello-world:v1
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  250.9kB

Step 1/8 : FROM golang:1.16 AS builder
1.16: Pulling from library/golang
e4d61adff207: Pulling fs layer
4ff1945c672b: Pulling fs layer
ff5b10aec998: Pulling fs layer
12de8c754e45: Pulling fs layer
8c86ff77a317: Pulling fs layer
0395a1c478ba: Pulling fs layer
245345d44ed8: Pulling fs layer
12de8c754e45: Waiting
8c86ff77a317: Waiting
0395a1c478ba: Waiting
245345d44ed8: Waiting
4ff1945c672b: Verifying Checksum
4ff1945c672b: Download complete
ff5b10aec998: Verifying Checksum
ff5b10aec998: Download complete
e4d61adff207: Verifying Checksum
e4d61adff207: Download complete
12de8c754e45: Verifying Checksum
12de8c754e45: Download complete
245345d44ed8: Verifying Checksum
245345d44ed8: Download complete
8c86ff77a317: Verifying Checksum
8c86ff77a317: Download complete
0395a1c478ba: Verifying Checksum
0395a1c478ba: Download complete
e4d61adff207: Pull complete
4ff1945c672b: Pull complete
ff5b10aec998: Pull complete
12de8c754e45: Pull complete
8c86ff77a317: Pull complete
0395a1c478ba: Pull complete
245345d44ed8: Pull complete
Digest: sha256:5f6a4662de3efc6d6bb812d02e9de3d8698eea16b8eb7281f03e6f3e8383018e
Status: Downloaded newer image for golang:1.16
 ---> 972d8c0bc0fc
Step 2/8 : WORKDIR $GOPATH/src/github.com/netology-code/sdvps-materials
 ---> Running in 693a8ea94dbe
Removing intermediate container 693a8ea94dbe
 ---> a93bf4fea683
Step 3/8 : COPY . ./
 ---> d29a1a5efe17
Step 4/8 : RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
 ---> Running in b514d8034eb5
Removing intermediate container b514d8034eb5
 ---> 83361e2fdda5
Step 5/8 : FROM alpine:latest
latest: Pulling from library/alpine
c6a83fedfae6: Pulling fs layer
c6a83fedfae6: Verifying Checksum
c6a83fedfae6: Download complete
c6a83fedfae6: Pull complete
Digest: sha256:0a4eaa0eecf5f8c050e5bba433f58c052be7587ee8af3e8b3910ef9ab5fbe9f5
Status: Downloaded newer image for alpine:latest
 ---> 324bc02ae123
Step 6/8 : RUN apk -U add ca-certificates
 ---> Running in 2b514f5c8f0b
fetch https://dl-cdn.alpinelinux.org/alpine/v3.20/main/x86_64/APKINDEX.tar.gz
fetch https://dl-cdn.alpinelinux.org/alpine/v3.20/community/x86_64/APKINDEX.tar.gz
(1/1) Installing ca-certificates (20240705-r0)
Executing busybox-1.36.1-r29.trigger
Executing ca-certificates-20240705-r0.trigger
OK: 8 MiB in 15 packages
Removing intermediate container 2b514f5c8f0b
 ---> 2381d59d139b
Step 7/8 : COPY --from=builder /app /app
 ---> d05205f5ce5d
Step 8/8 : CMD ["/app"]
 ---> Running in 489dd834ddcc
Removing intermediate container 489dd834ddcc
 ---> 40fbea6a5a83
Successfully built 40fbea6a5a83
Successfully tagged ubuntu-bionic:8082/hello-world:v1
Finished: SUCCESS
```

---

### Задание 2

**Что нужно сделать:**

1. Создайте новый проект pipeline.
2. Перепишите сборку из задания 1 на declarative в виде кода.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

код

```
pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git 'https://github.com/netology-code/sdvps-materials.git'}
  }
  stage('Test') {
   steps {
    sh 'go test .'
   }
  }
  stage('Build') {
   steps {
    sh 'docker build . -t ubuntu-bionic:8082/hello-world:v$BUILD_NUMBER'
   }
  }
 }
}
```

результат

```
Started by user admin
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/pipeline_task2
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Git)
[Pipeline] git
The recommended git tool is: NONE
No credentials specified
Cloning the remote Git repository
Cloning repository https://github.com/netology-code/sdvps-materials.git
 > git init /var/lib/jenkins/workspace/pipeline_task2 # timeout=10
Fetching upstream changes from https://github.com/netology-code/sdvps-materials.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/netology-code/sdvps-materials.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/netology-code/sdvps-materials.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
Avoid second fetch
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision da5acf7bcb7f437637adf06fbd03a24dc2c8f13e (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f da5acf7bcb7f437637adf06fbd03a24dc2c8f13e # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git checkout -b master da5acf7bcb7f437637adf06fbd03a24dc2c8f13e # timeout=10
Commit message: "branch main, add creds for vagrant box"
First time build. Skipping changelog.
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] sh
+ go test .
ok  	github.com/netology-code/sdvps-materials	0.007s
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] sh
+ docker build . -t ubuntu-bionic:8082/hello-world:v3
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  242.2kB

Step 1/8 : FROM golang:1.16 AS builder
 ---> 972d8c0bc0fc
Step 2/8 : WORKDIR $GOPATH/src/github.com/netology-code/sdvps-materials
 ---> Using cache
 ---> a93bf4fea683
Step 3/8 : COPY . ./
 ---> cd98e61970a1
Step 4/8 : RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
 ---> Running in b0340f60048d
Removing intermediate container b0340f60048d
 ---> b705619316d1
Step 5/8 : FROM alpine:latest
 ---> 324bc02ae123
Step 6/8 : RUN apk -U add ca-certificates
 ---> Using cache
 ---> 2381d59d139b
Step 7/8 : COPY --from=builder /app /app
 ---> Using cache
 ---> d05205f5ce5d
Step 8/8 : CMD ["/app"]
 ---> Using cache
 ---> 40fbea6a5a83
Successfully built 40fbea6a5a83
Successfully tagged ubuntu-bionic:8082/hello-world:v3
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```

---

### Задание 3

**Что нужно сделать:**

1. Установите на машину Nexus.
1. Создайте raw-hosted репозиторий.
1. Измените pipeline так, чтобы вместо Docker-образа собирался бинарный go-файл. Команду можно скопировать из Dockerfile.
1. Загрузите файл в репозиторий с помощью jenkins.

pipeline
```
pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git 'https://github.com/netology-code/sdvps-materials.git'}
  }
  stage('Test') {
   steps {
    sh 'go test .'
   }
  }
  stage('Build') {
   steps {
     sh 'docker build . -t 172.17.0.1:8082/hello-world:v$BUILD_NUMBER'
   }
  }
  stage('Push') {
   steps {
     sh 'docker login 172.17.0.1:8082 -u admin -p admin && docker push 172.17.0.1:8082/hello-world:v$BUILD_NUMBER && docker logout'  
     sh 'curl -u admin:admin http://172.17.0.1:8081/repository/helm-test/ --upload-file Vagrantfile'
       
   }
    
  }
 }
}
```

результат
```
Started by user admin
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/dz3pipeline
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Git)
[Pipeline] git
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/dz3pipeline/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/netology-code/sdvps-materials.git # timeout=10
Fetching upstream changes from https://github.com/netology-code/sdvps-materials.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/netology-code/sdvps-materials.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision da5acf7bcb7f437637adf06fbd03a24dc2c8f13e (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f da5acf7bcb7f437637adf06fbd03a24dc2c8f13e # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git branch -D master # timeout=10
 > git checkout -b master da5acf7bcb7f437637adf06fbd03a24dc2c8f13e # timeout=10
Commit message: "branch main, add creds for vagrant box"
 > git rev-list --no-walk da5acf7bcb7f437637adf06fbd03a24dc2c8f13e # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] sh
+ go test .
ok  	github.com/netology-code/sdvps-materials	(cached)
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] sh
+ docker build . -t 172.17.0.1:8082/hello-world:v63
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  4.047MB

Step 1/8 : FROM golang:1.16 AS builder
 ---> 972d8c0bc0fc
Step 2/8 : WORKDIR $GOPATH/src/github.com/netology-code/sdvps-materials
 ---> Using cache
 ---> a93bf4fea683
Step 3/8 : COPY . ./
 ---> 4dd3867486d3
Step 4/8 : RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
 ---> Running in 6576a4932efe
Removing intermediate container 6576a4932efe
 ---> 019c86026e3b
Step 5/8 : FROM alpine:latest
 ---> 324bc02ae123
Step 6/8 : RUN apk -U add ca-certificates
 ---> Using cache
 ---> 2381d59d139b
Step 7/8 : COPY --from=builder /app /app
 ---> Using cache
 ---> d05205f5ce5d
Step 8/8 : CMD ["/app"]
 ---> Using cache
 ---> 40fbea6a5a83
Successfully built 40fbea6a5a83
Successfully tagged 172.17.0.1:8082/hello-world:v63
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Push)
[Pipeline] sh
+ docker login 172.17.0.1:8082 -u admin -p admin
WARNING! Using --password via the CLI is insecure. Use --password-stdin.
WARNING! Your password will be stored unencrypted in /var/lib/jenkins/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
+ docker push 172.17.0.1:8082/hello-world:v63
The push refers to repository [172.17.0.1:8082/hello-world]
086792e19fe0: Preparing
d068c4b439c4: Preparing
78561cef0761: Preparing
d068c4b439c4: Layer already exists
78561cef0761: Layer already exists
086792e19fe0: Layer already exists
v63: digest: sha256:526b0a7dc8b8a24960e6acd1c88ee8060490bbd76d02afd36b80052f0352d52e size: 950
+ docker logout
Removing login credentials for https://index.docker.io/v1/
[Pipeline] sh
+ curl -u admin:admin http://172.17.0.1:8081/repository/helm-test/ --upload-file Vagrantfile
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed

  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100  4460    0     0  100  4460      0   140k --:--:-- --:--:-- --:--:--  150k
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

---
## Дополнительные задания* (со звёздочкой)

Их выполнение необязательное и не влияет на получение зачёта по домашнему заданию. Можете их решить, если хотите лучше разобраться в материале.

---

### Задание 4* (Не делал)

Придумайте способ версионировать приложение, чтобы каждый следующий запуск сборки присваивал имени файла новую версию. Таким образом, в репозитории Nexus будет храниться история релизов.

Подсказка: используйте переменную BUILD_NUMBER.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.
