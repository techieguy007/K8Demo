We have a simple Python - Flask Web App, which reads the current RAM and CPU usage and a React frontend which shows the statistics in the browser.

We will get it to work with Kubernetes , in few simple steps

`Build the images for frontend and backend using docker-compose`

```bash
docker-compose build
```

`Tag the images`

```bash
docker tag sysstats-client techieguy007/images:sysstats-client
docker tag sysstats-api techieguy007/images:sysstats-api
```

`Push these images to docker hub`

```bash
docker push techieguy007/images:sysstats-client
docker push techieguy007/images:sysstats-api
```

! The images need to tagged as we will pull them while deploying k8s from their tag.

`DEPLOYMENT STEPS ON kUBERNETES`

I have used minikube on Windows 11 OS with Hyper-V platform
