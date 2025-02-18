# Kubernetes Deployment for Docker Searching Movie Service

## Introduction
This project sets up a Kubernetes cluster to deploy the movie searching service from the Docker project hosted at [Docker-Searching-movie-Service](https://github.com/yasamangodarzi/Docker-Searching-movie-Service.git). The setup uses Kubernetes components such as Deployment, Service, ConfigMap, PersistentVolume (PV), and PersistentVolumeClaim (PVC).

---

## Implemented Components

### 1. Deployment
- **Server API Deployment:** 3 replicas
- **Elasticsearch Deployment:** 3 replicas
- **Redis Deployment:** 1 replica

### 2. Service
- **Server API Service:** Exposes the API pods
- **Elasticsearch Service:** Exposes Elasticsearch pods
- **Redis Service:** Exposes Redis pods

### 3. ConfigMap
- Stores non-sensitive configuration data separately from the application code, making the service portable.

### 4. PersistentVolume and PersistentVolumeClaim
- Created for Redis to ensure that cached data is not lost when Redis pods are restarted.

---

## Testing and Verification
- Applied all Kubernetes YAML files using `kubectl apply -f`.
- Verified PV and PVC status using `kubectl get pv` and `kubectl get pvc`.
- Tested data persistence after Redis pod deletion.
- Used `kubectl port-forward` to access the service locally and verify functionality.

---

## Conclusion
This project successfully deploys the Docker Searching Movie Service on a Kubernetes cluster with essential components for scalability, configuration management, and data persistence.



