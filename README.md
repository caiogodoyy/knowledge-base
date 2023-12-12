# Guia de Instalação (Windows)

## MinGW

1. [Faça o download do instalador.](https://sourceforge.net/projects/mingw/)
2. Durante a instalação, marque as opções `mingw32-base` e `mingw32-gcc-g++`.
3. Complete a instalação e aplique as mudanças.
4. Configure as variáveis de ambiente:
   - Acesse as variáveis de sistema.
   - Adicione o diretório `C:\MinGW\bin` ao Path.

## Python

1. [Faça o download do instalador.](https://www.python.org/downloads/)
2. Durante a instalação, marque as opções `Use admin privileges when installing py.exe` e `Add python.exe to PATH`.
3. Prossiga com a instalação e feche o instalador.

## JDK (Java Development Kit)

1. [Faça o download do instalador.](https://www.oracle.com/br/java/technologies/downloads/)
2. Configure as variáveis de ambiente:
   - Adicione o diretório `C:\Program Files\Java\jdk-17\bin` ao caminho (Path).
   - Crie uma nova variável de sistema chamada `JAVA_HOME` com o valor `C:\Program Files\Java\jdk-17`.

# Configurando Múltiplas Contas do Git
1. Crie `.gitconfig`:
```
[includeIf "gitdir:~/Worspace/Personal/"]
path = ~/.gitconfig.personal
[includeIf "gitdir:~/Workspace/Work/"]
path = ~/.gitconfig.work
```
2. Crie `.gitconfig.work`:
```
[user]
name = <your_username>
email = <your_work_email>
```
3. Crie `.gitconfig.personal`:
```
[user]
name = <your_username>
email = <your_personal_email>
```
4. Por fim, inicialize o git (`git init`) nos diretórios: `~/Worspace/Personal/` e `~/Workspace/Work/`.
