# Aula 02 - Observabilidade

## Observando os componentes da aplicação

* **Observabilidade:** um dos aspectos da parte de monitoramento

### Antes

* Abordagem monolítica da coisa
  * Frontend, backend e banco de dados num "blocão" de código
* **Maior preocupação:** garantir o funcionamento geral da aplicação
  * Análise de métricas como:
   * Percentual de utilização de CPU
   * Processo de leitura e escrita de dados
   * Uso de memória

### Atualmente

* Abordagem distribuída -- microsserviços
  * Fragmentação da aplicação
  * Interação por meio de APIs

### Observabilidade

* Analisar não só o todo da aplicação, mas também *funcionamento de cada parte*
* Nos permite identificar onde pode estar ocorrendo alguma falha, demora ou erro no processamento das requisições de forma mais "pontual"
* **Reação proativa:** ao identificar uma latência maior que a esperada, por exemplo, é possível agir para corrigir possíveis falhas ou problemas internos na aplicação

#### Exemplos

**Frontend**
* Tempo de carregamento das páginas
* Tempo de resposta

**Backend**
* Tempo de resposta das APIs

**Banco de dados**
* Eficiência das consultas
  * Consultas ineficientes, especialmente em períodos de alta demanda, podem causar sobrecarga e lentidão -> *gargalos*
 
**Mensageria e API de terceiros**
* Observar componentes de "fora" da aplicação
  * Monitorar tempo de resposta para evitar gargalos
 
### Diferença entre monitoramento e observabilidade

#### Monitoramento

olhar mais geral, que responde à pergunta:

> Está tudo funcionando na aplicação?

#### Observabilidade

É um olhar mais detalhado, nos fazendo compreender o que está acontecendo com cada componente e entre eles. Responde à pergunta:

> Por que não está funcionando?

## :point_up: Para saber mais: observabilidade e monitoramento

* Aplicações modernas geram um grande volume de dados em tempo real
  * Não é suficiente monitorar métricas isoladas, mas sim como os componentes interagem

**Definição de Observabilidade:** capacidade de acompanhar o estado interno de um sistema por meio de informações geradas durante sua execução. Ou seja, habilidade de entender como o sistema está se comportando em tempo real, analisando dados como logs, métricas e tracing. O objetivo é garantir que aspectos importantes para experiência do usuário final sejam monitorados e compreendidos.

**Definição de Monitoramento:** processo de acompanhar continuamente o estado de um sistema por meio de eventos registrados. Inclui a execução de ações reativas e proativas para manter o sistema funcionando corretamente.<br>
*Exemplo de eventos:* "uso de CPU acima de 80%" ou "falha ao conectar ao banco de dados"

**Definição de métrica:** indicador de nível de serviço, coletado dentro de uma série temporal. Serve para trazer dados importantes para observabilidade e monitoramento. Em outras palavras, é uma medição em uma janela de tempo que foca em uma propriedade do sistema. Sempre vai possuir um objetivo específico. Para cada ponto de atenção do sistema, deve existir uma métrica correspondente. Métricas são extraídas por meio da instrumentação. Ajudam a entender o comportamento do sistema em diferentes níveis. A partir delas, obtemos informações úteis para várias equipes diferentes: desenvolvimento, operação/infraestrutura, área de negócios, etc.

*Servem para medição de...*
* Performance
* Disponibilidade
* Saturação
* Erros
* Informações úteis para o negócio em geral

*Exemplos de pontos de atenção e métricas:*
* **Infraestrutura:** uso de CPU (%), espaço em disco disponível (GB).
* **Execução da aplicação:** tempo médio de resposta de requisições (ms), número de requisições com erro por minuto.
* **Regras de negócio:** taxa de conversão em um e-commerce (%), número de novos usuários cadastrados por dia.

## Glossário

* *Tracing:* rastreamento de requisições
