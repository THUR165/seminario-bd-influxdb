# Instalação do Ambiente

## Pré-requisito

Para executar o InfluxDB OSS v2 é necessário possuir o **Docker** instalado no sistema operacional.

### Instalação do Docker

#### Ubuntu/Debian

Atualize os pacotes do sistema:

```bash
sudo apt update
```

Instale o Docker:

```bash
sudo apt install docker.io -y
```

Habilite o serviço para iniciar automaticamente:

```bash
sudo systemctl enable docker
```

Inicie o serviço:

```bash
sudo systemctl start docker
```

Verifique se a instalação foi realizada com sucesso:

```bash
docker --version
```

Opcionalmente, adicione seu usuário ao grupo Docker para evitar o uso do `sudo`:

```bash
sudo usermod -aG docker $USER
```

Após executar esse comando, faça logout e login novamente ou reinicie o computador.

---

## Executando o InfluxDB OSS v2

Com o Docker instalado, execute o seguinte comando para iniciar o InfluxDB:

```bash
docker run -d \
-p 8086:8086 \
--name influxdb_seminario \
-v influxdb_data:/var/lib/influxdb2 \
influxdb:2
```

### Explicação dos parâmetros

| Parâmetro | Descrição |
|-----------|-----------|
| `-d` | Executa o container em segundo plano. |
| `-p 8086:8086` | Mapeia a porta padrão do InfluxDB para o computador local. |
| `--name influxdb_seminario` | Define um nome para o container. |
| `-v influxdb_data:/var/lib/influxdb2` | Cria um volume persistente para armazenar os dados. |
| `influxdb:2` | Utiliza a imagem oficial do InfluxDB OSS versão 2. |

---

## Primeiro Acesso

Após iniciar o container, abra o navegador e acesse:

```
http://localhost:8086
```

Na primeira execução será necessário realizar a configuração inicial do ambiente.

Configure:

- Usuário administrador;
- Senha;
- Organization;
- Bucket;
- API Token.

Esses elementos serão utilizados para armazenar e gerenciar os dados durante a demonstração prática.

---

## Verificando se o Container está em Execução

Para confirmar que o InfluxDB está funcionando corretamente, execute:

```bash
docker ps
```

A saída deverá ser semelhante a:

```text
CONTAINER ID   IMAGE        STATUS      PORTS
xxxxxxxxxxxx   influxdb:2   Up          0.0.0.0:8086->8086/tcp
```

Se o container estiver listado com o status **Up**, o ambiente está pronto para uso.