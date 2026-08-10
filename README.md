## Escreva uma benchmark para uma supermercado online o Quitandinha online 10/08 com dois casos ao menos.

# Benchmark de TI — Quitandinha Online

## 1. Objetivo

Este documento apresenta uma proposta de benchmark para avaliar o desempenho do sistema do **Quitandinha Online**, um supermercado online.

O objetivo é verificar como o sistema se comporta diante de diferentes cargas de utilização, analisando principalmente **tempo de resposta, quantidade de requisições processadas, uso de recursos e estabilidade do sistema**.

Para isso, foram definidos dois casos de teste:

* **Caso 1:** Consulta de produtos no banco de dados.
* **Caso 2:** Acesso simultâneo de usuários ao sistema.

---

## 2. Caso 1 — Consulta de produtos no banco de dados

### Cenário

O sistema do Quitandinha Online possui um banco de dados contendo informações sobre produtos, preços, categorias e estoque.

Um usuário realiza uma pesquisa por um produto, como:

> "Arroz"

O sistema precisa consultar o banco de dados e retornar os produtos correspondentes.

### Objetivo

Avaliar o desempenho do banco de dados durante consultas de produtos.

### Procedimento

1. Executar uma consulta de pesquisa de produtos.
2. Registrar o tempo de resposta.
3. Repetir a consulta diversas vezes.
4. Aumentar a quantidade de registros disponíveis no banco.
5. Comparar o tempo de resposta obtido.

### Métricas

* Tempo médio de resposta.
* Quantidade de registros consultados.
* Quantidade de requisições processadas.
* Taxa de erros.
* Utilização de CPU e memória do servidor.

### Resultado esperado

O sistema deve retornar os resultados rapidamente, mesmo com uma grande quantidade de produtos cadastrados.

Caso o tempo de resposta aumente significativamente conforme o banco cresce, pode ser necessário realizar otimizações, como:

* criação de índices;
* otimização das consultas SQL;
* melhoria da estrutura do banco;
* utilização de cache.

---

## 3. Caso 2 — Acesso simultâneo de usuários

### Cenário

Durante uma promoção, muitos clientes podem acessar o Quitandinha Online ao mesmo tempo.

Por exemplo, o sistema pode receber simultaneamente:

* 10 usuários;
* 50 usuários;
* 100 usuários;
* 500 usuários.

Cada usuário pode realizar ações como acessar produtos, pesquisar itens e adicionar produtos ao carrinho.

### Objetivo

Avaliar a capacidade do sistema de suportar múltiplos usuários simultaneamente sem apresentar lentidão ou falhas.

### Procedimento

1. Simular acessos simultâneos ao sistema.
2. Começar com 10 usuários.
3. Aumentar gradualmente para 50, 100 e 500 usuários.
4. Registrar o tempo de resposta para cada quantidade de usuários.
5. Registrar erros ou indisponibilidade do sistema.
6. Monitorar CPU, memória e rede do servidor.

### Métricas

* Quantidade de usuários simultâneos.
* Tempo médio de resposta.
* Requisições por segundo.
* Taxa de erros.
* Uso de CPU.
* Uso de memória RAM.
* Uso de rede.

### Resultado esperado

Espera-se que o sistema permaneça estável mesmo com o aumento da quantidade de usuários.

Caso o desempenho diminua consideravelmente, podem ser necessárias medidas como:

* aumento dos recursos do servidor;
* balanceamento de carga;
* otimização do código;
* utilização de cache;
* otimização do banco de dados;
* escalabilidade horizontal.

---

## 4. Comparação dos benchmarks

| Caso | Teste                | Principal objetivo            | Métricas                                           |
| ---- | -------------------- | ----------------------------- | -------------------------------------------------- |
| 1    | Consulta de produtos | Avaliar banco de dados        | Tempo de resposta, CPU, memória e erros            |
| 2    | Usuários simultâneos | Avaliar capacidade do sistema | Usuários, requisições/s, tempo de resposta e erros |

---

## 5. Conclusão

Os dois benchmarks permitem avaliar diferentes aspectos da infraestrutura de TI do Quitandinha Online.

O primeiro caso verifica o desempenho das **consultas ao banco de dados**, enquanto o segundo avalia a capacidade da aplicação de atender **diversos usuários simultaneamente**.

A realização desses testes permite identificar possíveis gargalos de desempenho e auxilia na tomada de decisões relacionadas à infraestrutura, banco de dados, aplicação e escalabilidade do sistema.

Dessa forma, o benchmark pode ser utilizado para garantir que o Quitandinha Online tenha um desempenho adequado mesmo com o crescimento da quantidade de produtos e usuários.
