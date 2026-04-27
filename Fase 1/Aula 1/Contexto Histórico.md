Tríade da segurança da informação:

![[Pasted image 20260321164601.png]]


[[vetor de ataque]]

# Contexto Histórico
## 1950

Era falado da segurança DO computador e não da informação.
Era tempo de guerra então os dados tinham que ser [[encriptografado]]

## 1960

Havia o controle de senhas.
Era trabalhado o controle de senhas e de usuário.

## 1970

Já surgiu o [[Creeper]] o primeiro vírus de computador.
Onde fazia alteração de computador sem intervenção humana.

## 1980

[[Elk Cloner Vírus]] forçou a primeira criação de um anti-vírus.
Orange Book (1977).
Apesar de ser antigo, é muito cultuado por que ainda é usado como aprendizado.

## 1990

Temos controle de acesso, o gerenciamento de indentidade.
- IDS -> Ver possíveis intrusos no sistema;
- Policy Compliance -> auditoria, política
- Log Manager -> centralizava os logs.
- Firewall -> Era disponibilizado de forma free você tinha que configurar estava chegando essa tecnologia.
- Back Oriffice (Sir Dystic) -> primeiro grupo de hacktivistas (Divisor de águas) - Saindo da arte para o crime
- PCN / BIA / DRP
- Celulares
- Hack. Processo
- Ger. Segurança da Informação
- Eleição Informatizada (1996)

Aparece também os [[Phreakers]] os hackers especialistas em telefonias móveis.
Aparece também o cargo de gerente de segurança da informação.

## 2000
Começamos a falar sobre como as coisas já aumentaram cada vez mais.
Assim como o usuário no ano de '90 você criava o usuário e depois dava as permissões, nesta época o usuário já é criado com as permissões integradas nele.
- Gerenciamento de identidade
- Perfil de acesso
- Malwares ([[RAT]])
- NIST (Avaliability, integrity, confidentiality, accountability, assurance)
- SIEM -> verifica os logs e analisa para saber se há algum problema para o mesmo.
- BYOD - Trazer o seu celular para dentro da empresa, no caso a segurança dentro da empresa.
- DLP e Data Control -> O que saí no email, o que entra, o controle de dados.
- Auditoria
- Smartphones
- Bluetooth
- APT - Advanced Persistent Threat
- Fraude Digital
- ISO/IEC 17799:2000
- CISO/CSO/Security Officer
- Big Data (Base de redes sociais)

## 2010
O primeiros grandes vazamentos de dados que realmente começaram a acontecer.
- Vazamento de Dados (Snowden, Yahoo..)
- Ransomwares (WannaCry) -> Começo também de bitcoin para efetuar o pagamento
- SCADA (OT) - Ataques a redes de distribuição de energia, água, gás, eletricidade
- IOT - Aonde também pode ter um lado "dark side of the moon".
- Resposta à Incidentes (Red, Blue, Purple Team)
- Privacidade de Dados
- DPO
- Hacker Ético
- Bug Hunters
- Suply Chain Attack
- Cloud Security

## 2020 - Hoje
O que acontece no mundo atualmente:
- Trabalho Remoto
- IoMT / Healthcare Security - IOT voltado para dispositivos médicos
- Application Security
- Desenvolvimento Seguro
- DevSecOps
- Ataque à Terceiros - As empresas começam a se preocupar se aquele cara que está conectado na rede também se preocupa com a segurança do mesmo.
- API Attacks
- Resiliência
- NFT Hacking - Hacking de moedas
- Hardware Hacking - Muitos especialistas de hardware hacking como aparelhos que hackeiam
- Metaverso Security
Novos modelos de negócio:
- FaaS - Modelo de negócio de fraude - Se encontra em darkweb ou deepweb
- MaaS - Malware as a Service - Se encontra em grupos de facebook
- RaaS - Ransomware as a Service - pode-se se customizar também

----


# BYOD
Bring your own device (Traga seu Próprio Dispositivo)

![[Pasted image 20260328220248.png]]

![[Pasted image 20260328221155.png]]

## O que esperar deste curso?
A Cibersegurança é o carro-chefe do nosso curso, independente da trilha escolhida. Será abordado os tipos de ataques e técnicas de forma superficial, para detalhá-las com maior profundidade nos capítulos seguintes.
Será apresentado também os vetores e os motivos dos ataques, de forma a termos um panorama dos perigos cibernéticos.

### O que é a cibersegurança?

É a revolução tecnológica que estamos vivendo, impõe novas preocupações, acessos remotos e novas superfícies de ataques.
A cada dia novos cibercriminosos executam novos ataques.
Segundo Fabian Fischer (2016)* , estes ataques são como "tentativas deliberadas, por parte de pessoas não autorizadas, de obter acesso a esses sistemas, geralmente com o objetivo de "roubo", destruição ou prática de outros tipos de ações danosas ou ilegais".
Um outro ponto interessante é que em 2014, de acordo com o Dan Craigen disse:
> "Cibersegurança é um termo amplamente utilizado, com definições muito diversificadas, por vezes até subjetivas e pouco informativas".

#### Algumas definições interessantes
1. Cibersegurança implica a salvaguarda das redes de computadores e das informações nelas contidas contra intrusão, danos ou descontinuidades (apud LEWIS, 2006)
2. Cibersegurança envolve a redução do risco de ataques a softwares, computadores, e redes. Isso inclui ferramentas usadas para detectar invasões, contenção de vírus, bloqueio de acessos maliciosos, forçar autenticação, uso de criptografia e assim por diante (apud AMOROSO, 2006)
3. Cibersegurança é um conjunto de ferramentas, políticas, conceitos e salva guardas de segurança, diretrizes, abordagens de gerenciamento de riscos, ações, treinamentos, melhores práticas, garantias e tecnologias que podem ser usados para proteger o ambiente cibernético, a organização e os recursos do usuário (apud ITU, 2009)

## Cibersegurança e os negócios

*O começo de tudo*
Amadurecimento constante da área
  - Aumento budget (tem um time)
  - Visibilidade
Da área negativa e uma área de suporte ao negócio
Segregação da disciplina de privacidade

Quando falamos em cibersecurity começa a falar de negócio, começamos a falar sobre custos de [[violação de dados]].

## CERT BR
E como estamos falando de ataques e ameaças, não podemos deixar de mencionar o CERT.br.
O CERT é um grupo de Respostas a Incidentes de Segurança para a Internet Brasileira, como é conhecido, é mantido pelo NIC.br, do comitê Gestor da internet no Brasil, tendo sob sua responsabilidade o tratamento dos incidentes de segurança em computadores que envolvam redes conectadas à internet brasileira.
Atua também como ponto central para notificações de incidentes de segurança no Brasil, provendo a coordenação e o apoio no processo de resposta a incidentes e, quando necessário, colocando em contato as partes envolvidas.
link: https://stats.cert.br/incidentes/
O que vemos diante disso:
- [[Worm]]
- [[Web Deface]]
- [[Invasão]]
- [[DOS]]
- [[SCAN]]
- Fraude

Roteirinho de exploração de sites: [[Exploração de sites]]

[[Extra]]