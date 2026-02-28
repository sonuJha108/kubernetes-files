`command to start the kind cluster`
 kind create cluster --name tws-cluster --config config.yml

* If you get the error to start the node like this
--> error code         k8s.io/kubernetes/cmd/kubeadm/kubeadm.go:25
                        runtime.main
                             runtime/proc.go:271
                            runtime.goexit
                             runtime/asm_amd64.s:1695

* edit the vi etc/docker/daemon.json
enter the code
 {
  "exec-opts": ["native.cgroupdriver=systemd"]
}

# restart the docker
systemctl restart docker

# delete the cluster and re-create cluster using the cmd
kind delete cluster --name tws-cluster
kind create cluster --name tws-cluster --config config.yml

check the cluster 
 kubectl cluster-info --context  kind-tws-cluster

change the kind context
kubectl config use-context kind-tws-cluster
