# Infrastructure_docker_mqtt

Note that you should create the passwd secret first. It will look something like this:

apiVersion: v1
kind: Secret
metadata:
  name: mqtt-passwd
type: Opaque
data:
  passwd: |
     <<base64 encoded mosquitto passwd file>>

Apply it to both the staging/production namespaces with:
kubectl -n staging apply -f mqtt-passwd.yaml
kubectl -n production apply -f mqtt-passwd.yaml
