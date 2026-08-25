# Loja Docker

Projeto de atividade avaliativa de Computacao em Nuvem com uma aplicacao em tres camadas usando Docker Compose.

## Servicos

- `web`: frontend publico com nginx, publicado em `http://localhost:8080`
- `api`: API interna com `traefik/whoami`, acessivel pelo proxy em `http://localhost:8080/api/`
- `banco`: Redis privado, com volume persistente `dados-banco`
- `objetos`: MinIO para armazenamento de objetos, com console em `http://localhost:9001`

## Como executar

```powershell
docker-compose up -d
```

## Testes uteis

```powershell
docker-compose ps
docker-compose exec banco redis-cli ping
docker-compose exec banco redis-cli set produto:1 "Camiseta"
docker-compose exec banco redis-cli get produto:1
```

## MinIO

- Console: `http://localhost:9001`
- Usuario: `admin`
- Senha: `admin12345`

## Encerrar

```powershell
docker-compose down
```
