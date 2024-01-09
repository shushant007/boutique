* installing the docker on the ec2
yum install docker 
started the service and enabled it.

* installing the kind tool for running local kubernetes cluster
install the kind from its official page 
- [ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64

-installed the kubectl cli to have communication with my cluster.

- creating the kind cluster
kind create cluster --name qa-cluster --config kind-config/config.yaml

- After the cluster is created and adservice was pointed to the image which was not present on the google image hub so i changed the image to use, it was earlier 3.0.1 and i changed it to 0.3.4
ImagePullBackOff 

- Since the port 7070 was not exposed in the environment resource in cartservice yaml file it was failing, so i added the port there to be exposed .

- Now the error is coming due to redis service of liveness probe issue, so i changed the name used there to the cluster name which i kept as qa-cluster.