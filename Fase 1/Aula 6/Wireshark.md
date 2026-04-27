O Wireshark tornou-se um dos programas sniffer de pacotes padrão do setor, usado por profissionais de rede e segurança da informação. Este software aberto está disponível para vários sistemas operacionais diferentes, incluindo Windows, Mac e Linux.
Instale e abra uma nova janela de terminal, e digite o comando ip a, e pressione enter.
Observe qual adaptador de rede o seu computador está usando para acessar a rede. Em seguida, registre o endereço IPv4 e o endereço MAC (endereço físico) da interface de rede. Além disso, você deve descobrir qual é o endereço IPv4 e o endereço MAC da interface de rede do seu roteador.
Capturando e analisar dados locais ARP no Wireshark. Para isso, a partir do Terminal do Kali Linux, executaremos o seguinte comando:
```sh
sudo wireshark
```

![[Pasted image 20260416145949.png]]

Digite a senha ao usuário.
Após iniciar o Wireshark, selecione a interface de rede que você identificou com o comando ip e inspira a palavra arp na caixa de filtro. Essa seleção configura o Wireshark para exibir somente os pacotes que fazem parte das trocas ARP entre os dispositivos na rede local.
![[Pasted image 20260416150158.png]]

Após selecionar a interface correta e inserir as informações de filtro, clique em Start (Iniciar) para começar a captura de dados. As informações começarão a passar abaixo da seção superior no Wireshark. Cada linha representa uma mensagem sendo enviada entre um dispositivo de origem e destino na rede.
A partir do Terminal do Kali Linux, use o comando ping para testar a conectividade para o endereço de gateway padrão que você identificou anteriormente.
![[Pasted image 20260416150436.png]]

Interrompa a captura de dados ao clicar em Stop Capture (Interromper Captura) na barra de ferramentas.
Examine os dados gerados pelas solicitações ping do seu computador. Os dados do Wireshark são exibidos em três seções, conforme apresentada na figura a seguir:
1. A seção 1 exibe a lista de quadros de PDU capturados com um sumário das informações do pacote de IPv4 listado.
2. A seção 2 lista as informações de PDU do quadro selecionado na parte superior da tela e separa um quadro de PDU capturado pelas suas camadas de protocolo.
3. A seção 3 mostra os dados brutos de cada camada. Os dados são exibidos em formato hexadecimal e decimal.
![[Pasted image 20260416151443.png]]

Clique nos quadros ARP na seção superior que tem o endereço MAC do seu computador (como o endereço de origem no quadro) e "transmissão" como o destino do quadro.
Com esse quadro de PDU ainda selecionado na seção superior, vá até a seção 2. Clique na seta à esquerda da linha Ethernet 2 para ver os endereços MAC de origem e destino.
![[Pasted image 20260416151737.png]]

Note que o endereço MAC de origem corresponde à interface do seu computador.
E, para finalizar, após a resposta ARP ser recebida pelo seu computador, a associação do endereço MAC para o endereço IPv4 é armazenada na memória do cache no PC. Quer saber mais sobre essa associação?
A partir do terminal de comando, inspira o comando `arp -a` e pressione enter. Note que a saída do comando exibirá as entradas que estão no cache no PC.
