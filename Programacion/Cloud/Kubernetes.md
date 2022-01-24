# Kubernetes

System for running many different containers over multiple different machines. 

You can use Kubernetes when you need to run many diferent containers with different images. (Scale aplication)


Development

* minikube

Production

* Managed solutions 
	* EKS Amazon elastic container service for kubernetes
	* GKE google cloud kubernetes engine
	* Yourself


## Important definition

* kubectl: use for managin containers in the node
	* Localy and production
* minikube: use for managing the VM itself
	* only localy


## Docker compose - kubernetes

| docker compose                                                 | kubernetes                                   |
| -------------------------------------------------------------- | -------------------------------------------- |
| Each entry can optionally get docker-compose to build an image | expects all images to already be built       |
| Each entry represents a container we want to create            | one config file per object we want to create |
| Each entry defines the networking requirementes (ports)        | We have to manually set up all networking    |


