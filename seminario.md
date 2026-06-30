# Proposta de Seminário: InfluxDB e o Gerenciamento de Dados de Séries Temporais

**Disciplina:** Projeto e Administração de Banco de Dados

**Professor:** Taciano

## Equipe

* Arthur de Medeiros Dantas
* Expedito Luiz de Franca
* Ivyson Wanderson Nunes Martins
* Jose Gean de Macedo Alves
* Julia Lilian Prudencio da Costa

---

# 1. Introdução

O crescimento da Internet das Coisas (IoT), da computação em nuvem, do monitoramento de infraestruturas e da análise de dados em tempo real gerou uma demanda cada vez maior por sistemas capazes de armazenar e processar grandes volumes de informações geradas continuamente ao longo do tempo.

Nesse contexto surgem os Bancos de Dados de Séries Temporais (Time Series Databases – TSDBs), desenvolvidos especificamente para lidar com dados associados a um instante temporal, permitindo consultas rápidas, alta taxa de inserção de registros e análises históricas eficientes.

Entre as principais soluções existentes destaca-se o InfluxDB, um banco de dados especializado em séries temporais amplamente utilizado por empresas e organizações que necessitam armazenar métricas, eventos, telemetria e dados de sensores em larga escala.

---

# 2. SGBD Escolhido: InfluxDB

O Sistema Gerenciador de Banco de Dados escolhido para este seminário é o **InfluxDB**.

O InfluxDB é um banco de dados Não Relacional (NoSQL) desenvolvido pela InfluxData e classificado como um TSDB (Time Series Database). Sua arquitetura foi projetada especificamente para armazenar, indexar e consultar dados temporais com alto desempenho.

Diferentemente dos bancos de dados relacionais tradicionais, que normalmente utilizam tabelas estruturadas para armazenar informações transacionais, o InfluxDB foi otimizado para cenários onde milhares ou até milhões de registros são gerados continuamente ao longo do tempo.

Os dados armazenados no InfluxDB são organizados por meio de conceitos próprios da plataforma:

* **Measurements:** equivalentes a tabelas lógicas que agrupam dados semelhantes;
* **Tags:** informações utilizadas para indexação e filtragem rápida;
* **Fields:** valores efetivamente armazenados;
* **Timestamp:** marca temporal associada a cada registro;
* **Buckets:** estruturas responsáveis pelo armazenamento dos dados e suas políticas de retenção.

Além disso, o sistema oferece recursos avançados para análise temporal, agregação de dados, monitoramento em tempo real e gerenciamento automático do ciclo de vida das informações.

---

# 3. Justificativa da Escolha

A escolha do InfluxDB foi motivada pela crescente importância dos dados temporais nos sistemas modernos.

Atualmente, diversos setores dependem da coleta contínua de informações para tomada de decisões e monitoramento de processos. Entre as principais aplicações do InfluxDB destacam-se:

## Internet das Coisas (IoT)

Sensores instalados em residências, indústrias e cidades inteligentes geram informações constantemente sobre temperatura, umidade, consumo energético, localização e outras variáveis.

## Monitoramento de Infraestrutura e DevOps

Empresas utilizam o InfluxDB para armazenar métricas de servidores, aplicações, bancos de dados e dispositivos de rede, permitindo identificar falhas e gargalos de desempenho.

## Mercado Financeiro

Instituições financeiras utilizam bancos de séries temporais para registrar oscilações de preços, volumes de negociação e indicadores econômicos em tempo real.

## Sistemas de Monitoramento Industrial

Equipamentos industriais produzem dados continuamente, exigindo armazenamento eficiente e consultas rápidas para análises operacionais.

Dessa forma, o InfluxDB representa uma tecnologia moderna e amplamente utilizada em ambientes corporativos, tornando-se uma excelente opção para estudo na disciplina de Projeto e Administração de Banco de Dados.

---

# 4. Objetivo do Seminário

O seminário tem como objetivo apresentar os conceitos fundamentais dos bancos de dados de séries temporais e demonstrar, na prática, como o InfluxDB realiza o armazenamento, gerenciamento e análise de dados temporais.

Além disso, busca-se evidenciar as diferenças entre bancos relacionais tradicionais e bancos especializados em séries temporais, destacando os cenários em que cada tecnologia apresenta melhor desempenho.

---

# 5. Proposta Prática

A atividade prática consistirá na construção de um ambiente de monitoramento simplificado utilizando o InfluxDB para armazenar dados simulados de sensores climáticos.

O cenário escolhido será a coleta de informações de temperatura e umidade da cidade de Caicó/RN, permitindo demonstrar as principais funcionalidades do SGBD.

## 5.1 Provisionamento do Ambiente

O InfluxDB será executado utilizando containers Docker.

Essa abordagem permitirá:

* Facilidade de instalação;
* Isolamento do ambiente;
* Reprodutibilidade da demonstração;
* Utilização de práticas modernas de infraestrutura.

## 5.2 Configuração Inicial

Após a inicialização do ambiente serão configurados:

* Organization;
* Bucket;
* Usuário administrador;
* Token de autenticação.

Essa etapa demonstrará os mecanismos básicos de administração e segurança da plataforma.

## 5.3 Modelagem dos Dados

Será apresentada a estrutura utilizada pelo InfluxDB para armazenamento de séries temporais.

Exemplo conceitual:

Measurement:

* clima

Tags:

* cidade = Caicó
* estado = RN

Fields:

* temperatura
* umidade

Timestamp:

* data e horário da coleta

## 5.4 Inserção de Dados

Os dados serão enviados para o banco utilizando o Line Protocol do InfluxDB através de comandos cURL.

Essa etapa demonstrará:

* Processo de ingestão de dados;
* Estrutura de armazenamento;
* Eficiência na gravação de informações temporais.

## 5.5 Consultas de Dados

Serão realizadas consultas utilizando as ferramentas disponibilizadas pelo próprio InfluxDB para recuperar informações armazenadas.

Serão demonstrados exemplos de:

* Consulta por intervalo de tempo;
* Filtragem por tags;
* Recuperação dos registros mais recentes;
* Visualização histórica dos dados.

## 5.6 Visualização e Análise

Utilizando o Data Explorer do InfluxDB serão gerados gráficos em tempo real para exibir a evolução das medições de temperatura e umidade.

Essa etapa permitirá observar como o banco de dados processa e apresenta informações temporais de forma imediata.

---

# 6. Funcionalidades do InfluxDB que Serão Demonstradas

Durante a apresentação serão exploradas as seguintes funcionalidades:

* Administração de Buckets;
* Controle de acesso por Tokens;
* Armazenamento de séries temporais;
* Utilização de Measurements, Tags e Fields;
* Ingestão de dados utilizando Line Protocol;
* Consultas temporais;
* Visualização gráfica integrada;
* Organização eficiente de dados históricos;
* Processamento otimizado para grandes volumes de registros.

---

# 7. Resultados Esperados

Ao final da demonstração espera-se comprovar que o InfluxDB é uma solução eficiente para cenários que exigem armazenamento e análise de dados temporais.

Também será possível compreender as diferenças entre bancos de dados relacionais tradicionais e bancos especializados em séries temporais, identificando os cenários em que cada abordagem é mais adequada.

---

# 8. Material Desenvolvido

Para complementar a apresentação do seminário, será disponibilizado um repositório no GitHub contendo todo o material utilizado durante o desenvolvimento da pesquisa e da demonstração prática. O objetivo é permitir que qualquer usuário consiga reproduzir o ambiente e executar os exemplos apresentados durante o seminário.


## Material disponibilizado

### instalacaoambiente.md

Arquivo contendo o procedimento completo para instalação do Docker, criação do container e inicialização do InfluxDB OSS v2.

### demostracaopratica.md

Guia passo a passo da demonstração prática, desde a configuração inicial até a consulta e visualização dos dados no Data Explorer.


## Código Utilizado na Demonstração

Durante a apresentação será utilizado o seguinte comando para iniciar o ambiente do InfluxDB utilizando Docker:

```bash
docker run -d \
-p 8086:8086 \
--name influxdb_seminario \
-v influxdb_data:/var/lib/influxdb2 \
influxdb:2
```

Após a inicialização do ambiente, toda a demonstração será realizada pela interface web do **InfluxDB OSS v2**, contemplando as seguintes etapas:

- Configuração do usuário administrador;
- Criação da Organization;
- Criação do Bucket;
- Geração do API Token;
- Inserção de dados utilizando o recurso **Load Data → Line Protocol**;
- Consulta das informações no **Data Explorer**;
- Visualização gráfica das medições de temperatura e umidade.

Todo o material, incluindo os códigos utilizados na prática, permanecerá disponível no repositório GitHub para consulta e reprodução da demonstração.

# Referências

* INFLUXDATA. InfluxDB Documentation. Disponível em: [https://docs.influxdata.com/](https://docs.influxdata.com/influxdb/v2/get-started/). Acesso em: 23 jun. 2026.

* DOCKER HUB. InfluxDB Official Image. Disponível em: https://hub.docker.com/_/influxdb. Acesso em: 23 jun. 2026.
