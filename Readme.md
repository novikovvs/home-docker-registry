# Private registry
## Boot

```shell
cp .env.example .env
# Прописать необходимый NGINX_PORT и REGISTRY_URL (=[domain])
docker compose up -d
```
## Как пользоваться
Если не настроено SSL, 
то в daemon.json докера (/etc/docker/daemon.json)
необходимо прописать "insecure-registries": [
"{full_path_to_registry}"
]

**BUILD**
```shell
docker build . -t {full_path_to_registry}/NAME:TAG
# Прим: docker build . -t nevasoft-registry:8083/php:8.2
```
**PUSH**
```shell
docker push {full_path_to_registry}/NAME:TAG
# Прим: docker push nevasoft-registry:8083/php:8.2
```
**PULL**
```shell
docker pull {full_path_to_registry}/NAME:TAG
# Прим: docker pull nevasoft-registry:8083/php:8.2
```
## UI
В .env можно указать _**UI_PORT**_, по этому порту будет находиться визуальное представление registry.

