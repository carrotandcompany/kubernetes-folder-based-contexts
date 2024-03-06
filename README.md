# Kubernetes folder-based context demo

This is a demo for this [blog post](https://www.cnc.io/en/blog/streamlining-kubernetes-project-management-with-folder-based-contexts.html).


# Prerequisits

* Install [direnv](https://direnv.net/)
* Install [minikube](https://minikube.sigs.k8s.io/)
* Install [ctlptl](https://github.com/tilt-dev/ctlptl)
* Clone this repo

# Setup

To setup the first local kubernetes cluster for demo purposes:

```bash
cd myproj

# we need to allow direnv to execute the .envrc file 
# Because it could be malicous code in it, so check it first
# in case you got if from someone you don' trust
direnv allow

# this creates a local kubernetes minikube cluster and a local 
# registry based on the ctlptl.yaml. It will also override the 
# .kube/config file because it is pointing to my local minikube
# cluster and not your newly creates one
ctlptl apply -f ctlptl.yaml
```

Do the same for `anotherproj`:

```bash
cd anotherproj
direnv allow
ctlptl apply -f ctlptl.yaml
```

Now you have two local kubernetes clusters running and you can switch between them by changing the directory.

More details on how this works can be found in the [blog post](https://www.cnc.io/en/blog/streamlining-kubernetes-project-management-with-folder-based-contexts.html).


# LICENSE 

MIT License

# Author

Christian Haintz, Carrot & Company and [Contributors](https://github.com/carrotandcompany/kubernetes-folder-based-contexts/graphs/contributors)


