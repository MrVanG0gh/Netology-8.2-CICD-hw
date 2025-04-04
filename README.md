# Netology-8.2-CICD-hw

# Домашнее задание к занятию "`CI/CD`" - `Иншаков Владимир`

### Задание 1

1. `Установите себе jenkins по инструкции из лекции или любым другим способом из официальной документации. Использовать Docker в этом задании нежелательно.`
2. `Установите на машину с jenkins golang.`
3. `Используя свой аккаунт на GitHub, сделайте себе форк репозитория. В этом же репозитории находится дополнительный материал для выполнения ДЗ.
Создайте в jenkins Freestyle Project, подключите получившийся репозиторий к нему и произведите запуск тестов и сборку проекта go test . и docker build ..`
4. `В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.`

![Screenshot_1](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex1_1.png)
![Screenshot_2](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex1_2.png)
![Screenshot_3](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex1_3.png)
![Screenshot_4](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex1_4.png)
![Screenshot_5](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex1_5.png)
![Screenshot_6](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex1_6.png)
![Screenshot_7](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex1_7.png)


'Started by user van

Running as SYSTEM
Building in workspace /var/lib/jenkins/workspace/Ex_01
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/Ex_01/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/MrVanG0gh/sdvps-materials.git/ # timeout=10
Fetching upstream changes from https://github.com/MrVanG0gh/sdvps-materials.git/
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/MrVanG0gh/sdvps-materials.git/ +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 223dbc3f489784448004e020f2ef224f17a7b06d (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 223dbc3f489784448004e020f2ef224f17a7b06d # timeout=10
Commit message: "Update README.md"
 > git rev-list --no-walk 223dbc3f489784448004e020f2ef224f17a7b06d # timeout=10
[Ex_01] $ /bin/sh -xe /tmp/jenkins17167753382176452219.sh
+ go test .
ok  	github.com/netology-code/sdvps-materials	(cached)
[Ex_01] $ /bin/sh -xe /tmp/jenkins6851789586664908469.sh
+ docker build . -t ubuntu-bionic:8082/hello-world:v6
#0 building with "default" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 350B done
#1 DONE 0.0s

#2 [internal] load metadata for docker.io/library/alpine:latest
#2 ...

#3 [internal] load metadata for docker.io/library/golang:1.16
#3 DONE 1.1s

#2 [internal] load metadata for docker.io/library/alpine:latest
#2 DONE 1.1s

#4 [internal] load .dockerignore
#4 transferring context: 2B done
#4 DONE 0.0s

#5 [builder 1/4] FROM docker.io/library/golang:1.16@sha256:5f6a4662de3efc6d6bb812d02e9de3d8698eea16b8eb7281f03e6f3e8383018e
#5 DONE 0.0s

#6 [stage-1 1/3] FROM docker.io/library/alpine:latest@sha256:a8560b36e8b8210634f77d9f7f9efd7ffa463e380b75e2e74aff4511df3ef88c
#6 DONE 0.0s

#7 [internal] load build context
#7 transferring context: 13.24kB 0.0s done
#7 DONE 0.0s

#8 [stage-1 2/3] RUN apk -U add ca-certificates
#8 CACHED

#9 [builder 3/4] COPY . ./
#9 CACHED

#10 [builder 4/4] RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
#10 CACHED

#11 [builder 2/4] WORKDIR /go/src/github.com/netology-code/sdvps-materials
#11 CACHED

#12 [stage-1 3/3] COPY --from=builder /app /app
#12 CACHED

#13 exporting to image
#13 exporting layers done
#13 writing image sha256:75adf8565d3c2390aec1f256ba6e13d5ed93d731918e9c92f37712eca99788d2 done
#13 naming to ubuntu-bionic:8082/hello-world:v6 done
#13 DONE 0.0s
Finished: SUCCESS'

---

### Задание 2

1. `Создайте новый проект pipeline.`
2. `Перепишите сборку из задания 1 на declarative в виде кода.`
3. `В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.`

![Screenshot_1](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex2_1.png)
![Screenshot_2](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex2_2.png)
![Screenshot_3](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex2_3.png)
![Screenshot_4](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex2_4.png)


Started by user van

[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins
 in /var/lib/jenkins/workspace/Ex_02
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Git)
[Pipeline] git
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/Ex_02/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/netology-code/sdvps-materials.git # timeout=10
Fetching upstream changes from https://github.com/netology-code/sdvps-materials.git
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/netology-code/sdvps-materials.git +refs/heads/*:refs/remotes/origin/* # timeout=10
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
ok  	github.com/netology-code/sdvps-materials	0.003s
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] sh
+ docker build . -t ubuntu-bionic:8082/hello-world:v5
#0 building with "default" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 350B 0.0s done
#1 DONE 0.0s

#2 [internal] load metadata for docker.io/library/alpine:latest
#2 DONE 1.2s

#3 [internal] load metadata for docker.io/library/golang:1.16
#3 DONE 1.2s

#4 [internal] load .dockerignore
#4 transferring context: 2B done
#4 DONE 0.0s

#5 [builder 1/4] FROM docker.io/library/golang:1.16@sha256:5f6a4662de3efc6d6bb812d02e9de3d8698eea16b8eb7281f03e6f3e8383018e
#5 DONE 0.0s

#6 [stage-1 1/3] FROM docker.io/library/alpine:latest@sha256:a8560b36e8b8210634f77d9f7f9efd7ffa463e380b75e2e74aff4511df3ef88c
#6 DONE 0.0s

#7 [internal] load build context
#7 transferring context: 98.51kB 0.1s done
#7 DONE 0.1s

#8 [builder 2/4] WORKDIR /go/src/github.com/netology-code/sdvps-materials
#8 CACHED

#9 [builder 3/4] COPY . ./
#9 DONE 0.2s

#10 [builder 4/4] RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
#10 DONE 6.4s

#11 [stage-1 2/3] RUN apk -U add ca-certificates
#11 CACHED

#12 [stage-1 3/3] COPY --from=builder /app /app
#12 CACHED

#13 exporting to image
#13 exporting layers done
#13 writing image sha256:75adf8565d3c2390aec1f256ba6e13d5ed93d731918e9c92f37712eca99788d2 done
#13 naming to ubuntu-bionic:8082/hello-world:v5 done
#13 DONE 0.0s
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS


---

### Задание 3

1. `Установите на машину Nexus.`
2. `Создайте raw-hosted репозиторий.`
3. `Измените pipeline так, чтобы вместо Docker-образа собирался бинарный go-файл. Команду можно скопировать из Dockerfile.`
4. `Загрузите файл в репозиторий с помощью jenkins.`
5. `В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.`

![Screenshot_1](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex3_1.png)
![Screenshot_2](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex3_2.png)
![Screenshot_3](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex3_3.png)
![Screenshot_4](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex3_4.png)
![Screenshot_5](https://github.com/MrVanG0gh/Netology-8.2-CICD-hw/blob/main/Ex3_5.png)

Started by user van

[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins
 in /var/lib/jenkins/workspace/Ex_03
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Git)
[Pipeline] git
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/Ex_03/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/netology-code/sdvps-materials.git # timeout=10
Fetching upstream changes from https://github.com/netology-code/sdvps-materials.git
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
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
+ go build .
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Push)
[Pipeline] sh
+ curl -u admin:admin http://localhost:8081/repository/raw-hosted/ --upload-file sdvps-materials -v
* Host localhost:8081 was resolved.
* IPv6: ::1
* IPv4: 127.0.0.1
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed

  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying [::1]:8081...
* Connected to localhost (::1) port 8081
* Server auth using Basic with user 'admin'
> PUT /repository/raw-hosted/sdvps-materials HTTP/1.1
> Host: localhost:8081
> Authorization: Basic YWRtaW46YWRtaW4=
> User-Agent: curl/8.5.0
> Accept: */*
> Content-Length: 2050207
> Expect: 100-continue
> 
< HTTP/1.1 100 Continue
} [65536 bytes data]
* We are completely uploaded and fine
< HTTP/1.1 201 Created
< Date: Tue, 01 Apr 2025 21:19:52 GMT
< Server: Nexus/3.79.0-09 (COMMUNITY)
< X-Content-Type-Options: nosniff
< Content-Security-Policy: sandbox allow-forms allow-modals allow-popups allow-presentation allow-scripts allow-top-navigation
< X-XSS-Protection: 1; mode=block
< Content-Length: 0
< 

100 2002k    0     0  100 2002k      0  2558k --:--:-- --:--:-- --:--:-- 2557k
100 2002k    0     0  100 2002k      0  2558k --:--:-- --:--:-- --:--:-- 2557k
* Connection #0 to host localhost left intact
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS



