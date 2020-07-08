# Livro Online - Testes

Esse material foi desenvolvido utilizando a ferramenta de geração de página estáticas [MkDocs](https://www.mkdocs.org/#mkdocs). Essa ferramenta utiliza arquivos fonte no formato Markdown, mas existem extensões que possibilitam ler o formato Jupyter Notebook (.*ipynb*). A configuração dos plugins, páginas, menus entre outros é feita através de um arquivo YAML. 

- [Livro Online - Testes](#livro-online---testes)
  - [Instalação](#instalação)
    - [Instalando o Python e o PIP](#instalando-o-python-e-o-pip)
    - [Instalando o MkDocs](#instalando-o-mkdocs)
  - [Execução](#execução)
  - [Desenvolvimento](#desenvolvimento)
    - [Menu](#menu)
    - [Adicionando conteúdo](#adicionando-conteúdo)


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

Vale ressaltar que em alguns sistemas operacionais é possível instalar o MkDocs diretamente pelo *package manager*. Nesse tutorial vamos utilizar o `pip`, 

```properties
pip install mkdocs
```

A seguir, verifique se o pacote foi instalado corretamente.

```console
$ mkdocs --version
mkdocs, version 0.15.3
```

## Execução

O MkDocs vem com um *dev-server* nativo, que permite visualizar a documentação a medida que você vai trabalhando nela. Uma vez estando no mesmo diretório do arquivo `mkdocs.yml`, inicie o server executando o seguinte comando:

```console
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 160402 15:50:43 server:271] Serving on http://127.0.0.1:8000
[I 160402 15:50:43 handlers:58] Start watching changes
[I 160402 15:50:43 handlers:60] Start detecting changes
```

Basta abrir a url `http://127.0.0.1:8000/` em seu browser.

## Desenvolvimento

### Menu

A estrutura de menus pode ser configurada a partir do arquivo `mkdocs.yml`.

```YAML
nav:
    - Home: 'index.md'
    - 'User Guide':
        - 'Writing your docs': 'writing-your-docs.md'
        - 'Styling your docs': 'styling-your-docs.md'
    - About:
        - 'License': 'license.md'
        - 'Release Notes': 'release-notes.md'
```

Com a configuração acima, nós temos 3 itens no *top level*: `Home`, `User Guide` e `About`. `Home` é um link para a homepage do site. Sob a seção `User Guide`, duas páginas são listadas. Por fim, na seção `About` mais duas páginas são listadas.

### Adicionando conteúdo

Para adicionar um vídeo do youtube, basta copiar o código do vídeo, fornecido pelo próprio youtube e adicionar em uma página .md. As dimensões podem ser configuaradas facilmente.

```markdown
[!embed](https://www.youtube.com/watch?v=xIGre_E2_og =100x20)
```