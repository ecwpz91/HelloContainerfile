# HelloDockerfile


## 1. Clone repo locally

```sh
git clone https://github.com/ecwpz91/HelloContainerfile.git
```

## 2. Change to directory

```sh
cd HelloContainerfile
```

## 3. Create a new project for you application

```sh
oc new-project hellocontainerfile --display-name="HelloContainerfile Demo"
```

## 4. Create a new build for your application

```sh
oc new-build --strategy docker --binary --docker-image registry.redhat.io/ubi7/ubi:latest --name myapp
```

## 5. Start a binary build using the local directory’s content

```sh
oc start-build myapp --from-dir . --follow
```

## 6. Deploy the application using new-app, then create a route for it

```sh
oc new-app myapp
```

## 7. Expose route to application

```sh
oc expose svc/myapp
```

## 8. Get the host name for your route and navigate to it

```sh
oc get route myapp
```

## 9. Build and deploy application using Dockerfile in single command

```sh
oc new-app --name=testapp centos:centos7~https://github.com/ecwpz91/HelloContainerfile.git --strategy=docker
```

## 10. Create service

```sh
oc expose dc/testapp --port=8080
```

## 11. Expose route to application

```sh
oc expose svc/testapp
```

## 12. Get the host name for your route and navigate to it

```sh
oc get route testapp
```

# References

https://docs.openshift.com/container-platform/3.11/dev_guide/dev_tutorials/binary_builds.html#binary-builds-private-code
