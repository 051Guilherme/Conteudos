# Comandos Para Usar No Git

### Configuração **Importante!**

Define quem está fazendo os commits:
~~~bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
~~~

Define o nome da branch principal por padrão: (MAIN)
~~~bash
git config --global init.defaultBranch main
~~~

Mostra as configurações:
~~~bash
git config --list
~~~

### Iniciando Repositório

Inicializa o controle de versão na pasta atual:
~~~bash
git init
~~~

Adiciona um novo repositório remoto:
~~~bash
git remote add origin <url>
~~~

Cria uma cópia local completa do repositório remoto:
~~~bash
git clone <url>
~~~

### Fluxo

Adiciona arquivos ao stage
~~~bash
git add arquivo.txt = Arquivo Específico
                Ou
git add .           = Adiciona todas as alterações
~~~

Salva permanentemente as alterações que estão no stage:
~~~bash
git commit -m "descrição clara do que foi feito"
~~~

Publica os commits locais no repositório remoto:
~~~bash
git push origin main
~~~

### Branches

Listar branches existentes
```bash
git branch
```

Criar uma nova branch
```bash
git branch minha-branch
```

Muda o diretório de trabalho para a branch escolhida.
```bash
git checkout minha-branch
```

Criar e trocar de branch ao mesmo tempo
```bash
git checkout -b minha-branch
```

