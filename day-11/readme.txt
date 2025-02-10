Taints and Tolerations in Kubernetes 

Taint -->

Think of taints as "only you are allowed" signs on your Kubernetes nodes. A taint marks a node with a specific characteristic, such as "gpu=true". By default, pods cannot be scheduled on tainted nodes unless they have a special permission called toleration. When a toleration on a pod matches with the taint on the node then only that pod will be scheduled on that node.

Tolerations -->

Toleration allows a pod to say, "Hey, I can handle that taint. Schedule me anyway!" You define tolerations in the pod specification to let them bypass the taints.

Taints & Tolerations in Action -->

Here’s a breakdown of the commands to manage taints and tolerations:

Tainting a Node:
kubectl taint nodes node1 key=gpu:NoSchedule
This command taints node1 with the key "gpu" and the effect "NoSchedule." Pods without a toleration for this taint won't be scheduled there.

To remove the taint , you add - at the end of the command , like below.

kubectl taint nodes node1 key=gpu:NoSchedule-
