# Backend Developer Learning Journey
![Backend Developer Learning Journey](https://roadmap.sh/roadmaps/backend.png)

# Summary
- [How does the internet works?](#how-does-the-internet-works)
- [What is HTTP?](#what-is-http)
- [DNS and how it works](#dns-and-how-it-works)
- [Configuring multiple git accounts](#configuring-multiple-git-accounts)
- [Operating System and how it works](#operating-system-and-how-it-works)
- [Guia de Instalação de Linguagens (Windows)](#guia-instalacao-linguagens-windows)
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

<a id="what-is-http"></a>
## What is HTTP?
The Hypertext Transfer Protocol (HTTP) is the foundation of the World Wide Web, and is used to load webpages using hypertext links. HTTP is an application layer protocol designed to transfer information between networked devices and runs on top of other layers of the network protocol stack. A typical flow over HTTP involves a client machine making a request to a server, which then sends a response message.

An HTTP request is the way Internet communications platforms such as web browsers ask for the information they need to load a website. Each HTTP request made across the Internet carries with it a series of encoded data that carries different types of information. A typical HTTP request contains:
 1. HTTP version type
 2. a URL
 3. an HTTP method
 4. HTTP request headers
 5. Optional HTTP body.

An HTTP method, indicates the action that the HTTP request expects from the queried server. For example, two of the most common HTTP methods are ‘GET’ and ‘POST’.

HTTP headers contain text information stored in key-value pairs, and they are included in every HTTP request (and response, more on that later). These headers communicate core information, such as what browser the client is using and what data is being requested.

The body of a request is the part that contains the ‘body’ of information the request is transferring. The body of an HTTP request contains any information being submitted to the web server, such as a username and password, or any other data entered into a form.

An HTTP response is what web clients (often browsers) receive from an Internet server in answer to an HTTP request. These responses communicate valuable information based on what was asked for in the HTTP request. A typical HTTP response contains:
 1. an HTTP status code
 2. HTTP response headers
 3. optional HTTP body

[HTTP status](https://www.httpstatus.com.br/) codes are 3-digit codes most often used to indicate whether an HTTP request has been successfully completed. Status codes are broken into the following 5 blocks

 1. 1xx Informational
 2. 2xx Success
 3. 3xx Redirection
 4. 4xx Client Error
 5. 5xx Server Error

Keep in mind that HTTP is a “stateless” protocol, which means that each command runs independent of any other command. In the original spec, HTTP requests each created and closed a TCP connection. In newer versions of the HTTP protocol (HTTP 1.1 and above), persistent connection allows for multiple HTTP requests to pass over a persistent TCP connection, improving resource consumption.

<a id="dns-and-how-it-works"></a>
## DNS and how it works
The Domain Name System (DNS) is the phonebook of the Internet. Humans access information online through domain names, like nytimes.com or espn.com. Web browsers interact through Internet Protocol (IP) addresses. DNS translates domain names to IP addresses so browsers can load Internet resources.

The process of DNS resolution involves converting a hostname (such as www.example.com) into a computer-friendly IP address (such as 192.168.1.1). An IP address is given to each device on the Internet, and that address is necessary to find the appropriate Internet device - like a street address is used to find a particular home. When a user wants to load a webpage, a translation must occur between what a user types into their web browser (example.com) and the machine-friendly address necessary to locate the example.com webpage.

When users enter a domain name into the address bar of their web browser, they will be taken to the site they want to visit. However, this seemingly instant task consists of several steps known as the DNS lookup or DNS resolution process. Here’s an example of what the DNS resolution process is typically like to illustrate better how DNS works.

 1. You want to be taken to Exemple website, so you enter the domain name exemple.com into the web browser’s address bar. What you’re doing here is submitting a DNS request.
 2. Next, your computer will check whether it already stored a DNS entry of the domain you submitted locally. A DNS record is an IP address that matches the fully-qualified domain name.
 3. First, your computer will search its hosts file and cache. The hosts file is a plain text file that maps hostnames to IP addresses in an operating system, while the cache is temporary data stored by a hardware or software component.
 4. Matching IP addresses for the DNS service are commonly found in your browser cache or internet service provider (ISP) cache. However, if no matching IP address is found in your hosts file and cache, other additional steps will be added to the DNS resolution process.
 5. Since your computer couldn't find a match locally, the DNS resolution process involves querying various servers, including the recursive resolver, root name server, TLD name server, and authoritative name server, until the correct IP address is obtained. This information is then cached for future use, enabling your computer to establish a connection with the website's server and take you to your desired destination.

<a id="configuring-multiple-git-accounts"></a>
## Configuring multiple git accounts
1. Create `.gitconfig`:
```
[includeIf "gitdir:~/Worspace/Personal/"]
path = ~/.gitconfig.personal
[includeIf "gitdir:~/Workspace/Work/"]
path = ~/.gitconfig.work
```
2. Create `.gitconfig.work`:
```
[user]
name = <your_username>
email = <your_work_email>
```
3. Create `.gitconfig.personal`:
```
[user]
name = <your_username>
email = <your_personal_email>
```
4. Finally, initialize Git (`git init`) in the directories: `~/Workspace/Personal/` and `~/Workspace/Work/`.

<a id="operating-system-and-how-it-works"></a>
## Operating System and how it works
An operating system (OS) is system software that hides hardware complexity, manages computer hardware and software resources, and provides common services for computer programs.

 1. Processes and Process Management

    A process is basically a program in execution. To put it in simple terms, we write our computer programs in a text file, and when we execute this program, it becomes a process which performs all the tasks mentioned in the program.

    When a program is loaded into the memory and it becomes a process, it can be divided into four sections ─ stack, heap, text, and data.
     - Stack: The process Stack contains the temporary data, such as method/function parameters, return address, and local variables. Think of it like a to-do list while playing a game. What tasks you need to complete, what items you have, and where you are in the game.
     - Heap: This is dynamically allocated memory to a process during its run time. This is like a flexible backpack. As you play, you might pick up new tools or items. The heap is where the game process stores these things.
     - Text: This includes the Program Counter (a pointer to the address of the next instruction to be executed for this process) and the contents of the processor’s registers. This is the actual game being played. What's happening right now, where your character is, and all the ongoing actions.
     - Data: This section contains the global and static variables. Here's where the game keeps track of everything it needs to remember—your score, the level you're on, and any other important info.

    When a process executes, it passes through different states. In general, a process can have one of the following five states at a time:
     - Start: The initial state when a process is first started/created.
     - Ready: The process is waiting to be assigned to a processor. Ready processes are waiting to have the processor allocated to them by the operating system so that they can run. A process may come into this state after the Start state, or while running it by but getting interrupted by the scheduler to assign CPU to some other process.
     - Running: Once the process has been assigned to a processor by the OS scheduler, the process state is set to running and the processor executes its instructions.
     - Waiting: the process moves into the waiting state if it needs to wait for a resource, such as waiting for user input, or waiting for a file to become available.
     - Terminated or Exit: Once the process finishes its execution, or it is terminated by the operating system, it is moved to the terminated state where it waits to be removed from main memory.

 2. Threads and Scheduling

    A thread is a flow of execution through the process code. It has its own program counter that keeps track of which instruction to execute next.

    A thread shares with its peer threads various information like code segment, data segment, and open files. When one thread alters a code segment memory item, all other threads see that.

    Threads provide a way to improve application performance through parallelism. Threads represent a software approach to improving the performance of operating systems by reducing the overhead.

    The process of scheduling is the responsibility of the process manager that handles the removal of the running process from the CPU and the selection of another process on the basis of a particular strategy.

    The Operating System maintains the following important process scheduling queues:
    - Job queue: This queue keeps all the processes in the system.
    - Ready queue: This queue keeps a set of all processes residing in the main memory, ready and waiting to execute. A new process is always put in this queue.
    - Device queues: The processes which are blocked due to unavailability of an I/O device constitute this queue.

    The OS can use different policies to manage each queue (FIFO, Round Robin, Priority, etc.).

 3. Memory Management

    Memory management is the functionality of an operating system which handles or manages primary memory.

    Memory management keeps track of each and every memory location, regardless of whether it is allocated to some process or free. It checks how much memory is to be allocated to processes. It decides which process will get memory at what time. And it tracks whenever memory gets freed up or unallocated, and correspondingly updates the status.

    - Logical Addresses:
      Think of these like virtual addresses. When a program runs, the CPU uses logical addresses to access memory. Each program believes it has the whole memory to itself, creating a conceptual view. It's like giving every program its own set of directions, and they don't know about each other.

    - Physical Addresses:
      Now, these are the real, physical locations in the computer's memory hardware. The operating system takes those virtual (logical) addresses and translates them into actual places in the computer's memory. It's like having a guide (the OS) that takes each program's directions and turns them into the real-world locations where data is stored.

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

<a id="guia-instalacao-docker-linux"></a>
## Guia de Instalação do Docker (Linux)
1. [Instale o Docker Engine usando o repositório apt.](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
2. [Configure o Docker como non-root user.](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user)
