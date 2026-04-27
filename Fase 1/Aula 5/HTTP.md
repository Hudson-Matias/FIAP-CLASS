Ao inserir um endereço da WWW ou URL em um navegador web, ele usará o protocolo da camada de aplicação para estabelecer uma conexão com um serviço da web em execução no servidor.
URLs URIs são os nomes que a maioria das pessoas associam as URLs. Para entender melhor como um navegador da internet e um host da internet interagem, podemos ver como uma página da internet é aberta. Neste exemplo, vemos a URL do site do cisco.
Primeiro, como mostra a figura 4 - "Aplicação (HTTP)", o navegador interpreta as três partes da URL:
1. **HTTP** - Protocolo;
2. **www.cisco.com** - servidor;
3. **index.html** - o nome do arquivo.

O navegador procura o servidor de nomes, converte www.cisco.com em um IP digital e depois usa-o para interconectar-se ao servidor. O uso do protocolo HTTP exige que o navegador envie uma solicitação GET ao servidor e solicite um arquivo index.html. O servidor envia o HTML da página da web para o browning e, por fim, o navegador descriptografa o HTML e formata a página na janela do browning.
![[Pasted image 20260414132620.png]]

O **protocolo HTTP** qualifica um protocolo de solicitação/resposta: quando um host cliente (geralmente um navegador web) envia uma solicitação para um servidor da web HTTP, ele especifica o tipo de mensagem usada nessa conversa.
Os três principais tipos de mensagens HTTP são GET, POST e PUT.
- **GET** - É uma solicitação de host para obter informações. Um host (navegador web) envia um GET ao servidor www para solicitar uma página HTML.
- **POST** - Carrega arquivos de informações para o servidor de www como formulários de dados.
- **PUT** - Carrega recursos ou conteúdo para o servidor de www.

Embora o HTTP seja muito flexível, não é um protocolo seguro: a mensagem solicitada é enviada ao servidor em texto sem formatação e pode ser interceptada e lida. A resposta do servidor (geralmente uma página HTML) também não é criptografada. Para conversas seguras na Internet, use HTTPs, pois ele usa autenticação e criptografia para proteger os dados transmitidos entre clientes e servidores.