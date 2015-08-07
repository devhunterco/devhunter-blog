# Devhunter blog

Pensamientos de devhuntercito en Hugo y gh-pages.


### Requisitos

- Instalar [golang](https://golang.org/)

>Luego instalar hugo directamente de Github

```bash
export GOPATH=$HOME/go
$ go get -v github.com/spf13/hug
```


### Como contribuir

En la comunidad devhunter eres libre de publicar cualquier idea, tutorial, experiencia o articulo siempre y cuando el contenido no viole el [código de conducta](https://github.com/devhunterco/community-docs/blob/master/CodigoDeConducta.md) de la comunidad.

Para publicar debes hacer lo siguiente:

>Clona el repositorio

```bash
$ git clone https://github.com/devhunterco/blog

```

>Crea un nuevo archivo `nombre_de_tu_post.md` en la carpeta `content`

```bash
$ touch content/nombre_de_tu_post.md

```

>Indica los `metadados` del post, asi:

```md

+++
date = "AA-MM-DD"
title = "Título del post"
summary = "Una breve introducción"
author_user_devhunter = "Tu usuario en la comunidad devhunter"
author_mail = "Tu correo"
+++

```

>Luego justo debajo, escribe tu post usando [markdown](http://daringfireball.net/projects/markdown/syntax)


Cuando termines haces un commit y luego envia un [pull request](https://help.github.com/articles/creating-a-pull-request/) a este repo y listo!
