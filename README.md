# Tchelinux Website


```sh
snap install hugo
git clone git@github.com:tonybolzan/tchelinux.git
cd tchelinux
hugo server --baseURL="http://127.0.0.1/" --watch
```

# Contribuindo
```sh
EVNAME=sm
EVYEAR=2020
echo -e '---\ntype: "page"\nlayout: "event"\n---' > content/events/$EVYEAR-$EVNAME.md
cp $HOME/cover1280x512.jpg static/img/events/$EVYEAR-$EVNAME/cover.jpg
cp data/events-template.json data/events/$EVYEAR-$EVNAME.json
edit data/events/$EVYEAR-$EVNAME.json
xdg-open http://127.0.0.1:1313/events/$EVYEAR-$EVNAME/
```

# Estrutura
```
config.yml                                  - Menus de navegação
content/_index.(br|en).md                   - Texto de apresentação
content/events/                             - Arquivos de referência padrão (não alterar)
data/events/*.json                          - Arquivo contendo todo o conteúdo dos eventos
static/img/events/<ano>-<evento>/cover.jpg  - Imagem 1280x512 do banner de cada evento
static/img/sponsors/*.(jpg|png)             - Imagens dos patrocinadores e apoiadores referenciadas no json
layouts/                                    - Layout html para construção das paginas dos eventos
```
