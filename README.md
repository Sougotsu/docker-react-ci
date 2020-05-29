# Training Docker and Kubernetes
## by Pipe (Juan Felipe Guerrero)

* ### **React Frontend** (Continuous integration)


>React node app listening on port **3000** for dev

Docker commands without docker compose
```
docker build -f Dockerfile.dev -t frontend .
docker run -it -p 3000:3000 -v /app/node_modules -v $(pwd):/app frontend
docker run -it frontend npm run test
```

Docker-compose use
```
docker-compose up --build
docker-compose up
```

#### Production build run

>React node app listening on port **8080** for production

```
docker build -t frontendrelease .
docker run -p 8080:80 frontendrelease
```