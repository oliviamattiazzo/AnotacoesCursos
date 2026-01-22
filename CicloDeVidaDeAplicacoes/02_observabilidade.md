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

## Estratégias de observabilidade

### Pilares de Observabilidade

**O que são?**<br>
O que vamos observar dentro de uma aplicação.

* Métricas
  * Percentual de uso de processamento
  * Percentual de CPU
  * Uso de memória
  * Leitura e escrita de dados
* Traços distribuídos
  * Monitorar o percurso das requisições internamente
  * Identificar pontos de lentidão e/ou maior latência
* Logs
  * Status da aplicação
  * Relatórios sobre erros e falhas
  * Prática de debug

**Como implementar?**

**Métricas:** Prometheus

* Captura métricas da aplicação (gerais e/ou personalizadas)
* Open source
* Usada em conjunto com o *Grafana*
* Prometheus exporta as métricas, o Grafana cria os gráficos para visualização
  * Diferentes formas de visualização facilitam o acompanhamento da aplicação

**Traços distribuídos:** Jaeger

* Camada de acompanhamento de requisições
* Caminho do processamento da requisição dentro da aplicação
* Não é necessário uma ferramenta de visualização - Jaeger já faz isso por conta própria
* Acompanhamento permite leitura clara sobre aspectos de latência e tempo de processamento
  * Identificação de gargalos

**Logs:** Graylog

* Coletando tudo o que está acontecendo na aplicação
* Logs são salvos num arquivo, com timestamp e informação
* Servidor de logs: recebem os arquivos de log
* Graylog ajuda a organizar, indexar e visualizar os logs

**Outras ferramentas**
* ELK Stack (Elasticsearch - Logstash - Kibana)
* New Relic
* Dynatrace

-> Previsão de problemas

## Respondendo a falhas

* Não queremos indisponibilidade na aplicação
* Garantir funcionamento íntegro e contínuo

### Chegou um problema! O que fazer?

1. Identificar quais são os pontos de falha (*pontos críticos*)
2. Reunir dados das métricas, traços distribuídos e logs
3. Analisar os dados
4. Configurar alertas
  * Mitiga falhas
  * Previne problemas antes que os usuários detectem
  * Minimiza o impacto no funcionamento da aplicação

:warning: Lembrar de também monitorar atividades suspeitas<br>
* Múltiplas requisições (exemplo)
* Ataques e intrusões no sistema
* **IDS**
  * Monitora atividades suspeitas
* **IPS**
  * Previne que atividades suspeitas abalem a aplicação

**Importante:** documentar o que aconteceu após uma falha (seja de desempenho ou de segurança)
* Aprendizado da equipe
* Promover cultura colaborativa
* Evitar repetição de :shit:
* Oportunidade de refatoração de código
  * Melhorar resiliência, desempenho e reduzindo vulnerabilidades

## Glossário

* *Tracing:* rastreamento de requisições
* *Traços distribuídos / Distributed tracing:* rastreamento e monitoramento das requisições do sistema e do seu percurso
* *Logs*: registros de funcionamento
* *IDS*: Intrusion Detection System
* *IPS*: Intrusion Prevention System
