# kubernetes-cluster-test


## Installing k3s on master node
"""
curl -sfL https://get.k3s.io | K3S_KUBECONFIG_MODE="644" sh -s
"""

### Check installation

List all nodes 
"""
kubectl get no
"""

### Get infos about the node (very verbose!)

"""
kubectl describe nodes
"""


### Get token on master node (required to add workers)
"""
cat /var/lib/rancher/k3s/server/node-token
"""

## Installing k3s on worker nodes

"""
curl -sfL https://get.k3s.io | K3S_TOKEN="your_token" K3S_URL="https://master_ip:6443" K3S_NODE_NAME="node_name" sh -
"""