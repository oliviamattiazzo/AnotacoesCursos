# Aula 03 - Segurança de aplicações

## Mecanismos de segurança

* Aspecto essencial durante todos os estágios de vida da aplicação -- não só monitoramento
* Primeiras interações com segurança: geralmente *autenticação/autorização*
  * *Autenticação:* quem é você
  * *Autorização:* o que você pode fazer
    * Usuários diferentes tem permissões diferentes

### Como tornar o processo de autenticação mais seguro?

* Autenticação de múltiplos fatores
  * SMS com código, biometria, reconhecimento facial -- confirmam que é realmente o usuário
* Evitar fraudes e acessos não permitidos
* *Exemplo:* ambientes financeiros exigem um alto grau de segurança

* Criptografia
  * Cuidado com dados sensíveis - vazamentos, por exemplo
  * Ajuda a manter inacessível os dados armazenados e transmitidos
* Dados guardados e protegidos de pessoas externas
* *Criptografia em repouso:* codifica as informações no banco de dados
  * Algoritmo que codifica as informações em dados initeligíveis, embaralhando as informações dos usuários 
* *Criptografia em trânsito:* codifica as informações que estão transitando de um estágio para o outro na aplicação
  * Se as informações forem interceptadas durante o caminho na rede, não estarão acessíveis 
* ***Chaves** de criptografia
* ***Protocolos** de segurança
  * *TLS:* Transport Layer Security
    * Camada de segurança utilizada no protocolo HTTP
    * Cria um túnel seguro entre o dispositivo de um cliente e o servidor

## :point_up: Para saber mais: pilares da segurança da informação

> **Definição:** conjunto de ações e estratégias para proteger sistemas, programas, equipamentos e redes de invasões
> De forma geral, proteger dados valiosos de possíveis violações ou ataques.

### Três pilares principais - CID

1. **Confidencialidade**
  * Medidas para garantir que as informações sejam mantidas sob sigilo
  * Implementação de restrições de acesso a informações específicas
2. **Integridade**
  * Informações não podem sofrer alterações não autorizadas ao longo de todo o processo (tráfego, armazenamento e processamento)
3. **Disponibilidade**
  * Usuários precisam conseguir acessar as informações de todos os sistemas possíveis, no momento em que precisarem

### Outros aspectos também importantes

* Autenticidade
  * Informações verdadeiras e sguras
  * Decorrentes de fontes confiáveis
  * Registrar autores da informaçnao para que seja possível rastrear e atestar a veracidade
* Irretratabilidade
  * Usuários não podem negar a autoria das informações
  * Garante a autenticidade
  * Nem autor nem receptor podem contestar qualquer transação de dados
* Conformidade
  * Garantir que todos os processos obedeçam às leis e normas regulamentares
  * Desenvolvimento de protocolos em conformidade com as normas
  * Promover mecanismos de fiscalização para assegurar o cumprimento dos protocolos
 
## Identificando vulnerabilidades

* Preocupar-se com a segurança durante todo o ciclo de vida da aplicação
  * Atualizações
  * Novas features
  * Mudanças de configurações
* Assegurar desempenho e segurança
  * Dados protegidos
  * Evitar interceptação e vazamento

### Boas práticas

* Pensar em segurança como requisito (fase de concepção)
* Implementar testes pensando na segurança + Revisão de código (fase de desenvolvimento)

### OWASP - Open Web Application Security Project

* Diretrizes e ferramentas de segurança
* OWASP Top 10
  * Identifica as 10 principais vulnerabilidades de aplicações web
  * Lista constantemente atualizada
* ZAP - Zed Attack Proxy
  * Ferramenta para identificação de vulnerabilidades em uma aplicação

### Testes de penetração (Pentest)

> Verificar se há algum tipo de brecha na nossa aplicação

#### Etapas de um Pentest

1. Coleta de informações
2. Planejamento e escopo
3. Identificação e Exploração
4. Relatório de Vulnerabilidades
5. Mitigação
6. Retest

#### Modelo de boxes

* White box
  * Ataque mais profundo
  * Informações sobre o sistema são conhecidas
  * Geralmente é usado na fase de testes de uma aplicação
* Black box
  * Simulação de um ataque real
  * Pouquíssimas ou nenhuma informações conhecidas
  * Testes das medidas de proteção e respostas a ataques
* Gray box
  * Combinação entre White e Black Box
  * Existe uma troca de informações
  * Frequentemente em Pentes para aplicações Web

#### Feramentas para Pentest

> Cada uma dessas ferramentas possui especificidades de uso. É preciso selecionar e utilizar de acordo com o tipo de *pentes* que queremos conduzir

* ZAP (Zed Attack Proxy)
* Burp Suite
* Metasploit
* Nikto
* Nmap

### Ambiente seguro e resiliente

* Práticas de desenvolvimento seguro
* Testes de penetração (pentests)
* Práticas de observabilidade

## :point_up: Para saber mais: o que é criptografia?

* Processo de conversão de dados, de um formato legível, facilmente acessível e decodificado, ara uma forma encriptada e não decodificável
* No formato não decodificável, mesmo que seja obtido acesso ao dado, não será possível realizar a leitura sem o acesso à chave de encriptação.
  * Somente sistemas autorizados conseguirão realizar a codificação das informações
* A conversão dos dados é realizada por um algoritmo de encriptação (ou *algoritmo de criptografia*), que define como será feito o processo
  * Com base em fundamentos e teorias da matemática
* Algoritmos de encriptação são categorizados em dois grupos: simétricos e assimétricos

## Gerenciando incidentes

* Cada minuto é crucial quando lidamos com aplicações
* Plano muito bem preparado para lidar com incidentes

### NIST - National Institute of Standards and Technology

* Publicação especial: SP 800-34
* Guia de Planejamento de Contingência
* Inicialmente proposto como diretriz para sistemas de informação federais
* Foi adotada por diferentes equipes como um guia de boas práticas para lidar com incidentes
* Pode ser usado para definir uma estrutura organizacional para lidar com incidentes em aplicações

**Importância de uma estrutura**

* Equipe precisa saber como agir
* Ações não-convergentes não solucionam problemas
  * Pode prolongar a existência do problema, inclusive
* Planos de contingência garantem que a equipe atue de maneira integrada e assertiva

### Etapas do plano de contingência

1. Política de planejamento de contingência
  *  Fornece a base para que toda a equipe de desenvolvimento e operações possa criar um plano de contingência
2. Análise de impacto nos negócios (BIA)
  *  Priorização de recursos e componentes de acordo com o impacto no funcionamento da aplicação
3. Controles preventivos
  *  Medidas para proteger a aplicação de incidentes
4. Estratégias de contingência
  *  Definição de ações para incidentes específicos. Para cada incidente, estabelecemos estratégias conforme a prioridade de funcionamento da aplicação e a anaálise de impacto dos negócios
5. Documentação do plano de contingência
  *  Para que as pessoas envolvidas saibam o que fazer
6. Testes, exercícios e treinamentos de equipe
  *  Para que a equipe saiba como agir. Uma equipe bem treinada e alinhada age rapidamente e de forma eficiente
7. Atualização e melhoria contínua do plano
  *  Novas vulnerabilidades e problemas de segurança surgem constantemente

## Exercício - identificando vulnerabilidades com o OWASP Top 10

### Dados do cenário

1. Exposição de Dados Sensíveis
  * Os números de CPF dos usuários estão sendo enviados no front-end sem criptografia.
  * O banco de dados armazena informações de pagamento em texto simples.
2. Cross-Site Scripting (XSS)
  * O campo de "comentários" permite a execução de scripts maliciosos.
3. Controle de Acesso Quebrado
  * Alunos conseguem acessar áreas restritas aos professores ao manipular URLs diretamente.
4. Injeção de SQL
  * O endpoint `/getStudent` permite inserir comandos SQL diretamente no parâmetro id.
5. Falhas na Configuração de Segurança
  * A aplicação aceita conexões HTTP não seguras (sem TLS), expondo os dados em trânsito a interceptações.

### TO DO:

* Identificar as vulnerabilidades e associá-las às categorias do OWASP Top 10.
* Para cada vulnerabilidade:
  * *Identificar e categorizar:* Relacionar o problema identificado à categoria correspondente do OWASP Top 10.
  * *Propor soluções práticas:* Sugerir melhorias ou medidas corretivas que sigam as melhores práticas de segurança.

### Documentação

* [OWASP Top 10](https://owasp.org/www-project-top-ten/)
* [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)

### Resolução
