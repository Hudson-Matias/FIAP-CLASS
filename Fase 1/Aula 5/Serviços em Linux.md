Realize a instalação, abra o terminal e realize a atualização da lista de repositórios com o seguinte comando:
```sh
apt update
```

Após a conclusão do mesmo, instale o apache2 com o seguinte comando:
```sh
sudo apt install apache2
```

Assim que instalado, o serviço é inicializado e deverá estar ativo e em execução.
Confirme com o seguinte comando:
```sh
systemctl status apache2
```
![[Pasted image 20260414125936.png]]

Como pode ver o serviço não foi iniciado.
Desta forma, se for necessário utilizar o serviço, é preciso iniciá-lo da seguinte forma:
```sh
systemctl start apache2
```
![[Pasted image 20260414130051.png]]

Além deste teste, você pode realizar outro.
Para realizar outro teste, você precisa de um navegador e o endereço IP do seu computador para acessar a página inicial padrão do Apache. Se o serviço está funcionando corretamente, você poderá visualizar uma página como a mostrada na figura 3 - "Página do Servidor Apache":
![[Pasted image 20260414130242.png]]

Você pode pegar o endereço do IP do seu computador usando o seguinte comando do terminal:
```sh
ip a
hostname -i
```

Quando você obter o endereço IP do seu servidor, digite-o na barra de endereços do seu navegador, como mostrado na figura 10 - "Página do serviço Apache":
A página aberta indica que o serviço Apache está funcionando corretamente, além de mostrar algumas informações básicas sobre os arquivos utilizados pelo Apache e seus diretórios.

[[HTTP]]
[[DNS]]
[[DHCP]]
[[FTP]]

## Servidor de compartilhamento de arquivos
O compartilhamento de arquivos entre computadores é muito comum em redes corporativas, principalmente em casos em que um mesmo arquivo é utilizado por uma grande parte dos usuários da rede.
Isso se dá mantendo uma pasta compartilhada em um servidor na qual os arquivos utilizados pelos usuários da rede ficam armazenados. Assim, quando um usuário precisar de um desses arquivos, será necessário acessar a pasta.
Em sistemas Linux, o servidor responsável pelo compartilhamento de arquivos mais utilizado é o Samba, que permite o compartilhamento de arquivos entre computadores com sistemas operacionais GNU/Linux e Microsoft Windows.
Um dos grandes atrativos do Samba é a compatibilidade com uma gama de outros aplicativos, o que permite a adição de várias funcionalidades do servidor. Por exemplo, o Samba permite que outros tipos de autenticação sejam utilizados, pois pode acontecer de ele ser implementado em uma rede já existente, com um servidor de autenticação já operacional.
A utilização de um novo sistema de autenticação obrigará os administradores da rede a refazerem os cadastros de todos os usuários, o que seria extremamente trabalhoso e, no caso de uma grande rede, completamente inviável.
O Samba permite ainda que cada usuário tenha um diretório no servidor que, ao autenticar-se em um computador da rede passe a ser acessível como se fosse um diretório local do computador, que permite ao usuário guardar nele seus arquivos pessoais. Esse diretório ainda pode ser acessível pela rede, mediante autenticação de usuário e senha.
Ainda é possível definir uma cota para cada usuário, de modo que o usuário terá um espaço disponível predeterminado pelo administrador da rede, e devido à existência de vários níveis de usuários dentro de uma rede, usuários de diferentes níveis podem ter diferentes cotas de espaço em disco no servidor.