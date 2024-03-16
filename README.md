# PR-TIMES-Internship
初めのスコアは132でしたけど、もう一回やり直してみたら、282になりました。以下はターミナルの記録です

```
root@ubuntu-virtual-machine:/home/ubuntu/Documents/Code/Ruby/private-isu/benchmarker# docker build -t private-isu-benchmarker .
[+] Building 17.6s (10/10) FINISHED                              docker:default
 => [internal] load build definition from Dockerfile                       0.0s
 => => transferring dockerfile: 172B                                       0.0s
 => [internal] load metadata for docker.io/library/golang:1.22             1.7s
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [1/5] FROM docker.io/library/golang:1.22@sha256:0b55ab82ac2a54a6f8f85  0.0s
 => [internal] load build context                                         15.8s
 => => transferring context: 1.25GB                                       15.8s
 => CACHED [2/5] RUN mkdir -p /opt/go                                      0.0s
 => CACHED [3/5] COPY . /opt/go                                            0.0s
 => CACHED [4/5] WORKDIR /opt/go                                           0.0s
 => CACHED [5/5] RUN go build -o bin/benchmarker                           0.0s
 => exporting to image                                                     0.0s
 => => exporting layers                                                    0.0s
 => => writing image sha256:99d82d6c170848714e360c2dc6260bcd2c5fdc7bd0065  0.0s
 => => naming to docker.io/library/private-isu-benchmarker                 0.0s
root@ubuntu-virtual-machine:/home/ubuntu/Documents/Code/Ruby/private-isu/benchmarker# docker run --network host --add-host host.docker.internal:host-gateway -i private-isu-benchmarker /opt/go/bin/benchmarker -t http://host.docker.internal -u /opt/go/userdata
{"pass":true,"score":132,"success":385,"fail":16,"messages":["リクエストがタイムアウトしました (GET /favicon.ico)","リクエストがタイムアウトしました (GET /js/timeago.min.js)","リクエストがタイムアウトしました (POST /login)","リクエストがタイムアウトしました (POST /register)"]}
root@ubuntu-virtual-machine:/home/ubuntu/Documents/Code/Ruby/private-isu/benchmaroot@ubuntu-virtual-machine:/home/ubuntu/Documents/Code/Ruby/private-isu/benchmaroot@ubuntu-virtual-machine:/home/ubuntu/Doroot@ubuntu-virtual-machine:/home/ubuntu/Documents/Code/Ruby/private-isu/benchmarker# docker run --network host --add-host host.docker.internal:host-gateway -i private-isu-benchmarker /opt/go/bin/benchmarker -t http://host.docker.internal -u /opt/go/userdata
{"pass":true,"score":282,"success":369,"fail":8,"messages":["リクエストがタイムアウトしました (GET /favicon.ico)","リクエストがタイムアウトしました (GET /posts)","リクエストがタイムアウトしました (POST /login)"]}

```
