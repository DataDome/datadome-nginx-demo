# DataDome Nginx demo

This repository provides an example of the DataDome Nginx module using Docker.

For additional information, please check our [public documentation](https://docs.datadome.co/docs/nginx).

## 1 - Configuration

Open the file `nginx.conf` and set your `datadome-server-side-key` (found inside your [DataDome Dashboard](https://app.datadome.co/dashboard/management/integrations)).

## 2 - Build

```
docker image build . -t datadome-nginx-demo-image
```

## 3 - Run

```
docker run -d --rm --name datadome-nginx-demo-container -p 8282:80 datadome-nginx-demo-image
```

## 4 - Test

```
curl -v  http://localhost:8282/
```

Your request was protected (the header `X-DataDome: protected` is present) and is shown in your Dashboard.

## 5 - Logs

```
docker logs -f datadome-nginx-demo-container
```

## 6 - Stop

```
docker stop  datadome-nginx-demo-container
```