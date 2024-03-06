```
docker run --name local-keycloak -d -p 8082:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD="p@ssw0rD!" quay.io/keycloak/keycloak:22.0.5 start-dev
```

```
  keycloak:
    image: quay.io/keycloak/keycloak:22.0.5
    container_name: local-keycloak
    environment:
      - KEYCLOAK_ADMIN=admin
      - KEYCLOAK_ADMIN_PASSWORD=p@ssw0rD!
    ports:
      - "8082:8080"
    command: start-dev
```
