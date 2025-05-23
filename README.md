# Forum-project


## Deployment

Docker image is published as `ivanzalac/forum`

Build and run locally with docker: in forum directory edit compose.yaml if needed and run `docker-compose up` - first run you will need to init database by executing `flask db upgrade` inside the container

Kubernetes: `forum/k8s/ephemeral-sqlite/forum-k8s.yaml` has sqlite ephemeral config, while `forum/k8s/persistent-postgresql/forum-k8s.yaml` has postgresql config suitable for production. Modify to match your desired config and run `kubectl apply -f <desired manifest file>`. Manifests currently target the published image on dockerhub.

You can use argocd to deploy on k8s:
```
argocd app create forum-app-argocd \
  --repo https://github.com/izalac/Forum-project.git \
  --path forum/k8s/persistent-postgresql \
  --revision argocd \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace forum-argocd \
  --sync-policy automated
```
