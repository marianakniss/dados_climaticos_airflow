# Weather Data - Airflow

Este repositório contém um DAG (datapipeline orquestrado pelo Airflow) escrito em Python que se comunica com uma [API de previsão do clima](https://www.visualcrossing.com/weather-api) para extrair dados sobre determinada cidade.
O DAG contém 2 tarefas: a primeira cria uma pasta com a data da semana da extração de dados; a segunda se conecta à API, extrai os dados e os salva em 3 arquivos dentro da pasta da primeira tarefa - um arquivo com os dados brutos, outro com as temperaturas da semana e outro com as condições climáticas.

## Preparação do ambiente

Para o funcionamento do Airflow, é necessário um ambiente Unix (ou Docker em ambiente Windows), executando os comandos abaixo dentro do diretório onde está o DAG:

#### Atualizar pacotes:
```
sudo apt update
```
```
sudo apt upgrade
```

####  Usar diferentes versões do Python na mesma máquina:
```
sudo add-apt-repository ppa:deadsnakes/ppa
```

#### Instalar Python3.9 e o pacote de ambientes virtuais do Python3.9:
```
sudo apt install python3.9
```
```
sudo apt install python3.9-venv
```

#### Criar e ativar o ambiente virtual onde o Airflow vai rodar:
```
python3.9 -m venv venv
```
```
source venv/bin/activate
```

#### Instalar o airflow:
```
pip install 'apache-airflow==2.3.2' --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.3.2/constraints-3.9.txt"
```

#### Exportar a variável de ambiente:
```
export AIRFLOW_HOME=~/Documents/airflow
```

#### Subir uma instância do airflow:
```
airflow standalone
```

##### Após esses passos, é possível acessar o localhost no navegador para acessar a interface gráfica do Airflow e poder acompanhar a execução do DAG.
