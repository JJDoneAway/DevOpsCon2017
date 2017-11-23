# Continious Delivery with GitLab to K8
- Michael Harrer
- GitLab from Idea to Production a Video to be googled
- everything as code

## Theory
### K8
- Kubernetes beschreibt einen Sollzustand. Es wird immer versuchen den Sollzustand zu erreichen.
- Ein Kubernetes Service ist ein selector auf die Pods
- Job is ein einmal Pods
- man kann halt nachher noch dran rumwurschteln

### GitLab CI / Runner
- GitLab CI yam erstellt die pipeline
- GitLab runner (K8 executor)
- erzeugt innerhalb von K8 innerhalb von K8

### Helm
 - ist der K8 Package Manager
 - helm ist der client
 - tiller ist die Serverseite

## Demo
- setup cluster und repos
- über Helm runner bauen
