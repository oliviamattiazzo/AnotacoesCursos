# Aula 01 - Pós-deploy

## Apresentação

* Para quem deseja ter uma visão sistêmica do desenvolvimento de software
    * Da concepção até a entrega e funcionamento -- ou seja, disponibilidade para usuários

### Etapas do pós-deploy:

#### Monitoramento

Garantir bom desempenho, eficiência e segurança

##### Observabilidade

* Como componentes estão interagindo
* Métricas
* Traços distribuídos
* **Logs**

##### **Segurança**

* Mecanismos para tornar a aplicação segura ainda durante o desenvolvimento
* Como desenhar **planos de contigência**
        
#### Manutenção

* Atualizações, mudanças de configuração e inclusão de novas funcionalidades

##### Boas práticas de...

* Manutenção do código
* Qualidade do código
* Refatoração - reduzir dívida técnica

**Resultado:** aplicação atualizável, com uma vida longa, e com capacidade de escalar -- funcionalidades e serviços

#### Atualização e Evolução

###### Infraestrutura

* Migrar entre ambientes
* Ambientes múltiplos
* Infraestrutura como código

## Testando pós deploy

**Procurar mais sobre:** Canary Deployment ou Blue Green

> Testes garantem o funcionamento correto da aplicação, minimizando risco e interrupções.

### Smoke testing

**Objetivo:** verificar o comportamento geral da aplicação em Produção.<br>
-> Verificações feitas de maneira orgânica *e rápida*<br>
-> **Exemplo:** carregamento das páginas principais de uma plataforma

Aplicações podem fazer uso de diferentes tipos de componentes<br>
**Exemplos:** Containers, instâncias, funções desempenhando papel de serviços *servless*

> **Questão:** Como realizar testes adequados para garantir que a funcionalidade está apresentando bom desempenho e operando corretamente, mesmo antes de ser implantada?

### Testes unitários

**Objetivo:** testar cada um dos componentes<br>
-> Não cobrem 100% do funcionamento de um serviço<br>
-> Focam em pequenas partes da aplicação<br>
-> Garantem somente o funcionamento *isolado* das coisas

### Testes de integração

**Objetivo:** verificar como as coisas estão conversando entre si

### Teste E2E *end-to-end*

**Objetivo:** teste completo do funcionamento da aplicação<br>
-> Começamos a fazer esses testes *antes* da aplicação<br>
-> Ambiente de *Staging* -- simula Produção

> Ideal que todos os testes sejam *automatizados*

### Testes de carga

**Objetivo:** simular picos de requests na aplicação<br>
-> A aplicação é robusta e resiliente o suficiente?

### Testes de penetração (pentests)

**Objetivo:** entender se há vulnerabilidades na aplicação<br>
-> Evitar vazamento de dados e uso indevido<br>
-> **Exemplo:** testar se um usuário consegue acessar dados de outro usuário indevidamente

> Após testes, chega a parte do **monitoramento** da aplicação.

## Monitorando a aplicação

* Estágio de **monitoramento** vem logo após ao estágio de **implantação**

### Picos de acesso

* Pode gerar problemas de disponibilidade
    * Reclamações, prejuízo

> **Definição de monitoramento:** verificar o desempenho e a saúde da aplicação

#### Ferramentas

* Prometheus
* DataDog
* New Relic
* Cloud Watch (AWS)
    * **Exemplo do que pode ser monitorado:** alarmes, logs, métricas, eventos...

#### Métricas

Ferramentas listadas acima lidam com **métricas** -- rastreamento e análise.

* Disponibilidade (uptime)
* Velocidade de resposta de APIs
* Tempo de carregamento de páginas
* Latência de rede e processamento (tempo de resposta)
* Utilização de recursos computacionais (CPU, memória)
* Volume de acessos
* Registros de erros (logs)

Monitoramento contínuo é **fundamental**.

> **Importante:** prever eventos e problemas<br>
> **Exemplo:** Erros e picos de acesso

**Agir** é melhor que reagir. Assim evitamos qualquer tipo de descontinuidade no comportamento da aplicação

## Escalabilidade e elasticidade

### Utilização de recursos computacionais

**Somente** configuração de alarmes não vai funcionar.<br>

**Escalabilidade e elasticidade:** propriedades fundamentais quando lidamos com aplicações que apresentam *variações na curva de acesso*.

#### Escalabilidade

Ao identificarmos um pico de acesso em uma aplicação, é necessário *adequar os recursos à demanda*.

##### Auto Scaling Groups

* Recurso do CloudWatch (AWS)
* Ferramenta que ajuda a ampliar a escala do sistema -- multiplica os recursos da aplicação
    * Maneira automatizada de fazer as coisas

> **Escalabilidade vertical:** adição de capacidade para um único recurso (mais processadores, mais memória, mais HD) || *Menos utilizada*<br>
> **Escalabilidade horizontal:** adição de recursos ao ambiente computacional

* **Amazon RDS:** utilizam os dois conceitos, vertical e horizontal.

> Como gerenciar o tráfego que está chegando?

##### Balanceadores de carga (*load balancer*)

**Objetivo:** distribuir o tráfego de maneira uniforme entre os diferentes servidores que estão executando a aplicação.<br>
-> Equilibrar tráfego e demanda de processamento entre recursos<br>
-> Também verificam a **integridade dos recursos** (*health checks*)

##### Políticas de escalabilidade

**Objetivo:** estabelecer métricas para adicionar novos recursos ao ambiente computacional.

#### Elasticidade

Se a demanda aumenta, aumentamos os recursos. Da mesma forma, se a demanda diminuir, diminuimos o número de recursos.<br>
-> **Otimização dos custos**

> *Escalabilidade* e *elasticidade* são características principais da computação em nuvem.

## Próximo passo

**Observabilidade**