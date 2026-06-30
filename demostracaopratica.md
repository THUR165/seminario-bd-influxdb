# Roteiro da Demonstração Prática

Este roteiro descreve todas as etapas realizadas durante a demonstração prática do seminário utilizando o **InfluxDB OSS v2**.

---

## 1. Inicialização do Ambiente

Verifique se o container do InfluxDB está em execução:

```bash
docker ps
```

Caso o container não esteja em execução, inicie-o com:

```bash
docker start influxdb_seminario
```

Após iniciar o ambiente, acesse a interface web do InfluxDB:

```
http://localhost:8086
```

---

## 2. Configuração Inicial

Na primeira execução do sistema, realize a configuração inicial criando:

- Usuário Administrador;
- Organization;
- Bucket;
- API Token.

Esses recursos serão utilizados durante toda a demonstração.

---

## 3. Inserção dos Dados

Na interface do InfluxDB, acesse:

```
Bucket → +add data (no seu bucket criado) → Line Protocol
```


Copie todo o conteúdo do arquivo (insira uma linha por vez):

```
dados_climaticos.lp
```

Cole os dados no campo disponível e clique em:

**Escrever Dados (Write Data)**

Essa etapa realizará a inserção das medições simuladas no banco de dados.

---

## 4. Consulta dos Dados

Após a inserção, acesse:

```
Data Explorer
```

Configure a consulta utilizando os seguintes parâmetros:

**Bucket**

```
MeuBucket
```

**Measurement**

```
clima
```

**Fields**

- temperatura
- umidade
- pressao

selecione somente temperatura

Execute a consulta clicando em **Submit**.

---

## 5. Visualização dos Resultados

O Data Explorer exibirá gráficos contendo as medições armazenadas.

Durante a demonstração será possível alternar entre os diferentes campos (*Fields*) para visualizar:

- Evolução da temperatura;
- Variação da umidade;
- Oscilações da pressão atmosférica.

Essa funcionalidade evidencia a capacidade do InfluxDB em armazenar e visualizar dados de séries temporais em tempo real.

---

## Fluxo da Demonstração

```
Docker
      ↓
InfluxDB OSS v2
      ↓
Organization
      ↓
Bucket
      ↓
Line Protocol
      ↓
Armazenamento
      ↓
Data Explorer
      ↓
Gráficos
```

---

## Objetivo da Demonstração

Ao final da prática será possível compreender:

- Como instalar o InfluxDB utilizando Docker;
- Como configurar um ambiente de trabalho;
- Como armazenar dados utilizando o Line Protocol;
- Como consultar informações temporais;
- Como visualizar séries temporais através do Data Explorer.