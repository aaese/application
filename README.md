# Kubernetes Deployment

Deploy the backend:
1. Build and push the Docker image to a registry.

Go to dir with FrontEndDockerfile and run:
```
docker build --pull --rm -f "FrontEndDockerfile" -t a2011se/application:frontend "." 

docker push a2011se/application:frontend
```
Go to dir with BackEndDockerfile and run:
```
docker build --pull --rm -f "BackEndDockerfile" -t a2011se/application:backend "." 

docker push a2011se/application:backend
```
2. Apply the Kubernetes configurations:
   ```sh
   kubectl apply -f backend-deployment.yaml
   kubectl apply -f backend-service.yaml
   kubectl apply -f frontend-deployment.yaml
   kubectl apply -f frontend-service.yaml```
