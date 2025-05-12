# Introduction to NPUs

devices.ipynb

# Containers stuff

## How to build container
```javascript
cd ov_docker
./build_docker.sh
```

## How to start container
```javascript
docker compose -f ov.yml up
```

## How to connect to running container
### 1. Check list of running containers:
```javascript
docker ps
```
### 2. Connect to specified container:
```javascript
docker exec -it CONTAINER_ID bash
```
### 3. Preparing to make inference with NS2:
```javascript
source /opt/intel/openvino_2022.1.0.643/setupvars.sh
./opt/intel/openvino_2022.1.0.643/install_dependencies/install_openvino_dependencies.sh
./opt/intel/openvino_2022.1.0.643/install_dependencies/install_NCS_udev_rules.sh
```
