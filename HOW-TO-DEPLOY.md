# How to deploy

### FLASK ML
[<img src="https://img.shields.io/static/v1?label=&message=API&color=red">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=AZURE-DIEGO&color=aqua">](<LINK>)

Microsserviço de Machine Learning

http://pycemaker.centralus.cloudapp.azure.com:5000/

```bash
docker compose up
```

### NIFI ETL
[<img src="https://img.shields.io/static/v1?label=&message=GUI&color=blue">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=AZURE-DIEGO&color=aqua">](<LINK>)

Aplicação NiFI que extrai as métricas do Prometheus, transforma e armazena em Banco de Dados MongoDB

http://pycemaker.centralus.cloudapp.azure.com/nifi/

```bash
docker run --name nifi -d -p 80:80 \
 -e NIFI_WEB_HTTP_PORT='80' \
 -e TZ=America/Sao_Paulo \
 apache/nifi:latest
```

### FLASK ETL
[<img src="https://img.shields.io/static/v1?label=&message=API&color=red">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=TESTER&color=gold">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=AZURE-PEDRO&color=aqua">](<LINK>)

Aplicação Flask que extrai as métricas do Prometheus, transforma e armazena em Banco de Dados MongoDB

http://pcm.centralus.cloudapp.azure.com:5000/

```bash
docker compose up
```

### LOCUST LOADER
[<img src="https://img.shields.io/static/v1?label=&message=EXEC&color=GREEN">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=AZURE-GUILHERME&color=aqua">](<LINK>)

Aplicação que simula concorrência de uso na aplicação Formulário

~~http://pyc.centralus.cloudapp.azure.com:8089/~~

```bash
docker run -d -p 8089:8089 \
 -v $PWD:/mnt/locust locustio/locust \
 -f /mnt/locust/locustfile.py \
 --headless \ 
 --csv=/mnt/locust/output
```

### LOCUST TESTER
[<img src="https://img.shields.io/static/v1?label=&message=GUI&color=blue">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=TESTER&color=gold">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-DIEGO&color=purple">](<LINK>)

Aplicação para testes e estresse da aplicação alvo

http://pcm-tester.herokuapp.com/

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/pycemaker/pycemaker-locust-tester/tree/main)

### PROMETHEUS
[<img src="https://img.shields.io/static/v1?label=&message=GUI&color=blue">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=AZURE-PEDRO&color=aqua">](<LINK>)

http://pcm.centralus.cloudapp.azure.com:9090/

```bash
docker run -p 9090:9090 \
 --name prometheus \
 -v /home/pycemaker/pcm/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \
 prom/prometheus
```

### MONGODB
[<img src="https://img.shields.io/static/v1?label=&message=DB&color=fuchsia">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=ATLAS-DIEGO-OUTLOOK&color=greenyellow">](<LINK>)

Banco de Dados que registra os dados coletados o Prometheus

<a>mongodb+srv://pycemaker.rbp9n.mongodb.net/pycemaker</a>

### MONGODB
[<img src="https://img.shields.io/static/v1?label=&message=DB&color=fuchsia">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=TESTER&color=gold">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=ATLAS-DIEGO-GMAIL&color=greenyellow">](<LINK>)

Banco de Dados que registra os dados coletados o Prometheus

<a>mongodb+srv://pcmtest.ipgwp.mongodb.net/pycemaker</a>

### DASHBOARD API
[<img src="https://img.shields.io/static/v1?label=&message=API&color=red">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-PEDRO&color=purple">](<LINK>)

API da Aplicação Dashboard

http://pcm-dash-api.herokuapp.com/

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/pycemaker/pycemaker-dashboard-api/tree/main)

### DASHBOARD CLIENT
[<img src="https://img.shields.io/static/v1?label=&message=GUI&color=blue">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-DIEGO&color=purple">](<LINK>)

Aplicação que exibe em tempo real métricas de uso e da saúde do sistema

http://pycemaker-dashboard.herokuapp.com/

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/pycemaker/pycemaker-dashboard-client/tree/main)

### POSTGRESQL
[<img src="https://img.shields.io/static/v1?label=&message=DB&color=fuchsia">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-DIEGO&color=purple">](<LINK>)

Banco de Dados que registra os dados do Formulário

~~<a>postgresql://pcm.centralus.cloudapp.azure.com:5432/</a>~~

### FORM SERVER
[<img src="https://img.shields.io/static/v1?label=&message=API&color=red">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=AZURE-PEDRO&color=aqua">](<LINK>)

API da Aplicação Formulário, sendo o alvo de testes e desenvolvimento do Machine Learning

http://pcm.centralus.cloudapp.azure.com:8080/

```bash
docker compose up
```

### FORM CLIENT
[<img src="https://img.shields.io/static/v1?label=&message=GUI&color=blue">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-PEDRO&color=purple">](<LINK>)

Aplicação Formulário que cadastra e lista usuários

http://pycemaker-form.herokuapp.com/

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/pycemaker/pycemaker-form-client/tree/main)

### ~~PROMETHEUS~~
[<img src="https://img.shields.io/static/v1?label=&message=GUI&color=blue">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=DESUSO&color=orange">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-PEDRO&color=purple">](<LINK>)

Aplicação que gera métricas de consumo da aplicação Formulário

http://pcm-prometheus.herokuapp.com/

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/diegosilva789/pycemaker-prometheus/tree/main)

### ~~POSTGRESQL~~
[<img src="https://img.shields.io/static/v1?label=&message=DB&color=fuchsia">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=DESUSO&color=orange">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-PEDRO&color=purple">](<LINK>)

Banco de Dados que registra os dados do Formulário

<a>postgres://ec2-18-210-64-223.compute-1.amazonaws.com:5432/d6vpo0ahvprdqq</a>

### ~~FORM SERVER~~
[<img src="https://img.shields.io/static/v1?label=&message=API&color=red">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=DESUSO&color=orange">](<LINK>) [<img src="https://img.shields.io/static/v1?label=&message=HEROKU-PEDRO&color=purple">](<LINK>)

API da Aplicação Formulário, sendo o alvo de testes e desenvolvimento do Machine Learning

http://pycemaker.herokuapp.com/

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/pycemaker/pycemaker-form-server/tree/main)
