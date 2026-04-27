## Ler, Escrever e Executar
Os direitos de acesso a arquivos e diretórios são definidos em termos de acesso de leitura, acesso de gravação e acesso de execução. Se observarmos a saída do comando ls, podemos obter algumas dicas de como isso é implementado:
```sh
kali@kali:~$ echo > arq.txt
kali@kali:~$ ls -l arq.txt
-r–r–-- 1 kali kali 0 Feb 06 07:57 arq.txt
```

Os primeiros dez caracteres da lista são os atributos do arquivo. O primeiro desses caracteres (-) informa que é um tipo de arquivo. Observe na tabela “Tipos de arquivos”, os tipos de arquivo que você provavelmente visualizará. Vale lembrar que existem outros tipos menos comuns, mas não citados:
![[Pasted image 20260414102230.png]]

Para especificar quem é afetado, uma combinação dos caracteres “u”, “g”, “o” e “a” é usada, conforme descrito na Tabela “Notação simbólica”, apresentada a seguir:
![[Pasted image 20260414102355.png]]

Utilizando a notação simbólica para especificar a permissão, você pode alterar o modo de permissão para o arquivo arq.txt, para que seja apenas leitura para o grupo, para que os outros usuários também possam ler ao arquivo, use o seguinte exemplo:
```sh
kali@kali:~$ chmod g-w,o+r arq.txt
kali@kali:~$ ls -l arq.txt
-rw-r--r-- 1 kali kali 0 Feb 06 07:57 arq.txt
```

A pergunta deve ser: o que significa os sinais “+” e “-” na sintaxe do comando?
A operação pode ser um “+” indicando que uma permissão deve ser adicionada, um “-” indicando que uma permissão deve ser retirada ou um “=” indicando apenas que as permissões especificadas devem ser aplicadas e que todas as outras devem ser removidas. Se nenhum caractere for especificado, “todos” será assumido.
## Mudança de Identidades
O shell é um tanto único, na medida em que ele é uma interface de linha de comando poderosa para o operar o sistema operacional e, ao mesmo tempo, um intérprete de linguagem script.  
Para que você possa escrever o seu programa shell script, você deve entender e realizar as seguintes tarefas:
  
- Escreva um script. Os shell scripts são arquivos de texto comuns e, para escrevê-los, precisamos de um editor de texto. Os melhores editores de texto fornecerão realce de sintaxe, permitindo ter uma visão codificada por cores dos elementos do script. Editores como Vim, Nano e muitos outros são bons candidatos para escrever scripts.
- Torne o script executável. Você precisa definir as permissões do arquivo script para permitir sua execução.
- Coloque o script em algum lugar onde o shell possa encontrá-lo. O shell pesquisa automaticamente certos diretórios em busca de arquivos executáveis quando nenhum nome de caminho explícito é especificado. Para maior comodidade, colocaremos nossos scripts nestes diretórios.
  
Seguindo a tradição de programação, criaremos um programa "hello world" para demonstrar um script extremamente simples. natão, você deve iniciar com utilização de um editor de texto:
```sh
kali@kali:~$ vim script.sh
```

Note que o editor de texto Vim foi iniciado. Para que você possa inserir conteúdo no arquivo, pressione a tecla "(I)nsert" para alterar para o modo de inserção do editor. Em seguida, digite este conteúdo no script:
```Vim
#!/bin/bash
#Meu script
echo “Hello World”
```

  
Assim que terminar de inserir o conteúdo, você precisará salvar o que foi feito. Sendo assim, pressione a tecla "Esc", para sair do modo inserção e volte para o modo "comando" do editor. Agora, pressione ":". Note que o cursor está no final da tela do editor. Quando isso acontecer, digite as letras "wq" e pressione a tecla "Enter". Esse procedimento, salva o conteúdo do arquivo "w" e sai do editor "q".
  
Vamos comentar as linhas do script:
  
A primeira linha do nosso script parece ser um comentário, já que começa com #, mas não é isso. O "#!" é uma sequência de caracteres, que na verdade representa uma construção especial chamada "shebang". O shebang é usado para informar ao sistema o nome do interpretador que deve ser usado para executar o script. Todo shell script deve incluir isso como sua primeira linha, combinado?! A segunda linha também tem "#". E agora?!
  
A segunda linha é, de fato, um comentário. Muitos arquivos de configuração ou shell scripts devem conter comentários para facilitar sua identificação. Vale comentar que tudo a partir do símbolo "#" em diante na linha é ignorado, ou seja, é comentário. A terceira e última linha do nosso script, utiliza um comando
  
A próxima tarefa que temos que fazer é tornar nosso script executável. Isso é feito facilmente usando chmod:
```sh
kali@kali:~$ chmod 755 script.sh
kali@kali:~$ ls -l script.sh 
-rwxr-xr-x 1 kali kali 44 Fev 06 15:00 script.sh
```

Existem duas configurações de permissão comuns para scripts: o valor 755 para scripts que todos podem executar e 700 para scripts que apenas o proprietário pode executar.
Com as permissões definidas, agora podemos executar nosso script:
```sh
kali@kali:~$ ./script.sh
Hello World
```

Para que o script seja executado, devemos preceder o nome do script com um caminho explícito. O “./” informa ao interpretador de comando qual é o caminho atual do arquivo de script.

## Melhores Localizações para Scripts
  
O diretório **~/bin** é um bom lugar para colocar scripts destinados ao uso pessoal. Se escrevemos um script em que todos em um sistema têm permissão para usar, o local tradicional seria **/usr/local/bin** e os scripts destinados ao administrador do sistema seriam localizados frequentemente em **/usr/local/sbin**.
Na maioria dos casos, os softwares produzidos localmente, como scripts ou programas compilados, devem ser colocados no diretório **/usr/local** e não em **/bin** ou **/usr/bin**. Esses diretórios são especificados pelo Linux Filesystem Hierarchy Standard para conter apenas arquivos fornecidos e mantidos pela distribuição Linux.  
Você pode configurar seu próprio diretório e manter seus scripts nele, porém, antes de começar a escrever seu próximo script, é recomendável designar um diretório para tal função. É recomendado que para scripts pessoais você faça isso em **~/bin**, ou seja, em um diretório chamado bin a partir do diretório de trabalho do seu usuário.
Para criar esta pasta, digite:
```sh
kali@kali:~$ mkdir ~/bin
```

Para fazer com que seus scripts possam ser executados de qualquer localização do sistema, você deve editar o arquivo **/etc/profile** e realizar as seguintes alterações:
```sh
kali@kali:~$ sudo vim /etc/profile
```

Digite a senha e, logo após visualizar o conteúdo do arquivo, navegue até o final do arquivo. Lembre-se de pressionar a tecla "(I)nsert" e adicione as linhas a seguir ao final do arquivo:
```VIM
PATH=$PATH:$HOME/bin
export PATH
```

Observe que a figura "Edição do arquivo profile", apresenta a alteração realizada anteriormente:
![[Pasted image 20260414104129.png]]

Assim que terminar de inserir o conteúdo, você deve salvá-lo e sair do editor. Para isso, lembre-se de utilizar a seguinte sequência de teclas: "ESC" e ":wq" para fazer com que as alterações entrem em vigor e executem a seguinte linha de comando:
```sh
kali@kali:~$ source /etc/profile
```

Agora você pode mover seu arquivo de script para o diretório ~/**bin** e sempre que necessário executá-lo.

## Criando mais Scripts
  
Você pode utilizar variáveis nos seus scripts com o propósito de armazenar um valor para ser utilizado posteriormente. A linguagem shell não é “tipada”, ou seja, ela permite armazenar qualquer tipo de valor em uma variável, desde strings a números.
Para declará-las basta seguir a sintaxe:
```VIM
nome_da_variavel=valor
```

Onde **nome_da_variavel** é uma sequência de caracteres que deve começar por qualquer letra maiúscula ou minúscula, e valor será o valor armazenado nesta variável.
Note que, agora, estamos iniciando o editor com o nome do arquivo que será salvo no diretório que criamos anteriormente. Para começar um novo script chamado s2.sh, digite:
```sh
kali@kali:~$ vim ~/bin/s2.sh
```

Inspira o conteúdo no arquivo e, quando terminar, você deve salvar o arquivo e sair. São os mesmo procedimentos utilizados anteriormente.
```VIM
#!/bin/bash
# Utilizando variáveis
nome="Aluno"
instituicao="Fiap"
cidade="São Paulo"
echo "Eu sou": $nome"
echo "A instituição que estudo é a: $instituicao"
echo "Localizada na cidade de: $cidade"
```

> IMPORTANTE:
> Esse procedimento é algo que deve ser realizado frequentemente!

A próxima tarefa é tornar nosso script executável. Isso é feito facilmente usando chmod:
```sh
kali@kali:~$ chmod 755 ~/bin/s2.sh
```

Agora, para executá-lo, você simplesmente pode digitar o nome do arquivo script.
```sh
kali@kali:~$ s2.sh
```

## Capturando a Entrada de Dados do Usuário

Pode ser que o seu script precise interagir com o usuário, pedindo para ele fornecer algum dado de entrada para processamento. Neste caso, é necessário "ler" o conteúdo que o usuário digitou. Para isso use a seguinte sintaxe.
```VIM
read nome_da_variavel
```

A partir de agora, você irá observar que serão apresentados apenas os nomes dos scripts e seus respectivos conteúdos. Você deve realizar os mesmos procedimentos iniciais, feitos no exemplo anterior. Combinado?!
```sh
kali@kali:~$ vim ~/bin/s3.sh
```

```VIM
#!/bin/bash
echo "Digite seu nome"
read nome;
echo "Seu nome é $nome!"
```

## Comandos de Seleção ou de Tomada de Decisão

Algumas vezes precisamos seguir um determinado fluxo de execução baseado em uma decisão tomada pelo usuário ou pelo próprio sistema utilizado. O comando que permite realizar esse procedimento é o condicional "if", que tem a seguinte sintaxe:
```VIM
if [ CONDICAO ]; 
then
  AÇÃO
fi
```

Vamos criar mais um arquivo.
```sh
kali@kali:~$ vim ~/bin/s4.sh
```

No exemplo a seguir, a condição proposta verifica se o número 5 é menor do que o número 10. Assim que você o executar, descobrirá se realmente essa condição é verdadeira ou não. O que acha?
```VIM
#!/bin/bash
if [ 5 -lt 10 ]
then
echo "É menor"
fi
```

Neste exemplo, a condição proposta verifica qual dos dois números que você digitou é o maior.
```VIM
#!/bin/bash
echo -n "Digite o primeiro número: "
read numero1;
echo -n "Digite o segundo número: " 
read numero2;

if [ $numero1 -gt $numero2 ]
then
  echo "O primeiro número é  maior."
else
  echo "O segundo número é maior"
fi
```

Se você quiser elaborar outros scripts, observe que existem outros operadores que podem ser utilizados para comparar números. Observe atentamente quais são na tabela "Operadores aritméticos":
![[Pasted image 20260414123530.png]]

Existe uma maneira de conhecer as propriedades do arquivo utilizando outros operadores, que são apresentados na tabela "Operadores para Arquivos":
![[Pasted image 20260414123624.png]]

Com as condições aninhadas, você também pode colocar instruções "if" inteiras dentro de outras, criando assim o que é chamado de "if aninhado". O exemplo apresentado a seguir utiliza como entrada fornecida pelo usuário um nome para um arquivo. A partir dessa entrada, o script verifica se o arquivo existe ou não.
```sh
kali@kali:~$ vim ~/bin/s7.sh
```

```VIM
#!/bin/bash
echo "Insira qual arquivo você deseja criar"
read arquivo;
if [ -f $arquivo ]
then
echo "O arquivo já existe"
else
  touch $arquivo
  if [ -w $arquivo ]
  then
    echo "O arquivo foi criado e pode se modificado."
  else
    echo "O arquivo foi criado e não pode se modificado."
  fi
fi
```

## Controle de Fluxo

Continuando nosso aprendizado, examinaremos um conceito de programação denominado looping, que pode ser usado para repetir partes dos programas. O shell fornece comandos compostos para loop. Vamos aos exemplo?
```sh
kali@kali:~$ vim ~/bin/for.sh
```

O script a seguir exibe a mensagem "Looping .. número x".
```VIM
#!/bin/bash
#for: exibir uma série de números
for i in 1 2 3 4 5
do
	echo "Looping ... numero $i"
done
```

Note que a saída da execução do script apresentou a mensagem cinco vezes, alterando apenas o valor da variável, "i", que foi incrementada toda vez que o loop se iniciava.
```sh
kali@kali:~$ for.sh
Looping ... numero 1
Looping ... numero 2
Looping ... numero 3
Looping ... numero 4
Looping ... numero 5
```

O código utilizado nesse script não ficou tão elegante, com isso, imagine se você quisesse criar uma repetição por 100 vezes. Seria cansativo ter que digitar todos esses números. Então, vamos melhorar no próximo script:
```sh
kali@kali:~$ vim ~/bin/for-melhor.sh
```
```VIM
#!/bin/bash
#for: exibir uma série de números
for i in {1..5}
do
  echo "O valor da variável i é: $i"
done
```

Note a elegância na linha do "for", na qual "{1..5}" indica que o loop será repetido de 1 a 5.
O comando **while**, pode expressar uma ideia semelhante do comando **for** apresentado anteriormente. Vamos utilizá-lo e reproduzir uma saída semelhante a do exemplo anterior, ou seja, exibir números em ordem sequencial. Note que utilizamos uma variável chamada "contador para armazenar os valores. Basicamente o código funciona da seguinte maneira: enquanto o valor da variável "contador" for menor ou igual a cinco, exiba seu valor.
```sh
kali@kali:~$ vim ~/bin/while.sh
```

O conteúdo do script pode ser construído da seguinte maneira:
```VIM
#!/bin/bash
# while: exibir uma série de números
contador=1
while [[ $contador -le 5 ]]; do
	echo $contador
	contador=$((contador + 1))
done
```

Vamos a outro exemplo:
```sh
kali@kali:~$ vim ~/bin/while-bye.sh
```

Neste exemplo, o código do script aguarda o usuário digitar um valor para comparar com o valor da variável declarada. Enquanto esse valor digitado for diferente, o script fica em funcionamento, ou seja, em uma espécie de looping.
```VIM
#!/bin/bash
# while: comparando um valor digitado
valor=hello
while [ "$valor" != "bye" ]
do
  echo "Digite uma palavra ou bye para sair"
  read valor
  echo "Você digitou: $valor"
done
```

Agora construindo alguns menus simples e utilizando uma lógica para atuar na seleção das opções disponíveis. Este tipo de construção aparece com frequência em programas, fornecendo um mecanismo de controle de fluxo para decisões de várias opções.
O comando bash, composto de múltipla escolha é denominado "case" e possui a seguinte sintaxe:
```VIM
case palavra in
padrão
esac
```

Vamos utilizar um exemplo muito simples. Quem gosta de frutas vai adorá-lo.
```sh
kali@kali:~$ vim ~/bin/case-fruta.sh
```

Utilize o código a seguir:
```VIM
#!/bin/bash
#case: escolha de uma opção
fruta="kiwi"
case "$fruta" in
   "maça") echo "A maçã está saborosa." 
   ;;
   "banana") echo "Banana engorda e faz crescer." 
   ;;
   "kiwi") echo "Fruta do Huck." 
   ;;
esac
```

Note que a resposta "foi "Fruta do "uck", uma vez que a variável valor está definida com o valor "kiwi".
