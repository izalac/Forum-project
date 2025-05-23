# Forum-project


## Deployment

From forum directory:

Run locally with docker: edit compose.yaml if needed and run `docker-compose up` - first run you will need to init database by executing `flask db upgrade` inside the container

Kubernetes: build image, k8s/ephemeral-sqlite/forum-k8s.yaml has sqlite ephemeral config, while k8s/persistent-postgresql/forum-k8s.yaml has postgresql config suitable for production. Modify to match your desired config and run `kubectl apply -f <desired manifest file>`. Manifests assume image is pushed to where it's reachable, and named forum:latest
