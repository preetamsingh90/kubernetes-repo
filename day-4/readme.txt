Multi Container Pod Kubernetes - Sidecar vs Init Container

Multi Container Pod Kubernetes - Sidecar vs Init Container

The main application pod that to be up and running all the init containers inside that pod has to be initialized first

k create deploy nginx-deploy --image nginx --port 80
k create deploy mydb --image redis --port 80
k expose deploy nginx-deploy --name myservice --port 80
k expose deploy mydb --name mydb --port 80
