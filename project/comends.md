kompose convert -f docker-compose-backend.yaml -f docker-compose-frontend.yaml -f docker-compose-keycloak.yaml -f docker-compose-mongo.yaml -f docker-compose-nginx.yaml -f docker-compose-postgres.yaml

kubectl create configmap app-realm --from-file=app-realm.json=/mnt/c/Users/maria/Desktop/projekt---technologie-chmurowe-mariakoren/project/kubernetes/app-realm.json


to stop:

kubectl scale deployment backend --replicas=0
kubectl scale deployment frontend --replicas=0
kubectl scale deployment mongo --replicas=0
kubectl scale deployment nginx --replicas=0


to run:

kubectl scale deployment backend --replicas=1
kubectl scale deployment frontend --replicas=1
kubectl scale deployment mongo --replicas=1
kubectl scale deployment nginx --replicas=1


kubectl create configmap app-realm --from-file=app-realm.json --dry-run=client -o yaml > app-realm-configmap.yaml

/opt/keycloak/bin/kc.sh export --realm=app --dir=/opt/keycloak/data/export --users=realm_file
docker cp project-keycloak-1:/opt/keycloak/data/export/app-realm.json /mnt/c/Users/maria/Desktop/projekt---technologie-chmurowe-mariakoren/project/app-realm.json


docker build -t mariakoren/project-backend:latest .
docker push mariakoren/project-backend:latest

docker build -t mariakoren/project-frontend:latest .
docker push mariakoren/project-frontend:latest

docker build -t mariakoren/project-keycloak:latest .
docker push mariakoren/project-keycloak:latest