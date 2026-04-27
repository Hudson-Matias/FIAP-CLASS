O protocolo de resolução de nomes ou Domain Name System (DNS), define um serviço automático que compara nomes de recursos com endereços de rede solicitados, incluindo consultar, responder e formatar dados. A intercomunicação do protocolo DNS usa um único formato chamado mensagem.
Esse padrão de mensagem é usado para quaisquer outros tipos de consultas e respostas de servidores, mensagens de erro e transferências de dados de registros ou recursos de servidores, de acordo com a figura 5 - “DNS”:
![[Pasted image 20260416114055.png]]
Os servidores DNS guardam diferentes tipos de registros de recursos usados para resolver nomes. Esses registros contêm o nome, endereço e tipo do registro. Esses tipos de registro incluem: IPv4 do dispositivo do terminal.
- Um IPv4 de dispositivo - A.
- Um servidor de nomes autoritativo - NS.
- um endereço IPv6 - AAAA.
- Um registro de troca de e-mails - MX.
Quando um host faz uma consulta, o processo DNS do servidor primeiro examina seu próprio registro para resolver o nome. Se não conseguir resolver o nome usando seus registros guardados, entrará em contato com outros servidores para concluir a tarefa. Quando uma correspondência é encontrada e retornada ao servidor solicitante original, o servidor guarda temporariamente o número do endereço, caso o mesmo nome seja solicitado novamente.
O serviço de cliente DNS nos computadores Windows também guarda nomes resolvidos anteriormente na memória. O comando ipconfig /displaydns mostra todas as entradas de nomes de domínio em cache.
A hierarquia se parece com uma árvore invertida, com suas raízes no topo e ramificações abaixo, como mostra a figura 5 - “DNS”, usando nomes de domínio para formar uma hierarquia.
A estrutura de nomes é dividida em áreas fáceis de gerenciar. Cada servidor de nomes de domínio mantém um arquivo de banco de dados específico e é responsável apenas pelo gerenciamento do mapeamento de nome para IP dessa pequena parte da estrutura de nomes de domínio. Quando o servidor de nomes de domínio recebe uma solicitação para converter um nome que não pertence à sua zona DNS, o servidor de nomes de domínio o encaminha para outro servidor de nomes de domínio na zona correspondente para conversão.  
O DNS é altamente escalável porque a resolução do nome do nó de rede é distribuída por vários servidores. Muitos domínios de grande porte representam um tipo de organização ou país de origem. Exemplos:
- .com - Comércio;
- .org - Organização beneficente;
- .br - Brasil;
- .it - Itália.
Ao configurar dispositivos de rede, um ou mais endereços de servidor de nomes de domínio serão fornecidos para que os clientes de nomes de domínio possam usá-los na resolução de nomes. Normalmente, o provedor de Internet − ISP fornece um endereço usado como servidor DNS. Quando o aplicativo de um usuário solicita a conexão a um dispositivo por nome, o cliente DNS solicitante consulta o servidor de nomes para resolver o nome para um endereço numérico.  
Os sistemas operacionais de computador também possuem um utilitário chamado **nslookup**, que permite aos usuários consultar manualmente servidores de nomes para resolver nomes de dispositivos de rede específicos. Esse programa também pode ser usado para corrigir problemas de resolução de nomes e verificar o status atual do servidor de nomes.
![[Pasted image 20260416115929.png]]