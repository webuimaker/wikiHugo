---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Sample Installation and Setup of Kubernetes"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

<strong>Note: </strong>In this example, from X-Team’s [Introduction to Kubernetes Architecture](https://x-team.com/blog/introduction-kubernetes-architecture/) , all the components are installed inside a single docker container, acting as both master and worker node. This is solely for demonstration purposes.


## Installing Kubernetes


1. Set the K8S_VERSION env variable to the latest stable Kubernetes release, for later retrieval:

`export K8S_VERSION=$(curl -sS https://storage.googleapis.com/kubernetes-release/release/stable.txt)`

2. Assuming the host’s architecture is amd64, set the ARCH env variable:

`export ARCH=amd64`

3. Run the `hypercube` Docker container, which itself takes care of installing all the Kubernetes components. It requires special privileges, which are explained below.

```
docker run -d --volume=/:/rootfs:ro \
--volume=/sys:/sys:rw --volume=/var/lib/docker/:/var/lib/docker:rw \
--volume=/var/lib/kubelet/:/var/lib/kubelet:rw --volume=/var/run:/var/run:rw \
--net=host --pid=host --name=hyperkube-installer \
--privileged gcr.io/google_containers/hyperkube-${ARCH}:${K8S_VERSION}\  
/hyperkube kubelet --containerized \
--hostname-override=127.0.0.1 --api-servers=http://localhost:8080 \
--config=/etc/kubernetes/manifests --allow-privileged --v=2
```



4. Run the command `docker ps` to see all the running containers started by hypercube, for example a container created with the command `"/hyperkube apiserver"`.

The volume parameters are required to mount and give access to the host’s `/root` , `/sys` , `/var/run `and `/var/lib/docker` filesystems inside the container instance. The `--privileged` option grants access to all devices of the host, namely to start new containers. Parameters `--net=host` and `--pid=host` allow access to the network and PID namespace of the host.

`hypercube's` Docker image is available from Google’s Container Registry (GCR), we use ARCH and K8S_VERSION env variables to construct the full path to the image that fits our environment: `gcr.io/google_containers/hyperkube-${ARCH}:${K8S_VERSION}`

## Deploying Pods
1. Start a bash shell inside the hypercube container:

`docker exec -it hyperkube-installer /bin/bash`

2. Export the Kubernetes version and processor architecture inside the container:

`export K8S_VERSION=$(curl -sS https://storage.googleapis.com/kubernetes-release/release/stable.txt)
export ARCH=amd64`

3. Download the kubectl command line tool into /usr/bin/kubectl and make it executable:

```
curl -sSL "http://storage.googleapis.com/kubernetes-release/release/$K8S_VERSION/bin/linux/$ARCH/kubectl" > /usr/bin/kubectl
chmod +x /usr/bin/kubectl
```

4. Now you can run kubectl commands to retrieve information on Kubernetes state:

```
kubectl get nodes
kubectl get pods
kubectl get namespaces
```

5. Start deployment of a sample nginx pod and exit the container:

`kubectl run nginx --image=nginx --port=80 ; exit`

6. Run the command docker ps to see the new nginx containers running on the host.

7. Declare the nginx pod deployment as a service and map port 80 of the nginx service to port 8080 on the host:

```
docker exec -it hyperkube-installer /bin/bash
kubectl expose deployment nginx --port=8080 --target-port=80
```

8. Check that the nginx service is ready and was assigned an IP, and store it in a variable:

```
kubectl get service nginx
ip=$(kubectl get svc nginx --template={{.spec.clusterIP}}
```

9. Check the nginx welcome page is there via a browser or downloading it with curl:

`curl "http://$ip:8080"`


**For further reading, see Kubernetes Documentation:** {{< read-more "Introduction to Kubernetes Architecture" "https://x-team.com/blog/introduction-kubernetes-architecture/" "_target"  >}}