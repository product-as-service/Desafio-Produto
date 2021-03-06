# Desafio-Produto 


OBS: Como não foi destacado no caso quem cuidaria da parte de Devops/Micro Serviço dos modelos sinalizando de que forma a equipe de Dados iria consultar os resultados gerados, assumi que é responsabilidade da equipe Analytics a criação do serviço, caso não seja ignorar a parte de APIs (FASE-4). :bowtie:

## 1) Qual a proposta de valor da entrega?

Promover redução de esforços e economia de tempo na gestão de leads, através da simplificação no processo de busca de empresas ativas como potenciais clientes.


## 2) Monte o backlog de estórias com as respectivas prioridades (explicar critério de priorização)

O Projeto foi dividido em 4 Fases. No [kanban](https://github.com/product-as-service/Desafio-Produto/projects/1) existem as issues centralizadoras de tarefas (com a label **central**), e o detalhamento das ações em issues secundárias (com a label **tarefas**).

OBS1: Foi realizado um detalhamento maior na fase 3, por ser o core business do time de Analytics :exclamation:

OBS2: Clicando nos Links será redirecionado para as issues dos itens :running:



[[FASE-1] Definições de Produto](https://github.com/product-as-service/Desafio-Produto/issues/1) :hammer:
- Pré análise das demandas e definições de desenvolvimento
- Alinhamento de expectativas
- Gestão de Cronograma

[[FASE-2] Levantamento dos dados que serão utilizados](https://github.com/product-as-service/Desafio-Produto/issues/2) 
- Comunicação com a equipe de Dados para extração de informações úteis para o modelo
- Insights para inteligação de informações

[[FASE-3] Desenvolvimento do Modelo de Classificação](https://github.com/product-as-service/Desafio-Produto/issues/3)
- [Criação do Modelo de Classificação](https://github.com/product-as-service/Desafio-Produto/issues/5) 
- [Criação da taxa de confiabilidade](https://github.com/product-as-service/Desafio-Produto/issues/6)
- [Formas de retroalimentação do modelo](https://github.com/product-as-service/Desafio-Produto/issues/7)

[[FASE-4] Levantando o Serviço de Classificação de Empresas](https://github.com/product-as-service/Desafio-Produto/issues/4)
- Serviço que se comunicará com a Equipe de Dados para fornecer inputs para Aplicação

## 3) Organize em uma timeline quais são os passos de desenvolvimento.
As atividades são em sequências pelas Fases do projeto.

Tempo de Cada Fase:

**Fase 1 e 2**: 1 Semana

**Fase 3**: 4 Semanas

**Fase 4**: 2 Semanas


Tempo total do Projeto
7 Semanas = **3 Sprint e 1 semana** :star:

## 4) Quem são as pessoas envolvidas e as dependências entre times?

Está sinalizdo dentro das issues, mas em linhas gerais:

### Fase 1:

**Envolvidos:**

**Produto:** UX, PM e PO de Dados, Analytics e Aplicação

**Engenharia:** Engenharia Dados, Analytics e Aplicação

### Fase 2:

**Envolvidos:**

**Produto:** PO de Dados e Analytics

**Engenharia:** Engenharia Dados e Analytics

**Dependências:** Fornecimentos dos dados para a criação do pelo por parte da equipe Data.

### Fase 3:

**Envolvidos:**

**Produto:** PO de Analytics

**Engenharia:** Engenharia Analytics

### Fase 4:

**Envolvidos:**

**Produto:** PO de Dados e Analytics

**Engenharia:** Engenharia Dados e Analytics

**Dependências:** Criar APIs de Classificação e Feedback por parte de Analytics para que Dados possa utilizar.



## 5) Como você organizaria os fluxos de comunicação?
- Reunião de Check de projeto Semanal com pauta.
- Reunião de Passagem de Bastão em tarefas de fim de execução de uma equipe e início de outra.
- Reservar tempo na Planning da Sprint em momentos que terá interação entre duas equipes diferentes em um mesmo momento.
- Documentação do serviço. :heavy_exclamation_mark:

## 6) Quais critérios de aceitação de negócios das entregas? 

- A divisão de classificação deve ser entre: Pouco Provável / Provável / Muito Provável
- Deve existir uma taxa de confiabilidade relacionada a classificação gerada para o CNPJ
- O Modelo deve permitir inputs de Feedbacks (Ativos / Passivos) do cliente para retroalimentação do modelo
- O sistema deve clusterizar resultados genéricos caso não seja possível classificar um CNPJ

## 7) Você precisa definir critérios técnicos? Quais?
- O input recebido deverá ser o CNPJ da organização
- O critério de classificação deverá ter como base a clusterização dos resultados no BD de empresas Ativas
- Os endpoints devem ser protegidos por tokens 


## 8) Quais seriam as métricas para medir o sucesso da entrega?

**Negócio**
- Garantir que taxa de cobertura de classificação na base de Empresas Ativas seja superior a 70% :rocket:
- Promover taxa média de confiabilidade por região e geral do algoritmo acima de 40%
- 20% Penetração da nova feature na base de clientes, nos dois primeiros meses de Lançamento
- 60% de leeds nas etapas finais de funil de vendas estarem com a classificação Muito Provável


**Operacionais**
- Tempo médio de resposta da API inferior a 5s
- Promover cobertura por testes unitários acima de 70%
- Accuracy, precision, recall do algoritmo de acordo com benchmarking de mercado
- Menos de 5% de feedbacks de classificação incorreta nos 3 primeiros meses

## 9) Quais os pontos de risco e que merecem atenção?
- Dificuldade de ter uma base já treinada com a classificação correta
- Performance do algoritmo
- Matriz / Filial pode interferir  na precisão da classificação
- Dados do CNPJ desatualizados em comparação com a Receita Federal
- Retroalimentação do modelo com atualização das features
