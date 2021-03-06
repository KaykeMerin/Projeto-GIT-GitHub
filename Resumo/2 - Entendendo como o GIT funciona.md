## Entendendo como o GIT funciona

### Tópicos fundamentais

Para entender seu funcionamento, deveremos entender alguns tópicos importantes antes:

**- SHA1**

É um algoritmo de encriptação, a grosso modo, ele pega seu arquivo e embaralha ele de uma forma específica. O conjunto de caracteres (40 dígitos) que é criado quando se roda este algoritmo vai ser alterado por qualquer alteração feita no arquivo.

**- Sistema Distribuído**

Caso você armazene seu código em uma nuvem (GitHub, por exemplo), você poderá ter muitas pessoas (maintainers) que também terão uma versão confiável do seu código.

**- Segurança**

Cada um dos objetos do GIT tem seu próprio SHA1. Se caso haja qualquer alteração em um arquivo dentro de uma blob por exemplo, todos os outros SHA1 também serão alterados, já que o commit aponta para árvores que apontam para essa blob com o arquivo. Isso torna os praticamente impossível uma alteração sem rastreamento de um commit.

**- Objetos internos**

BLOBS

São como “bolhas” que ficam guardados o conteúdo junto com alguns metadados (tipo (neste caso, blob), tamanho, \0 e “conteúdo”)

TREES

Responsável por montar a estrutura de onde estão localizados os arquivos. As árvores, além de apontar para blobs (ou outras árvores) também armazenam elas. 

COMMITS

É o objeto que junta os outros dois objetos e dá sentido a eles. Os commits apontam para: 

Árvores, parente (commit anterior), autor e mensagem (dá significado para as alterações).



### Chaves SSH (Linux)

Quando o momento de você colocar seu código no GitHub chegar, você terá que se autenticar. Uma das formas de fazer isso seria usando a chave SSH, que estabelece uma conexão segura e encriptada entre duas máquinas. 

Oque faremos é basicamente, configurar a nossa máquina local como uma máquina “confiável” para o GitHub.

1. Quando você já estiver com sua conta na plataforma do GitHub, vá em: 

   Configurações > SSH and GPG Keys > New SSH key

2. Após isso, volte para seu terminal e gere sua chave usando o comando:

   `ssh-keygen -t ed25519 -c seu@email.com`

3. Navegue até a pasta em que suas chaves foram criadas usando o comando:

​	`cd c/home/your_user/.ssh/`

4. Agora, para temos que visualizar o conteúdo da chave para colocar no GitHub, use:

​	`cat id_ed25519.pub`

​	Copie o conteúdo e cole na área Key. Não se esqueça de colocar um título para sua chave.

5. Por fim, teremos que inicializar o ssh agent para lidar com as chaves, use o comando:

   `eval $(ssh-agent -s)`

   `ssh-add id_ed25519`

6. Cadastre e confirme sua senha e pronto, você está autentificado.

