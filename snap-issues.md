/ [Home](index.md)

# Snap Issues 

- Snap docker Issue :

  - It threw error when we use kind for K8s like below:

```
kind load docker-image finance-app:latest --name mycluster

Image: "finance-app" with ID "sha256:a66aa7115cbe1510df3e46017c238bd5a243df028848e2308eb7ff61e1b74d7d" not yet present on node "mycluster-control-plane", loading...
ERROR: command "docker save -o /tmp/images-tar558720786/images.tar finance-app" failed with error: exit status 1
Command Output: failed to save image: invalid output path: directory "/tmp/images-tar558720786" does not exist
```


- Zoom Issue

Zoom audio has some issues with Snap on Ubuntu. Still we need to collect more information for this issue.
