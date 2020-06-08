# grpc-greeter-go

This sample application is based upon the followings.
https://github.com/GoogleCloudPlatform/istio-samples/tree/master/sample-apps/grpc-greeter-go
https://cloud.google.com/solutions/using-istio-for-internal-load-balancing-of-grpc-services?hl=ja

Rather than using iLB, this sample app uses external network LB.


## Pre-requisite
* GKE + ASM(Istio) ready environment

## Usage
TBD, but general procedure is below.
* Build container images of client, server apps
* Apply Istio manifests (including TLS certificate setup for ingress-gateway)
* Deploy the server app container to GKE with Istio env
* Run the client app container
```
docker run --rm -v $(pwd)/cert.pem:/data/cert.pem  --add-host grpc.example.com:34.84.80.223 gcr.io/k8s-day/grpc-greeter-go-client --address=grpc.example.com:443 --repeat 400
```



