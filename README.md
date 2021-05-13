# gabrielknot/ipnginx
An simple debug image for kubernete. Your environiment variables will be exozed as an web page runnig above a nginx server.

In your kubernetes mainifest you may have to add it:
```console
image: gabrielknot/ipnginx
env:
- name: MY_POD_NAME
  valueFrom:
    fieldRef:
      fieldPath: metadata.name
- name: MY_POD_NAMESPACE
  valueFrom:
    fieldRef:
      fieldPath: metadata.namespace
- name: MY_POD_IP
  valueFrom:
    fieldRef:
      fieldPath: status.podIP
```
