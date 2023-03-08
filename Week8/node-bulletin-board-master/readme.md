
## 1 Git clone

```
git clone https://github.com/Tuchsanai/devopt_week8.git

cd devopt_week8/node-bulletin-board-master

```

## 3 Build Docker image
```

docker build --tag bulletinboard:1.0

```

## 3 Run Nginx with port mapping and volume mapping

```
docker run -p 8005:8080 -d --name bb bulletinboard:1.0

```