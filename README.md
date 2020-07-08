# Livro Online - Testes

Esse material foi desenvolvido utilizando a ferramenta de geração de página estáticas [MkDocs](https://www.mkdocs.org/#mkdocs). Essa ferramenta utiliza arquivos fonte no formato Markdown (*.md*), mas existem extensões que possibilitam ler o formato Jupyter Notebook (.*ipynb*). A configuração dos plugins, páginas, menus entre outros é feita através de um arquivo YAML. 

- [Livro Online - Testes](#livro-online---testes)
  - [Instalação](#instalação)
    - [Instalando o Python e o PIP](#instalando-o-python-e-o-pip)
    - [Instalando o MkDocs](#instalando-o-mkdocs)
  - [Execução](#execução)
  - [Desenvolvimento](#desenvolvimento)
    - [Menu](#menu)
    - [Adicionando conteúdo](#adicionando-conteúdo)
  - [Deploy](#deploy)


## Instalação

### Instalando o Python e o PIP

O Python e PIP já vem instalado em algumas distribuições Linux, então antes de proseguir, verifique se já possui no seu sistema.

```console
$ python --version
Python 3.8.2
```

```console
$ pip --version
pip 20.0.2 from /usr/local/lib/python3.8/site-packages/pip (python 3.8)
```

**Observação:** Como dito na própria [documentação](https://www.mkdocs.org/#manual-installation), o MkDocs tem suporte para as seguintes versões do Python: 3.5, 3.6, 3.7, 3.8 e PyPy3.

Para instalar em distribuições derivadas do *debian*, utilize o comando abaixo

```bash
sudo apt update
sudo apt install -y python3 python3-pip
```

Caso você possua um sistema operacional diferente, os links abaixo possuem tutoriais para a maior parte dos sistemas operacionais.

* Python [[Clique aqui](https://realpython.com/installing-python/)]
* Pip [[Clique aqui](https://pip.pypa.io/en/stable/installing/)]

### Instalando o MkDocs

Vale ressaltar que em alguns sistemas operacionais é possível instalar o MkDocs diretamente pelo *package manager*. Nesse tutorial vamos utilizar o `pip`.

```bash
pip install mkdocs
```

A seguir, verifique se o pacote foi instalado corretamente.

```console
$ mkdocs --version
mkdocs, version 0.15.3
```
Clone e entre no repositório do projeto.

```bash
git clone https://github.com/arma29/online-book.git
cd online-book
```

Instale as dependências do projeto.

```bash
pip install -r requirements.txt
```

## Execução

O MkDocs vem com um ambiente de desenvolvimento embutido, que permite visualizar a documentação a medida que você vai trabalhando nela. Inicie o servidor executando o comando abaixo.

```bash
mkdocs serve
```

Agora, basta abrir a url http://127.0.0.1:8000 em seu *browser*.

## Desenvolvimento

### Menu

A estrutura de menus pode ser configurada a partir do arquivo [mkdocs.yml](mkdocs.yml).

```yaml
site_name: Online Book
nav: 
  - Home: index.md
  - Notebook: notebooks/hello-world.ipynb 
  - Binder: https://mybinder.org/v2/gh/binder-examples/demo-julia/master?filepath=demo.ipynb
  - Aulas: 
    - Selenium: aula.md
    - Randoop: aula.md
...
```

Com a configuração acima, nós temos 4 itens no *top level*: `Home`, `Notebook`, `Binder` e `Aulas`. `Home` é um link para a homepage do site. Sob a seção `Aulas`, duas páginas são listadas.

![](https://i.imgur.com/5PoZFCD.png)

**Observação**: Os arquivos são lidos a partir do diretório [docs](docs/) na raiz do projeto, ou seja, para o arquivo `docs/index.md` basta especificar `index.md`.

### Adicionando conteúdo

O MkDocs aceita os formatos Markdown (*.md*) e Jupyter Notebook (.*ipynb*). Os arquivos de descrição estão dispostos no diretório `docs/` e os notebooks dentro do subdiretório `docs/notebooks`. Com o uso de Markdown é possível adicionar videos, *twetts*, postagens do Medium, entre outros conteúdos.

![](https://i.imgur.com/3MRUSMY.png)


## Deploy

Para realizar o *deploy* para o GitHub, basta executar o comando abaixo.

```bash
mkdocs gh-deploy
```

Se tudo der certo, a saída deve ser similar a essa.

```console
$ mkdocs gh-deploy
INFO    -  Cleaning site directory 
INFO    -  Building documentation to directory: /home/fmelo/Projects/university/online-book/site 
INFO    -  Documentation built in 0.43 seconds 
INFO    -  Copying '/home/fmelo/Projects/university/online-book/site' to 'gh-pages' branch and pushing to GitHub. 
INFO    -  Your documentation should shortly be available at: https://arma29.github.io/online-book/ 
```

Por trás dos panos, o conteúdo estático do site é gerado para o diretório site/, em seguida é criada uma branch chamada gh-pages, contendo o diretório recém criado. Basta acessar o site https://arma29.github.io/online-book/.
