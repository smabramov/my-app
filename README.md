# my-app - Абрамов Сергей

Создал на DockerHub репозторий smabramovvv/my-app
Создал статичную web-страницу.
Создал Dockerfile.

[my-app]()

Зашел на DockerHub под своим логином и паролем:

```
serg@debian:~/git/my-app$ docker login -u smabramovvv
Password: 
WARNING! Your password will be stored unencrypted in /home/serg/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credential-stores

Login Succeeded
```

Создал docker образ и запушил образ на Hub, после запустил контейнер:

```
serg@debian:~/git/my-app$ docker build . -t smabramovvv/my-app:1.1.1
[+] Building 10.7s (9/9) FINISHED                                                                                      docker:default
 => [internal] load build definition from Dockerfile                                                                             0.0s
 => => transferring dockerfile: 138B                                                                                             0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                                                  2.1s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                                     0.0s
 => [internal] load .dockerignore                                                                                                0.0s
 => => transferring context: 2B                                                                                                  0.0s
 => [1/3] FROM docker.io/library/nginx:latest@sha256:0a399eb16751829e1af26fea27b20c3ec28d7ab1fb72182879dcae1cca21206a            8.1s
 => => resolve docker.io/library/nginx:latest@sha256:0a399eb16751829e1af26fea27b20c3ec28d7ab1fb72182879dcae1cca21206a            0.0s
 => => sha256:2426c815287ed75a3a33dd28512eba4f0f783946844209ccf3fa8990817a4eb9 2.29kB / 2.29kB                                   0.0s
 => => sha256:9bea9f2796e236cb18c2b3ad561ff29f655d1001f9ec7247a0bc5e08d25652a1 8.58kB / 8.58kB                                   0.0s
 => => sha256:af302e5c37e9dc1dbe2eadc8f5059d82a914066b541b0d1a6daa91d0cc55057d 28.21MB / 28.21MB                                 5.2s
 => => sha256:0a399eb16751829e1af26fea27b20c3ec28d7ab1fb72182879dcae1cca21206a 10.27kB / 10.27kB                                 0.0s
 => => sha256:207b812743af01771d6c94b3ebc59543bf3c6fefe5d4d9ebfa6e5e5558801d34 43.84MB / 43.84MB                                 7.3s
 => => sha256:841e383b441eda86c164d8e833da080b951c951d612853cac2fd44eed0d72226 627B / 627B                                       0.9s
 => => sha256:0256c04a8d84ab5ae434b607055df8fdfe0278dba43f3e603a861dc7e26da395 957B / 957B                                       1.6s
 => => sha256:38e992d287c563d332ed8c9bdefec32a84f50f94cc39bb4729a3e73cefde88eb 406B / 406B                                       2.0s
 => => sha256:9e9aab598f58e86706b73c23e0ff33fc4eb60a5e69424147f9cb7c02e853323b 1.21kB / 1.21kB                                   2.3s
 => => sha256:4de87b37f4ad0b499be3db4cc6831db3d8158867f12dabc0bf42046b56784d3b 1.40kB / 1.40kB                                   3.0s
 => => extracting sha256:af302e5c37e9dc1dbe2eadc8f5059d82a914066b541b0d1a6daa91d0cc55057d                                        1.0s
 => => extracting sha256:207b812743af01771d6c94b3ebc59543bf3c6fefe5d4d9ebfa6e5e5558801d34                                        0.6s
 => => extracting sha256:841e383b441eda86c164d8e833da080b951c951d612853cac2fd44eed0d72226                                        0.0s
 => => extracting sha256:0256c04a8d84ab5ae434b607055df8fdfe0278dba43f3e603a861dc7e26da395                                        0.0s
 => => extracting sha256:38e992d287c563d332ed8c9bdefec32a84f50f94cc39bb4729a3e73cefde88eb                                        0.0s
 => => extracting sha256:9e9aab598f58e86706b73c23e0ff33fc4eb60a5e69424147f9cb7c02e853323b                                        0.0s
 => => extracting sha256:4de87b37f4ad0b499be3db4cc6831db3d8158867f12dabc0bf42046b56784d3b                                        0.0s
 => [internal] load build context                                                                                                0.0s
 => => transferring context: 389B                                                                                                0.0s
 => [2/3] RUN rm -rf /usr/share/nginx/html/*                                                                                     0.4s
 => [3/3] COPY index.html /usr/share/nginx/html/                                                                                 0.0s
 => exporting to image                                                                                                           0.0s
 => => exporting layers                                                                                                          0.0s
 => => writing image sha256:6d7b80f6c3f7d603ea50ab6e0f1762ec2ba90a80517b3432835afbfa820199f5                                     0.0s
 => => naming to docker.io/smabramovvv/my-app:1.1.1                                                                              0.0s
serg@debian:~/git/my-app$ docker push smabramovvv/my-app:1.1.1
The push refers to repository [docker.io/smabramovvv/my-app]
58ee5bb30b4b: Pushed 
1f6acd8e1f9b: Pushed 
b57b5eac2941: Mounted from library/nginx 
58045dd06e5b: Mounted from library/nginx 
541cf9cf006d: Mounted from library/nginx 
32c977818204: Mounted from library/nginx 
943132143199: Mounted from library/nginx 
88ebb510d2fb: Mounted from library/nginx 
f5fe472da253: Mounted from library/nginx 
1.1.1: digest: sha256:d338f73c3a13ca3e79fc2eb1cf5623fc77f64d1307978f2dd5748eac9b3b8ed2 size: 2192
serg@debian:~/git/my-app$ docker run -p 80:80 smabramovvv/my-app:1.1.1
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/02/01 07:43:35 [notice] 1#1: using the "epoll" event method
2025/02/01 07:43:35 [notice] 1#1: nginx/1.27.3
2025/02/01 07:43:35 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2025/02/01 07:43:35 [notice] 1#1: OS: Linux 6.1.0-29-amd64
2025/02/01 07:43:35 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/02/01 07:43:35 [notice] 1#1: start worker processes
2025/02/01 07:43:35 [notice] 1#1: start worker process 29
2025/02/01 07:43:35 [notice] 1#1: start worker process 30
2025/02/01 07:43:35 [notice] 1#1: start worker process 31
2025/02/01 07:43:35 [notice] 1#1: start worker process 32
2025/02/01 07:43:35 [notice] 1#1: start worker process 33
2025/02/01 07:43:35 [notice] 1#1: start worker process 34

172.17.0.1 - - [01/Feb/2025:07:45:14 +0000] "GET / HTTP/1.1" 200 350 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0" "-"
2025/02/01 07:45:14 [error] 29#29: *1 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "127.0.0.1", referrer: "http://127.0.0.1/"
172.17.0.1 - - [01/Feb/2025:07:45:14 +0000] "GET /favicon.ico HTTP/1.1" 404 153 "http://127.0.0.1/" "Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0" "-"
```
![my-app](https://github.com/smabramov/my-app/blob/ce8a16a10ecae487607862d7dbecd9c5f58d87b5/my-app.png)