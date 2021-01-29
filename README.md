# Kubernetes



Interact With a Pod:

- kubectl get po : Get pod name
- kubectl logs POD_NAME: dump pod logs
- kubectl logs -f POD_NAME: -f option to stream pod logs
  
Connection into the POD container:

- kubectl exec -it POD_NAME -- /bin/bash
