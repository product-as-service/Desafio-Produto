# Desafio-Produto


OBS: Como não foi destacado no caso quem cuidaria da parte de Devops/Micro Serviço dos modelos, sinalizando de que forma a equipe de Dados iria consultar os resultados gerados, assumi que é responsabilidade da equipe Analytics a criação do serviço, caso não seja ignorar a parte de APIs :)

## 1) Qual a proposta de valor da entrega?

Promover redução de esforços e economia de tempo na gestão de leeds, através da simplificação no processo de busca de empresas ativas como potenciais clientes.


## 2) Monte o backlog de estórias com as respectivas prioridades (explicar critério de priorização)

O Projeto foi dividido em 4 Fases:

[[FASE-1] Definições de Produto](https://github.com/product-as-service/Desafio-Produto/issues/1)

[[FASE-2] Levantamento dos dados que serão utilizados](https://github.com/product-as-service/Desafio-Produto/issues/2)

[[FASE-3] Desenvolvimento do Modelo de Classificação](https://github.com/product-as-service/Desafio-Produto/issues/3)

[[FASE-4] Levantando o Serviço de Classificação de Empresas](https://github.com/product-as-service/Desafio-Produto/issues/4)

## 3) Organize em uma timeline quais são os passos de desenvolvimento.

## 4) Quem são as pessoas envolvidas e as dependências entre times?

## 5) Como você organizaria os fluxos de comunicação?
- Reunião de Check de projeto Semanal com pauta.
- Reunião de Passagem de Bastão em tarefas de fim de execução de uma equipe e início de outra.
- Reservar tempo na Planning da Sprint em momentos que terá interação entre duas equipes diferentes em um mesmo momento.
- Documentação do serviço.

## 6) Quais critérios de aceitação de negócios das entregas? 

- A divisão de classificação deve ser entre: Pouco Provável / Provável / Muito Provável
- Deve existir uma taxa de confiabilidade relacionada a classificação gerada para o CNPJ
- O Modelo deve permitir imputs de Feedbacks (Ativos / Passivos) do cliente para retroalimentação do modelo
- O sistema deve clusterizar resultados genéricos caso não seja possivel classificar um CNPJ

## 7) Você precisa definir critérios técnicos? Quais?
- O imput recebido deverá ser o CNPJ da organização
- O critério de classificação deverá ter como base a clusterização dos resultados no BD de empresas Ativas
- Os endpoints devem ser protegidos por tokens 


## 8) Quais seriam as métricas para medir o sucesso da entrega?

**Negócio**
- Garantir que taxa de cobertura de classificação na base de Empresas Ativas seja superior a 70%
- Promover taxa média de confiabilidade por região e geral do algoritimo acima de 60%
- 20% Penetração da nova feature na base de clientes, nos dois primeiros meses de Lançamento
- 45% de leeds nas etapas finais de funil de vendas estarem com a classificação Muito Provável


**Operacionais**
- Tempo médio de resposta da API inferior a 5s
- Promover cobertura por testes unitários acima de 70%
- Accuracy, precision, recall do algoritmo de acordo com benchmarking de mercado
- Menos de 5% de feedbacks de classificação incorreta nos 3 primeiros meses

## 9) Quais os pontos de risco e que merecem atenção?
- Dificuldade de ter uma base já treinada com a classificação correta
- Performance do algoritmo
- Matriz / Filial pode inteferir na precisão da classificação
