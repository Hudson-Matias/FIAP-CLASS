[[Wireshark]]
## Protocolo de Comunicações
![[Pasted image 20260416152400.png]]

## Formatação e encapsulamento da mensagem

- Todas as comunicações são regidas por protocolos.
- Protocolos são as regras que as comunicações seguirão.
- Essas regras variam de acordo com o protocolo.
![[Pasted image 20260416152556.png]]
- Quando uma mensagem é enviada, ela deve usar um formato ou estrutura específica.
- Os formatos da mensagem dependem do tipo de mensagem e do  canal usado para entregá-la.
## Funções de protocolos de rede

![[Pasted image 20260416153012.png]]

- Os dispositivos usam protocolos acordados para se comunicar.
- Protocolos podem ter uma ou mais funções.
![[Pasted image 20260416153131.png]]

## Interação de protocolos

![[Pasted image 20260416153325.png]]

- As redes exigem o uso de vários protocolos.
- Cada protocolo tem sua própria função e formato.
## Conjunto de protocolos

![[Pasted image 20260416153502.png]]
![[Pasted image 20260416153517.png]]

## TCP/IP

![[Pasted image 20260416163056.png]]

## Processos de protocolos TCP/IP

Um servidor web encapsulando e enviando uma página da Web para um cliente.
Um cliente desencapsulando a página da web para o navegador da Web
![[Pasted image 20260416163336.png]]

## Modelos OSI e TCP/IP

![[Pasted image 20260416163507.png]]

## Segmentação de mensagens

![[Pasted image 20260416163708.png]]

- Segmentação é o processo de dividir mensagens em unidades menores.
- Multiplexação é o processo de tomar vários fluxos de dados segmentados e intercalá-los juntos.

## Sequenciamento

![[Pasted image 20260416163934.png]]

- Sequenciamento é o processo de numeração dos segmentos para que a mensagem possa ser remontada no destino.
- O TCP é responsável por sequenciar os segmentos individuais.
## Unidades de dados de protocolo

![[Pasted image 20260416164221.png]]

Encapsulamento é o processo em que os protocolos adicionam suas informações aos dados.
- Em cada etapa do processo, uma PDU possui um nome diferente para refletir suas novas funções.
- PDUs passando a pilha são as seguintes:
	- Dados (fluxo de dados);
	- Segmento;
	- Pacote;
	- Quadro;
	- Bits (fluxo de bits).

## Endereços

![[Pasted image 20260416164651.png]]

Tanto o link de dados quanto as camadas de rede usam endereçamento para entregar dados da origem ao destino.

