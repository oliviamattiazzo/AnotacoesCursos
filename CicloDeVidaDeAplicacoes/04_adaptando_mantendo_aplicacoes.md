# Aula 04 - Adaptando e mantendo aplicações

## Adicionando funcionalidades

* Melhorar experiência do usuário

**Nova etapa:** Manutenção do sistema

* Atualizações
* Novos recursos

### Primeiro passo - Consultar a *documentação* da aplicação

> **Definição:** Detalhamento da estrutura e comportamento de uma aplicação

#### Pontos importantes

* Entender como a estrutura da aplicação foi criada
  * Módulos
  * Propósito
  * Interação
* Entender o comportamento da aplicação
* Processo de documentação começa com diagramas e modelagem da aplicação
  * Linguagens gráficas (UML)
  * Inclusão de textos que expliquem o funcionamento -- muito além dos comentários no código
* Curva de aprendizado facilitada

### Ferramentas para documentação de projetos

* **Swagger - ** APIs RESTful, cria documentação interativa que demonstra exemplos práticos
* **Sphinx - ** projetos Python, gera documentação a partir de docstrings no código e exporta para HTML e PDF
* **JavaDoc - ** ecossistema Java, cria documentaçnao HTML a partir de comentários no código
* **PlantUML - ** solução para criar diagramas, como fluxos e modelos arquiteturais, diretamente no código
* **Docusaurus - ** documentação de projetos gerais, cria sites modernos de documentação com foco em personalização e experiência do usuário

## Qualidade de código

Não basta software estar funcional, deve ter bom desempenho, utilizar bem os recursos computacionais e ser fácil de manter, atualizar e escalar

### Critérios para um código de qualidade

* **Clareza**
  * Nomes descritivos para variáveis, funções e classes

  ```
    // Ruim
    def f(x):
      return x * 9/5 + 32

    // Bom
    def converter_celsius_fahrenheit(temperatura_celsius):
      return temperatura_celsius * 9/5 + 32
  ```
  
* **Legibilidade**
  * Estrutura lógica, comentários didáticos, consistência no estilo
  ```
    # Bom
    # Calcula a média de uma lista de números
    media = sum(lista_numeros) / len(lista_numeros)

    ########

    # Ruim
    for i in range(10):
      if i % 2 == 0: print(i)

    # Bom
    for numero in range(10):
      if numero % 2 == 0:
        print(numero)
  ```

* **Modularização**
  * Divisão do código em componentes menores
 
* **Eficiência**
  * Desempenho
  * Consumo de memória
  * Complexidade algorítmica
  * Como garantir? -> *Testes*
    * Quality Assurance / Garantia de Qualidade
    * *Testes fazem parte de toda a vida da aplicação!*

### Manifesto do Teste

* Testar continuamente **mais que** testar no final
* Previnir defeitos **mais que** encontrar defeitos
* Entender o teste **mais que** verificar funcionalidade
* Construir o melhor sistema **mais que** quebrar o sistema
* Time responsável pela qualidade **mais que** responsabilidade do testador

* Testes voltados para o negócio e outros voltados para a tecnologia
  * **Tecnologia:** dizem respeito à equipe que está opera, desenvolve, melhora e atualiza a aplicação
  * **Negócio:** envolvem todas as pessoas de produto e analistas de negócio, que nos ajudam a entender as demandas do mercado
* Testes que orientam o processo de desenvolvimento e testes que criticam o produto
  * Testes unitários
  * Testes de componente
  * Testes de performance
  * Testes de carga
  * Testes de segurança
  * Testes de aceitação
  * Testes de UX (usabilidade)
 
## Para saber mais: oq ue é QA?

> É um processo ou conjunto de atividades que visam garantir que um produto ou serviço atenda aos padrões de qualidade estabelecidos.
> **No desenvolvimento de software,** são práticas e técnicas usadas para monitorar e melhorar a qualidade de um software durante seu ciclo de vida

* Inclui:
  * Testes de software
  * Revisões de código
  * Automação de testes
  * Análise de requisitos
  * Entre outros
  * **Objetivo:** identificar e corrigir problemas antes que o software seja entregue aos usuários finais.
 
* O que faz um QA?
  * Definição de padrões e diretrizes
  * Planejamento de testes
  * Testes e validação
  * Revisões e auditorias
  * Feedback e melhoria contínua
  * Documentação
  * Automação de testes
  * Colaboração interdepartamental
  * Resolução de problemas
  * Treinamento e educação

## Manutenção e refatoração

**Importante:** manter o código limpo, eficiente e fácil de manter

> Se implementamos funcionalidades e correções sem nos preocuparmos com a evolução e eficiência da aplicação, com o tempo, aumentaremos o custo operacional e de desenvolvimento.

* Dívida técnica
* Refatoração
  * Melhorias estruturais
  * Correções de bugs
  * Padrões de design (design patterns)
  * **Não acumular dívida técnica!**
