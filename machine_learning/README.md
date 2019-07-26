# This is a readme for the machine learning

## MNIST:
https://github.com/guchchcug/MNIST-scratch
https://github.com/guchchcug/MNIST-keras
Fashion-mnist:
https://github.com/guchchcug/fashion-mnisit-base

## Procedures
```
Docker run
keras codes for MNIST
docker run -p 80:8888 guchch/mnist-keras:1.0 # a practice of dockerization from my local machine
docker run -p 80:8888 guchch/mnist-keras2-github:1.0 # a practice of dockerization from docker hub
```
### scratch codes for MNIST
```
docker run -p 80:8888 guchch/mnist-scratch:latest
```
### keras codes for fashion MNIST
```
docker run -p 80:8888 guchch/mnist-scratch:1.0
```

### How does the Dockerfile look like?
The following codes are for keras codes; for other codes, just replace “mnist_cg_keras.py” by the names of other codes:
```
FROM nvidia/cuda:10.1-base
RUN apt-get update && apt-get install -y python3 python3-pip
RUN pip3 install numpy pandas sklearn keras tensorflow matplotlib pillow argparse
COPY src /app
WORKDIR /app
ENTRYPOINT [“python3”, “mnist_cg_keras.py”]
```
```
Docker build from my local machine
docker login
docker build -t guchch/mnist-keras .
```

### Docker build from github
```
echo “# MNIST-keras” >> README.md
git init
git add README.md
git commit -m "practice for dockerization"
git remote add origin https://github.com/guchchcug/MNIST-keras.git
git push -u origin master
```
Then, add a repository from dockerhub.
