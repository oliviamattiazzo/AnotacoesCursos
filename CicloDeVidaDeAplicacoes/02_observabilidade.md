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
