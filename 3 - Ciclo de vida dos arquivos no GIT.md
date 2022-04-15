## Ciclo de vida dos arquivos no GIT

### Passo a passo no clico de vida

Para arquivos no GIT, temos dois agrupamentos básicos, Untracked (GIT tem ciência) e Tracked (GIT ainda não tem ciência). A partir disso, devemos saber que arquivos no agrupamento Tracked podem se subdividir em 3 estágios diferentes, são eles: 

- *Unmodified*

  Arquivo que ainda não foi modificado.

- *Modified*

  Arquivo unmodified que sofreu modificação.

- *Staged*

  Arquivos que estão se preparando para fazer parte de um commit.

Quando usamos `git init`, temos arquivos *untracked*, pois o GIT ainda não tem ciência da existência deles, assim que usamos `git add`, apresentamos ao GIT esses arquivos, então eles são movidos para *staged*, pois eles acabaram de ser apresentados e estão prontos para fazer parte de um commit.

Quando alteramos um arquivo *unmodifed*, ele passa automaticamente para *modified* (pois sofreu alterações). Então, usamos `git add` neste arquivo (que acaba de ser classificado como *modified*), para que ele se torne *staged*, e fique pronto para ser commitado. Nesta hora, usamos `git commit -m "comentário"`, para "selar" essas mudanças e torna-lo uma nova versão deste arquivo, ou seja, salvamos as alterações e voltamos ela ao seu estado inicial (*unmodified*).

O ambiente em que trabalhamos são divididos em duas partes, ambiente de desenvolvimento e servidor.

- Ambiente de desenvolvimento

  Versão que fica em nossa máquina.

  *Working Directory*

  *Staging Area*

  *Local Repository*

- Servidor

  Versão que fica no servidor (neste caso, GitHub)

  *Remote Repository*

Quando você adiciona um arquivo *untracked* e usa `git add`, ele é movido para *Staging Area*, a mesma coisa acontece para arquivos *unmodified* que são movidos para *modified* (transitam em *Working Directory* e *Staging Area*). Quando você commita os arquivos, eles são movidos para a *Local Repository* e desta forma poderá empurrar para o servidor (*Remote Repository*).