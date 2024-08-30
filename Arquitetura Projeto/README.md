## Arquitetura para movimentação de dados do Oracle EBS R12 para o Google BigQuery usando Debezium, Apache Kafka e BigQuery direto

**Componentes:**

* Oracle EBS R12: Sistema de origem que contém os dados de pedidos.
* Debezium: Ferramenta de captura de alterações que captura alterações em tempo real nas tabelas de pedidos do Oracle EBS R12.
* Apache Kafka: Plataforma de streaming que recebe as alterações capturadas pelo Debezium.
* Google BigQuery: Data warehouse que armazenará os dados de pedidos.

**Fluxo de dados:**

1. O Debezium captura alterações em tempo real nas tabelas de pedidos do Oracle EBS R12.
2. As alterações capturadas são enviadas para o Apache Kafka.
3. O BigQuery consome as alterações do Apache Kafka e as carrega diretamente em tabelas particionadas no BigQuery.

**Benefícios:**

* Streaming em tempo real: As alterações nos dados de pedidos são capturadas e transmitidas para o BigQuery em tempo real.
* Escalabilidade: O Apache Kafka pode lidar com grandes volumes de dados e escalar horizontalmente para atender à demanda crescente.
* Sem armazenamento intermediário: Os dados são transmitidos diretamente do Apache Kafka para o BigQuery, eliminando a necessidade de armazenamento intermediário.
* Custo reduzido: Esta arquitetura usa ferramentas open-source e elimina a necessidade de ferramentas proprietárias ou serviços gerenciados, reduzindo os custos gerais.

**Observação:**

Esta arquitetura pressupõe que o BigQuery esteja configurado para consumir dados do Apache Kafka. Isso pode ser feito usando o conector do BigQuery para o Apache Kafka ou criando uma assinatura do Pub/Sub no tópico do Kafka e configurando o BigQuery para consumir da assinatura do Pub/Sub.