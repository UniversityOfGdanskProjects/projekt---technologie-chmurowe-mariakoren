kompose convert -f docker-compose-backend.yaml -f docker-compose-frontend.yaml -f docker-compose-keycloak.yaml -f docker-compose-mongo.yaml -f docker-compose-nginx.yaml -f docker-compose-postgres.yaml

kubectl create configmap app-realm --from-file=app-realm.json=/mnt/c/Users/maria/Desktop/projekt---technologie-chmurowe-mariakoren/project/kubernetes/app-realm.json