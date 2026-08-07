# Evidências Semana 1 — Containers e Cluster

## Inicialização dos containers
- Comando executado: `docker-compose up -d`
- Resultado: todos os serviços iniciados com sucesso
- Saída do `docker ps`:

![Saída do docker-compose e docker ps](docs/print-docker-compose.png)

## Testes de funcionamento
- Teste via navegador: acesso ao `http://localhost:8080` retornando página inicial da aplicação.

![Aplicação rodando na porta 8080](docs/print-app-8080.png)

- Teste via terminal:
```bash
curl http://localhost:8080/health
