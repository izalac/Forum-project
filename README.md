# Forum-project


## Deployment

From forum directory:
Run locally with docker: edit compose.yaml if needed and run `docker-compose up` - first run you will need to init database by executing `flask db upgrade` inside the container
Kubernetes: build image, edit k8s/forum-k8s.yaml to match your desired config and run `kubectl apply -f k8s/forum-k8s.yaml`
