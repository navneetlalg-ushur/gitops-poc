# gitops-poc
basic repo for gitops setup

### Namespace

- sales-dev
- sales-staging
- sales-prod
- billing-dev
- billing-staging
- billing-prod
- shipping-dev
- shipping-staging
- shipping-prod

### Annotations 

- The Docker registry where a pod's containers are stored
- The git repo from which a container is built
- Pointers to logging, monitoring, analytics, or audit repositories
- Debugging-related information, such as name, version, and build information
- System information, such as URLs of related objects from other ecosystem components
- Rollout metadata, such as config or checkpoints
- Phone or email of people in charge of the component's project
- The team's website URL

### Labels


- Determining whether a pod is part of a production or a canary deployment
- Differentiating between stable and alpha releases
- Specifying to which layer (UI, business logic, database, and so forth) an object belongs
- Identifying whether a pod is front-end or back-end
- Specifying an object’s release version (V1.0, V2.0, V2.1, and so on)


```yml
apiVersion: v1
kind: Pod
metadata:
  name: sample-job
  annotations:
    repo: "https://git.your-big-company.com.br/lms/new-proj"
    imageregistry: "https://hub.docker.com"
    maintainer: "Navneet Lal Gupta"
    email: "navneet@example.com"
  labels:
    product: intracity
    version: stable
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
```