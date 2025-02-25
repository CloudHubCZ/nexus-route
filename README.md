
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
podman tag alpine:3.21.3 9.141.134.217/repo-b/alpine:3.21.3 && podman push 9.141.134.217/repo-b/alpine:3.21.3

# Examples
podman logout nginx.cloudhub.cz/repo-a
podman login nginx.cloudhub.cz/repo-a --tls-verify=false -u repoa -p repoa
podman tag localhost/davidmachacek/kafka-producer:20241205.6 nginx.cloudhub.cz/repo-a/kafka-producer:20241205.6
podman push nginx.cloudhub.cz/repo-a/kafka-producer:20241205.6 --tls-verify=false
podman pull nginx.cloudhub.cz/repo-a/kafka-producer:20241205.6 --tls-verify=false
podman tag docker.io/davidmachacek/appd-snapshots:20250214.1 nginx.cloudhub.cz/repo-a/appd-snapshots:20250214.1
podman push nginx.cloudhub.cz/repo-a/appd-snapshots:20250214.1 --tls-verify=false

podman logout nginx.cloudhub.cz/repo-b
podman login nginx.cloudhub.cz/repo-b --tls-verify=false -u repob -p repob
podman tag docker.io/davidmachacek/appd-snapshots:20250214.1 nginx.cloudhub.cz/repo-b/appd-snapshots:20250214.1
podman tag docker.io/davidmachacek/appd-snapshots:20250214.1 nginx.cloudhub.cz/appd-snapshots:20250214.1
podman push nginx.cloudhub.cz/repo-b/appd-snapshots:20250214.1 --tls-verify=false


podman tag localhost/davidmachacek/kafka-producer:20241205.8 nginx.cloudhub.cz/repo-b/kafka-producer:20241205.8

# Examples - REPO-A
podman logout nginx.cloudhub.cz
podman login nginx.cloudhub.cz --tls-verify=false -u repoa -p repoa
IMAGE_NAME_A=nginx.cloudhub.cz/repo-a/alpine:3.21.3-a && podman tag docker.io/library/alpine:3.21.3 $IMAGE_NAME_A && podman push $IMAGE_NAME_A --tls-verify=false
podman pull $IMAGE_NAME_A --tls-verify=false

# Examples - REPO-B
podman logout nginx.cloudhub.cz
podman login nginx.cloudhub.cz --tls-verify=false -u repob -p repob
podman pull docker.io/library/alpine:3.20.6
IMAGE_NAME_B=nginx.cloudhub.cz/repo-b/alpine:3.20.6-b && podman tag docker.io/library/alpine:3.20.6 $IMAGE_NAME_B && podman push $IMAGE_NAME_B --tls-verify=false
podman pull $IMAGE_NAME_B --tls-verify=false