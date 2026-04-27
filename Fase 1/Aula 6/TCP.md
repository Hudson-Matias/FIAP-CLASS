# Protocolo de Controle de Transmissão
O TCP fornece confiabilidade e controle de fluxo. Operações básicas de TCP:
- Número e rastreamento de segmentos de dados transmitidos para um host específico a partir de um aplicativo específico;
- Confirmar dados recebidos;
- Retransmitir quaisquer dados não reconhecidos após um certo período de tempo;
- Dados de sequência que podem chegar em ordem errada;
- Enviar dados a uma taxa eficiente que seja aceitável pelo receptor.
![[Pasted image 20260416173443.png]]

## Cabeçalho do TCP

TCP é um protocolo stateful, o que significa que ele controla o estado da sessão de comunicação,
O TCP registra quais informações foram enviadas e quais foram confirmadas.
![[Pasted image 20260416173547.png]]

## Aplicações que usam TCP

![[Pasted image 20260416174003.png]]

O TCP lida com todas as tarefas associadas à divisão do fluxo de dados em segmentos, fornecendo
confiabilidade, controlando o fluxo de dados e reordenando segmentos.