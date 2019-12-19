# HelloDockerfile


## Clone repo locally

```sh
git clone https://github.com/ecwpz91/HelloDockerfile.git
```

## Change to directory

```sh
cd HelloDockerfile
```

## Create a new project for you application

```sh
oc new-project hellodockerfile --display-name="Hello Dockerfile Demo"
```

## Create a new build for your application

```sh
oc new-build --strategy docker --binary --docker-image centos:centos7 --name myapp
```


## Start a binary build using the local directory’s content


```sh
oc start-build myapp --from-dir . --follow
```

## Deploy the application using new-app, then create a route for it

```sh
oc new-app myapp
```

## Expose route to application

```sh
oc expose svc/myapp
```

# References

https://docs.openshift.com/container-platform/3.11/dev_guide/dev_tutorials/binary_builds.html#binary-builds-private-code
