# Livro Online - Testes

Feito com [MkDocs](https://www.mkdocs.org/#mkdocs)

### Instalação

Pode ser feita utilizando algum package manager, buscando pelo pacote `MkDocs`. Caso não encontre uma versão recente, a instalação pode ser feita via `pip`.

Verifique se já possui Python no seu sistema, bem como o gerenciador pip:

```bash
$ python --version

Python 3.8.2

$ pip --version

pip 20.0.2 from /usr/local/lib/python3.8/site-packages/pip (python 3.8)
```

**Como dito pelo próprio site, MkDocs tem suporte para as seguintes versões do Python: 3.5,3.6,3.7,3.8 e pypy3.**

### Instalando MkDocs - pip

```bash
pip install mkdocs
```

Verifique se foi instalado corretamente com o comando:

```bash
$ mkdocs --version

mkdocs, version 0.15.3
```

### Manutenção

O MkDocs vem com um *dev-server* nativo, que permite visualizar a documentação a medida que você vai trabalhando nela. Uma vez estando no mesmo diretório do arquivo `mkdocs.yml`, inicie o server executando o seguinte comando:

```bash
$ mkdocs serve

INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 160402 15:50:43 server:271] Serving on http://127.0.0.1:8000
[I 160402 15:50:43 handlers:58] Start watching changes
[I 160402 15:50:43 handlers:60] Start detecting changes

```

Basta abrir a url `http://127.0.0.1:8000/` em seu browser.

#### Menu

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

#### Adicionando conteúdo

Para adicionar um vídeo do youtube, basta copiar o código do vídeo, fornecido pelo próprio youtube e adicionar em uma página .md. As dimensões podem ser configuaradas facilmente.

```html
<iframe width="600" height="400" src="https://www.youtube.com/embed/4dFVU-fTMkM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```