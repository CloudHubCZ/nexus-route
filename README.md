
## GUI
http://9.141.122.248:8081/
admin
admin

## Full image transfer
podman pull alpine:3.21.3 && podman tag alpine:3.21.3 9.141.122.248:9090/repo-a-alpine:3.21.3 && podman push 9.141.122.248:9090/repo-a-alpine:3.21.3

## Podman push
podman push 9.141.122.248:9090/repo-a-alpine:3.21.3 --tls-verify=false

## podman login
podman login 9.141.122.248:9090 --tls-verify=false

## NGINX
podman login nginx.cloudhub.cz/repo-a --tls-verify=false

podman tag alpine:3.21.3 9.141.134.217/repo-a/alpine:3.21.3 && podman push 9.141.134.217/repo-a/alpine:3.21.3


# Examples
podman logout nginx.cloudhub.cz/repo-a
podman login nginx.cloudhub.cz/repo-a --tls-verify=false -u repoa -p repoa
podman tag localhost/davidmachacek/kafka-producer:20241205.6 nginx.cloudhub.cz/repo-a/kafka-producer:20241205.6
podman push nginx.cloudhub.cz/repo-a/kafka-producer:20241205.6 --tls-verify=false
podman pull nginx.cloudhub.cz/repo-a/kafka-producer:20241205.6 --tls-verify=false

podman logout nginx.cloudhub.cz/repo-b
podman login nginx.cloudhub.cz/repo-b --tls-verify=false -u repob -p repob
podman tag docker.io/davidmachacek/appd-snapshots:20250214.1 nginx.cloudhub.cz/repo-b/appd-snapshots:20250214.1
podman push nginx.cloudhub.cz/repo-b/appd-snapshots:20250214.1 --tls-verify=false


podman tag localhost/davidmachacek/kafka-producer:20241205.8 nginx.cloudhub.cz/repo-b/kafka-producer:20241205.8