# Data-Pipeline---proj-05---Azure
Data Pipeline with Azure Databricks

Fomos contratados como pessoas engenheiras de dados em uma empresa imobiliária. Como nossa primeira tarefa, precisamos desenvolver um pipeline de engenharia de dados, usando recursos da ferramenta de Cloud utilizada pela empresa, a Microsoft Azure.

Estrutura do pipeline
Para entender como esse pipeline deve ser estruturado, vamos analisar uma imagem com a visão geral de todos os passos que precisamos realizar para construir nosso pipeline.


![image](https://github.com/fgabreu/Data-Pipeline---proj-04---Azure-/assets/57818977/1b39f66a-818d-4b48-8277-ba9fe11bb9e8)

Primeiramente, vamos precisar construir e estruturar um Data Lake, utilizando o recurso do Data Lake Gen2 da própria Azure. Esse Data Lake vai ser estruturado em três camadas:

Camada Inbound;
Camada Bronze.
Camada Silver.
A camada Inbound é a camada de entrada, onde vamos adicionar os dados na versão bruta. Os dados que vamos receber vão ser dados de imóveis, já que trabalhamos em uma empresa imobiliária.

Com esses dados na nossa camada de entrada, vamos utilizar a ferramenta Databricks para aplicar determinadas transformações nesses dados e passá-los pelas camadas Bronze e Silver do Data Lake.

Uma vez que tivermos todo esse fluxo de dados estruturado, vamos utilizar uma ferramenta chamada Azure Data Factory para orquestrar e automatizar a execução desse pipeline de acordo com o intervalo de tempo definido pela empresa.

- DESENVOLVIMENTO

O que foi feito:
- Datalake estruturado com as camadas necessárias
- Configuramos o Databricks
- Criamos os notebooks no Databricks
- Criamos o recurso do Data Factory
- Estruturamos o pipeline

Conforme a regra de negócios, novos dados de imóveis serão periodicamente adicionados ao nosso Data Lake, com uma frequência de atualização de uma vez por hora. Para garantir que nosso pipeline seja executado de acordo com esse intervalo de tempo, foi necessario configurar um gatilho no Azure Data Factory.
O gatilho é responsável por acionar a execução do pipeline sempre que novos dados forem detectados. Dessa forma, podemos automatizar o fluxo de processamento dos dados, garantindo que as transformações e atividades sejam realizadas regularmente e de acordo com o intervalo desejado.

Abaixo, segue uma imagem da pipeline de dados no Azure Data Factory após uma atualização dos dados.

![datafactory1](https://github.com/fgabreu/Data-Pipeline---proj-04---Azure-/assets/57818977/1f3f6273-05a9-4511-b471-80442ecfcbaa)

Com isso, finalizamos o pipeline e colocamos em produção.
