oc registry login

oc project cont-stg

oc apply -f imagestream.yml

oc apply -f configMap.yml

docker build -t default-route-openshift-image-registry/cont-stg/nginx-fallback:0.0.1 .

docker push default-route-openshift-image-registry/cont-stg/nginx-fallback:0.0.1

oc apply -f content-stg-deployment.yml

oc apply -f content-stg-gateway.yaml

oc apply -f content-stg-route.yaml
