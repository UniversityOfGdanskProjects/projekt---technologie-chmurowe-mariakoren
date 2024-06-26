# Projekt z przedmiotu bezpieczeństwo aplikacji webowych

Aplikacja w całości działa na platfrormie kubernetes

W celu uruchamienia trzeba wejść do folderu project/kubernetes i użyć komenty `kubectl apply -f .`

Dodatkowo aplikacja korzysta ze zmiennych środowiskowych

w folderze project/frontend trzeba utworzyć plik .env z podobną zawartością:

```
REACT_APP_KEYCLOAK_URL=http://localhost:9090/
REACT_APP_KEYCLOAK_REALM=app
REACT_APP_KEYCLOAK_CLIENT_ID=api
```

w folderze project/backend ważna jest zmienna 
```
PUBLICKEY=
```

zawartość której trzeba skopiować z aplikacji keycloak

Keycloack działa pod adresem localhost:9090

Frontend pod adresem localhost:3000

Backend pod adresem localhost:5000

Dodatkowo przy pierwszym uruchamieniu trzeba załadować zawartość pliku app-realm.json do keycloak aby stworzyć realm z całą, niezbędną zawartością


