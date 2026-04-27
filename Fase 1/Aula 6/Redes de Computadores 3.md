## Propósito de camada de transporte

A camada de transporte é:
 - Responsável pela comunicação lógica entre aplicativos executados em hosts diferentes.
 - O link entre a camada de aplicação e as camadas inferiores responsáveis pela transmissão da rede.
 ![[Pasted image 20260416172539.png]]

## Responsabilidades da camada de transporte

A camada de transporte tem as seguintes responsabilidades:
- Acompanhamento de conversas individuais;
- Segmentando dados e remontando segmentos;
- Adiciona informações de cabeçalho;
- Identificar, separar e gerenciar várias conversas;
- Usa segmentação e multiplexação pare permitir que diferentes conversas de comunicação sejam intercaladas na mesma rede.
![[Pasted image 20260416173033.png]]

Os protocolos de camada de transporte especificam como transferir mensagens entre hosts.
A camada de transporte inclui os protocolos TCP e UDP.
![[Pasted image 20260416173241.png]]

[[TCP]]
[[UDP]]

## Números de Porta

Os protocolos de camada de transporte TCP e UDP usam números de porta para gerenciar várias conversas simultâneas.
![[Pasted image 20260416174733.png]]

[[Sockets]]
