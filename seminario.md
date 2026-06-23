# Proposta de Seminário: InfluxDB e o Armazenamento de Séries Temporais

**Disciplina:** Projeto e Administração de Banco de Dados  
**Professor:** Taciano  

## Equipe

- Arthur de Medeiros Dantas  
- Expedito Luiz de Franca  
- Ivyson Wanderson Nunes Martins  
- Jose Gean de Macedo Alves  
- Julia Lilian Prudencio da Costa  

---

## SGBD Escolhido: InfluxDB

O Sistema Gerenciador de Banco de Dados (SGBD) escolhido para a pesquisa e apresentação do seminário é o **InfluxDB**.

Trata-se de um banco de dados **Não-Relacional (NoSQL)** classificado especificamente como um **TSDB (Time Series Database ou Banco de Dados de Séries Temporais)**. Desenvolvido do zero pela empresa InfluxData, ele foi projetado para otimizar o armazenamento, a recuperação e a análise de dados carimbados com o tempo (timestamps).

---

## Justificativa e Relevância

SGBDs relacionais tradicionais lidam com extrema eficiência em transações de negócios (ACID), mas frequentemente sofrem com gargalos de performance e excesso de indexação quando submetidos a cargas de trabalho que exigem a ingestão contínua de milhares de registros por segundo.

O **InfluxDB** resolve essa limitação do mercado. Ele é amplamente utilizado na indústria moderna em áreas como:

- **Internet das Coisas (IoT):** Armazenamento de telemetria contínua de milhares de sensores.  
- **Monitoramento e DevOps:** Análise de desempenho de servidores, infraestruturas de nuvem e redes.  
- **Mercado Financeiro:** Registro de cotações em tempo real com precisão de nanossegundos.  

O InfluxDB destaca-se por sua altíssima velocidade de gravação, compressão agressiva para redução de custos de disco e implementação nativa de políticas de retenção automática (Data Lifecycle Management).

---

## Proposta Prática

A demonstração prática do seminário terá como objetivo comprovar a eficiência do InfluxDB na ingestão e visualização rápida de dados temporais, simulando um ambiente de telemetria de sensores IoT.

### O que será feito:

- **Provisionamento do Ambiente:**  
  A instalação e execução do InfluxDB não será feita de forma nativa no sistema operacional, mas sim através de tecnologia de containers utilizando o Docker. Isso garantirá um ambiente isolado, reprodutível e alinhado com as boas práticas de infraestrutura moderna.

- **Configuração do SGBD:**  
  Pela interface nativa da ferramenta, será configurada uma *Organization*, um *Bucket* (equivalente ao database relacional) e a geração de um Token de Autenticação de API para garantir a segurança da ingestão de dados.

- **Ingestão de Dados (Line Protocol):**  
  Utilizaremos a interface de linha de comando (via cURL) para enviar dados simulados de sensores climáticos (temperatura e umidade) da cidade de Caicó/RN. Será demonstrada a simplicidade do Line Protocol, formato de texto altamente otimizado do InfluxDB para inserção massiva, utilizando as estruturas de *Measurements*, *Tags*, *Fields* e *Timestamps*.

- **Consulta e Visualização (Data Explorer):**  
  Finalizaremos a prática demonstrando como os dados inseridos são processados imediatamente pelo SGBD. Acessaremos o painel **Data Explorer** do próprio InfluxDB para plotar gráficos de linha em tempo real, evidenciando as oscilações dos dados inseridos e comprovando a vocação da ferramenta para análises temporais instantâneas.

---

## Referências

- INFLUXDATA. *InfluxDB Official Documentation*. Disponível em: https://docs.influxdata.com/influxdb/v2/get-started/. Acesso em: 23 jun. 2026.  
- DOCKER HUB. *InfluxDB Official Image*. Disponível em: https://hub.docker.com/_/influxdb. Acesso em: 23 jun. 2026.  
 