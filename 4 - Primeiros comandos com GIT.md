## Primeiros comandos com GIT

### Iniciando o GIT e criando um commit

-Iniciar o GIT

`git init`

Quando usamos este comando dentro de uma pasta, permitimos que o GIT comece a gerenciar e versionar o nosso código.

Na primeira vez que você estiver usando o GIT, você terá que fazer algumas configurações para se registrar, já que os commits exigem um autor, faça isso com os comandos:

`git config --global user.email "seu@email.com"`

`git config --global user.name seuNickName`

-Iniciar o versionamento

`git add`

-Criar um commit

`git commit -m "comentário"`