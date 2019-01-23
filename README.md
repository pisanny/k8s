# k8s

DaemonSet configuration traefik-ds.yaml

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ./tls.key -out ./tls.crt -subj "/CN=*.domain.by"

kubectl create secret tls traefik-ui-tls-cert --key tls.key --cert tls.crt -n kube-system


htpasswd -c ./auth admin

kubectl create secret generic admin --from-file auth --namespace=kube-system


kubectl apply -f traefik-ds.yaml

