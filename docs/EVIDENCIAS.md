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
```

## Cluster kubeadm 3 nós (Etapa 1.3)

- Comando executado: `kubectl get nodes -o wide`
- Resultado: cluster kubeadm com 1 control-plane + 2 workers, containerd como runtime, Flannel como CNI, todos os nós em estado Ready na rede privada 192.168.56.0/24.
- Saída completa: ver `docs/evidencia-cluster-nodes.txt`

```text
NAME          STATUS   ROLES           AGE    VERSION    INTERNAL-IP     EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION       CONTAINER-RUNTIME
k8s-master    Ready    control-plane   5d5h   v1.33.13   192.168.56.10   <none>        Ubuntu 22.04.5 LTS   5.15.0-190-generic   containerd://2.2.1
k8s-worker1   Ready    <none>          5d5h   v1.33.13   192.168.56.11   <none>        Ubuntu 22.04.5 LTS   5.15.0-187-generic   containerd://2.2.1
k8s-worker2   Ready    <none>          5d5h   v1.33.13   192.168.56.12   <none>        Ubuntu 22.04.5 LTS   5.15.0-187-generic   containerd://2.2.1
```

## Ainda pendente (Semana 1)

- Etapa 1.2 — Distroless + Trivy + Cosign
- Etapa 1.4 — Deployments + StatefulSet nos 4 namespaces
- Etapa 1.5 — ConfigMap + Secret + Pod multicontainer + EmptyDir
- Etapa 1.6 — PV NFS RWX