# Backend Developer Learning Journey
![Backend Developer Learning Journey](https://roadmap.sh/roadmaps/backend.png)

# Summary
- [How does the internet works?](#how-does-the-internet-works)
- [Guia de Instalação de Linguagens (Windows)](#guia-instalacao-linguagens-windows)
- [Configurando Múltiplas Contas do Git](#configurando-multiplas-contas-git)
- [Guia de Instalação do Docker (Linux)](#guia-instalacao-docker-linux)

<a id="#how-does-the-internet-works"></a>
## How does the internet works?
There are two main concepts that are fundamental to the way the Internet functions: packets and protocols.
 - Packets: In networking, a packet is a small segment of a larger message. Each packet contains both data and information about that data. The information about the packet's contents is known as the "header," and it goes at the front of the packet so that the receiving machine knows what to do with the packet. To understand the purpose of a packet header, think of how some consumer products come with assembly instructions.

   When data gets sent over the Internet, it is first broken up into smaller packets, which are then translated into bits. The packets get routed to their destination by various networking devices such as routers and switches. When the packets arrive at their destination, the receiving device reassembles the packets in order and can then use or display the data.

   Packets are sent across the Internet using a technique called packet switching. Intermediary routers and switches are able to process packets independently from each other, without accounting for their source or destination. This is by design so that no single connection dominates the network. If data was sent between computers all at once with no packet switching, a connection between two computers could occupy multiple cables, routers, and switches for minutes at a time.
 
 - Protocols: A protocol is a standardized way of doing certain actions and formatting data so that two or more devices are able to communicate with and understand each other.

   There are protocols for sending packets between devices on the same network (Ethernet), for sending packets from network to network (IP), for ensuring those packets successfully arrive in order (TCP), and for formatting data for websites and applications (HTTP). In addition to these foundational protocols, there are also protocols for routing, testing, and encryption. And there are alternatives to the protocols listed above for different types of content — for instance, streaming video often uses UDP instead of TCP.

   Because all Internet-connected computers and other devices can interpret and understand these protocols, the Internet works no matter who or what connects to it.

<a id="guia-instalacao-linguagens-windows"></a>
## Guia de Instalação de Linguagens (Windows)
### MinGW
1. [Faça o download do instalador.](https://sourceforge.net/projects/mingw/)
2. Durante a instalação, marque as opções `mingw32-base` e `mingw32-gcc-g++`.
3. Complete a instalação e aplique as mudanças.
4. Configure as variáveis de ambiente:
   - Acesse as variáveis de sistema.
   - Adicione o diretório `C:\MinGW\bin` ao Path.
### Python
1. [Faça o download do instalador.](https://www.python.org/downloads/)
2. Durante a instalação, marque as opções `Use admin privileges when installing py.exe` e `Add python.exe to PATH`.
3. Prossiga com a instalação e feche o instalador.
### JDK (Java Development Kit)
1. [Faça o download do instalador.](https://www.oracle.com/br/java/technologies/downloads/)
2. Configure as variáveis de ambiente:
   - Adicione o diretório `C:\Program Files\Java\jdk-17\bin` ao caminho (Path).
   - Crie uma nova variável de sistema chamada `JAVA_HOME` com o valor `C:\Program Files\Java\jdk-17`.

<a id="configurando-multiplas-contas-git"></a>
## Configurando Múltiplas Contas do Git
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

<a id="guia-instalacao-docker-linux"></a>
## Guia de Instalação do Docker (Linux)
1. [Instale o Docker Engine usando o repositório apt.](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
2. [Configure o Docker como non-root user.](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user)
