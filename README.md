# Meu Enxoval Back-end

Este projeto contempla os requisitos para entrega do MVP da Sprint II da disciplina: **Desenvolvimento Back-end Avançado**, do curso de Pós-Graduação em Desenvolvimento FullStack pela PUC-Rio.

O propósito deste MVP (Produto Mínimo Viável) é aplicar o conhecimento adquirido nas aulas para criar um sistema web dedicado à elaboração de listas de enxoval de bebê. Este sistema visa auxiliar mães de primeira viagem e qualquer pessoa que queira compilar uma lista de itens essenciais para o enxoval do bebê.

Para alcançar esse objetivo, foi implementada uma API seguindo o padrão REST, que permite aos usuários realizar operações de consulta, adição, exclusão e edição de produtos armazenados em um banco de dados, seguindo o conceito CRUD (Create, Read, Update, Delete).

Como uma diretriz essencial para o desenvolvimento deste MVP, foi incorporado um serviço que consome dados de uma API externa. Mais especificamente, só é possível realizar o download da lista porque o sistema integra uma API pública que permite aos usuários exportar a lista de enxoval de bebê em formato Excel (por exemplo, .xlsx) para facilitar o compartilhamento e o armazenamento offline. Isso amplia a funcionalidade do sistema, permitindo que os usuários acessem e baixem suas listas em um formato conveniente a partir de uma fonte externa confiável.

As principais tecnologias que serão utilizadas aqui é o:
 - [Flask](https://flask.palletsprojects.com/en/2.3.x/)
 - [SQLAlchemy](https://www.sqlalchemy.org/)
 - [OpenAPI3](https://swagger.io/specification/)
 - [SQLite](https://www.sqlite.org/index.html)


Diagrama da arquitetura da aplicação e estratégias de comunicação implementadas neste MVP:
>https://drive.google.com/file/d/1FhFoFzJZCfz99QRLVnd7GHBNPOcQVcvA/view?usp=share_link

---
## Como Executar
Será necessário ter todas as libs python listadas no `requirements.txt` instaladas.
> É fortemente indicado o uso de ambientes virtuais do tipo [virtualenv](https://virtualenv.pypa.io/en/latest/installation.html).

---
### `` Observação 01`` - Pasta env existente

A pasta `env`, presente neste repositório, representa o ambiente virtual utilizado para construir esse projeto.
Nesta pasta todas as dependências e bibliotecas necessárias para executar esta API já se encontram instaladas.

Após clonar o repositório, é necessário ir ao diretório raiz, pelo terminal, para poder executar os comandos descritos abaixo.

**Passo I - Ative o ambiente virtual:**
```
source env/bin/activate
```
**Passo II - Para executar o servidor:**
```
(env)$ flask run --host 0.0.0.0 --port 5000
```
Em modo de desenvolvimento é recomendado executar utilizando o parâmetro reload, que reiniciará o servidor automaticamente após uma mudança no código fonte.
```
(env)$ flask run --host 0.0.0.0 --port 5000 --reload
```
**Passo III - Acesso no browser**
> Abra o [http://localhost:5000/#/](http://localhost:5000/#/) no navegador para verificar o status da API em execução.

---
### `` Observação 02`` - Pasta env Inexistente

Caso a pasta `env` neste repositório não exista ou não esteja disponível em sua máquina, siga os procedimentos a seguir:

**Passo I - Crie um Ambiente Virtual**

Após clonar o repositório, abra um novo terminal e digite o seguinte comando:
```
python -m venv env
```
> Este comando cria um novo ambiente virtual usando o módulo "env" do Python

**Passo II - Ative o ambiente virtual:**
```
source env/bin/activate
```
**Passo II - Instale os requirements**

As dependências/bibliotecas, descritas no arquivo `requirements.txt`.
```
(env)$ pip install -r requirements.txt
```
Depois siga os passos II e III respectivamente contidos na sessão de Observação 1.

## Como executar através do Docker

Certifique-se de ter o [Docker](https://docs.docker.com/engine/install/) instalado e em execução em sua máquina.

Navegue até o diretório que contém o Dockerfile e o requirements.txt no terminal.
Execute o seguinte comando para construir a imagem Docker:

```
$ docker build -t nome-da-pasta-api .
```

Uma vez criada a imagem, para executar o container basta executar, **como administrador**, seguinte o comando:

```
$ docker run -p 5000:5000 rest-api
```
Uma vez executando, para acessar a API, basta abrir o [http://localhost:5000/#/](http://localhost:5000/#/) no navegador.
