# superset-deployment

Contains a Dockerfile that builds a customised Superset image.  Kubernetes manifest files run the Superset instance in a basic distributed mode.  An equivalent helm chart of the Kubernetes manifest files is also provided.

All instructions are executed from the root directory of the project and assume an Ubuntu operating system.

## Docker image

### Build

```
$ sudo docker build -f dockerfiles/Dockerfile -t alanb-2/superset:2.1.3 .
```

### Test

The custom image can be smoke tested by following the official quickstart documentation [here](https://superset.apache.org/docs/quickstart/) to start, create an account, configure and access the containerised Superset instance.

Note that the Docker image name and tag should be changed to the local name used in the build step above e.g. `alanb-2/superset:2.1.3`.

## Kubernetes

