# Laboratório Docker

## Construção

docker build -t devops-webapi:1.4.0 .

## Execução

docker compose up -d

## Staging

docker run -d --name devops-api-staging -p 8081:8080 -e APP_ENVIRONMENT=staging -e APP_VERSION=1.4.0 devops-webapi:1.4.0

## Production

docker run -d --name devops-api-prod -p 8082:8080 -e APP_ENVIRONMENT=production -e APP_VERSION=1.4.0 devops-webapi:1.4.0

## Health Check

curl.exe -f http://localhost:8082/health     
curl.exe -f http://localhost:8081/health     

## Nova versão

docker build -t devops-webapi:1.5.0 .

## Falha controlada

devops-webapi:1.2.0

## Rollback

devops-webapi:1.1.0

## Docker Compose

docker compose up -d
docker compose ps
docker compose down