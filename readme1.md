# Projekt z przedmiotu bezpieczeństwo aplikacji webowych


## Autor: Maria Koren

## Krótki opis:

Aplikacja jest słownikiem języka międzysłowiańskiego. Na stronie localhost:3000 widać 3 przyciski. Po kliknięciu na "opinie" możemy czytać i dodawać opinii (nie potrzebuje logowania). Po kliknięciu na "lista słów" można zobaczyć listę słów wraz z tłumaczeniami. Po kliknięciu na "moje słowa" zostanie wykonane przekierowanie na keycloak. Po udanym zalogowaniu zostanie widoczna lista wcześniej zapisanych słów. Jeżeli teraz wejdziemy na sronę lista słów, dodatkowo przy każdym słowie pojawi się możliwość zapisać to słowo. Dodatkowo jest opcja administratora. Przy zalogowaniu się jako administrator będą widocznę zapisanę słowa dla każdego użytkownika, pojawi się możliwość dodania słów, usuwania słów, usuwania opinii.

## Uruhamienie

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


