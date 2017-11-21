# Java Development in the age of the whale

- speaker Dr. Roland Huß, red hates
- about K8 and Java
- https://github.com/ro14nd-talks/kubernetes-for-java-developers
- https://fabric8.io/

# Motivation
- split work is good for dev but a nightmare for Ops
- so put it into container
- you need to orchestrate the containers ==> Kubernetes

# What is K8
Open source orchestration systems
- scheduling
- horizontal scaling
- self healing
- service discovery
- automated rollout and rolleback
- pod has ip and name, volume
- lables to attache and select
- service is the dispatcher for the instances

# Highlevel Architecture
- Master which is a specal piece of software
- Nodes
- kubectrl

# How to get a k* cluster
- in the cloud at google or azure
- raspi pi cluster
- minikube

# Tools
- **fabric8 a toolset for all you need**
- open shift io

# Fabric8-maven-plugin
- create Docker images
- create recource configuration
- zero configuration mode
- https://maven.fabrics8.io

# Demo
- spring boot (Web, Actuator, DevTools)
- create @RestController , @RequestMapper with just a return Map(uuid, random number)
- add plugin to pom.xml fabric8 plugin
- minikuke start, minikube status
- kubectrl get Nodes
- mvn package fabricate8:build
- docker run {image name}
- curl -s http://($minicube_url)
- mvn fabric8:resource => create resource in target classes
- mvn fabric8:apply ==> deploy on kubectrl
- kubectrl get deployment, get pods
- minicube dashboards
- type in the service descriptor to NodePort
- kubectrl service nameoftheservice --url
- in pom.xml add properties the NodePort
- remote debugging mvn fabric8:debug call it twice connect to localhost:5005
- mvn fabric8:undeploy
- mvn fabric8:watch => live deploy and reload browser
- mvn fabric8:cluster-start
