
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