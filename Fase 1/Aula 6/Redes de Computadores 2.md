## Mensagens ICPM v4

-  O ICMP (Internet Control Message Protocol) fornece feedback sobre problemas relacionados ao processamento de pacotes IP sob determinadas condições.
- As mensagens ICMP comuns ao ICMPv4 incluem:
	- Acessibilidade do host;
	- Destino ou serviço inalcançável;
	- Tempo excedido.

## Acessibilidade do host

![[Pasted image 20260416165744.png]]

ICMP Echo Message pode ser usado para testar a capacidade de acesso de um host em uma rede IP.

## Destino ou Serviço Inacessível

- Uma mensagem de destino ICMP inacessível pode ser usada para notificar a origem de que um destino ou serviço está inacessível.
- A mensagem ICMP incluirá um código indicando por que o pacote não pode ser entregue.
Alguns códigos de Destino Inacessível para ICMPv4 são os seguintes:
 - 0 = rede inalcançável
 - 1 = host inalcançável
 - 2 = protocolo inalcançável
 - 3 = porta inalcançável

## Características de camada de rede

Fornece serviços para permitir que dispositivos finais troquem dados.
IP versão 4 (IPv4) e IP versão 6 (IPv6) são os principais protocolos de comunicação de camada de rede.
A camada de rede executa quatro operações básicas:
 - Endereça os dispositivos finais;
 - Encapsulamento;
 - Roteamento;
 - Desencapsulamento;

![[Pasted image 20260416170923.png]]
![[Pasted image 20260416170932.png]]

## Campos do Cabeçalho do Pacote IPv4

![[Pasted image 20260416171115.png]]

As características do cabeçalho de rede IPv4:
 - Contém vários campos de informação.
 - O diagrama é lido da esquerda para a direita, 4 bytes por linha.
 - Cabeçalho 20 bytes (comprimento 32 bits x 5 linhas).
 - Os dois campos mais importantes são origem e o destino.
## Fragmentação do datagrama IP

Tamanho teórico do datagrama IP é de 65.535 bytes.
MTU (Maximum Transmission Unit).
Quadros Ethernet podem transmitir 1500 bytes, mas em outros enlaces não mais do que 576 bytes.
![[Pasted image 20260416171812.png]]