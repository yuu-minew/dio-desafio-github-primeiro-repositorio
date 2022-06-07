# Introdução ao Git/GitHub

Git é um sistema de código aberto e gratuito para controle de versão.
Criado pelo Linus e seu time, na necessidade de um sistema melhor.
Permite gravar alterações em arquivos ao longo do tempo, permitindo ter acesso e visualizar versões específicas desses arquivos.
Ele faz-se necessário para diminuir conflitos entre os códigos de cada desenvolvedor.

Ao usar o Git é necessário armazenar seu repositório em algum lugar. Pode ser feito offline, no seu próprio PC ou de forma online, através do Git Hub. (Funciona como "nuvem" dos códigos)

##Comandos Básicos
1. Windows (cmd)
cd **mudar/navegar diretório**
cd .. **voltar diretório**
cls **limpar tela**
TAB **auto completa**
dir **listar diretórios**
mkdir **criar diretório**
echo hello
hello > hello.txt **se não tiver o arquivo, ele é criado**
del **deleta os arquivos**
rmdir "nome do diretório" /S /Q **deleta o diretório**

2. Unix
cd **mudar/navegar diretório**
cd .. **voltar diretório**
clear **limpar tela** ou CTRL+L
TAB **auto completa**
ls **listar diretórios**
mkdir **criar diretório**
echo hello
hello > hello.txt **se não tiver o arquivo, ele é criado**
rm -rf "nome do diretório" **deleta o diretório**

##Como o Git funciona
1. SHA1
Segurança, criptografa
Gera conjunto de 40 caracteres
Forma curta de representar um arquivo

2. Objetos Fundamentais
BLOBS (Bolha) tipo tamanho \0 texto
TREES \0 armazena blob commit tamanho texto nome do arquivo
COMMITS

3. Sistema distribuido seguro

##Iniciando o Git e commit
Escolher o diretório
Git Bash
git init **iniciar o git**
ls **listar**
ls -a **listar arquivos ocultos**

##Configurar o Git (Windows)
Abrir o terminal
git config --global user.name "yuu-minew"
git config --global user.email "yuu.minew@gmail.com"

**git bash importante!** facilita o uso

##Criar chave SSH
abrir o terminal
ssh-keygen -t ed25519 -C "yuu.minew@gmail.com"
confirmar o local
colocar senha
Verificar
cd /c/Users/Kosug/.ssh/
ls
Vai listar duas chaves, uma pública e a privada
cat id_ed25519.pub
Vai dar a chave para colar no GitHub>SSH keys

eval $(ssh-agent -s)
Agent pid 1234 *esse número muda*
ls
id_ed25519 id_ed25519.pub
ssh-add id_ed25519
Colocar a senha
Identidade Adicionada

##Clonar um repositório
git clone "colar SSH, copiado do github"
yes
ls *verificar*

###Markdown é uma sintaxe usada para padronizar e facilitar a formatação de texto na web. (.md)

##Iniciando Git e commit
Voltando ao diretório, criar um arquivo de texto.md
git bash
git add * **adicionar ao git**
git commit -m "mensagem do commit inicial" **commit ao git**

##Ciclo de Vida dos arquivos Git

Untracked > (tracked) Unmodified > Modified > Stage

##Trabalhando com o Git Hub
É melhor usar o mesmo e-mail e username nas duas contas (Git/GitHub), pois facilita a interação.
git config--ls

Caso queira alterar o e-mail
git config --global --unset user.email
git config --global --unset user.name

##Criar Repositório
GitHub>Criar Repositório>Nome>Public/Private>README>Create
[Git]
ls
git remote add origin "link do repositório do github"
git remote -v
git status **verifica o atualizações/status**
git push origin master

##Resolvendo Conflitos
git status
**modified: README.md**
git add *
ls
git status
**modified: README.md**
git commit -m "adiciona msg"
git push origin master
**![rejected] error: failed to push some refs to ...**
git pull origin master
**merge failed**
abrir o arquivo e arrumar manualmente
git status
**both modified**
git add *
git commit -m "msg"
git push origin master