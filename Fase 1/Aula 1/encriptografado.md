## O que é criptografia

**Criptografia** é a área da segurança da informação que reúne princípios, métodos e algoritmos para proteger dados, escondendo seu conteúdo, evitando uso não autorizado e também ajudando a detectar alterações indevidas. Em outras palavras, ela não serve só para “embaralhar” dados: também pode apoiar **confidencialidade, integridade, autenticação e não repúdio**. ([NIST CSRC](https://csrc.nist.gov/glossary/term/cryptography?utm_source=chatgpt.com "cryptography - Glossary | CSRC"))

## O que é encriptação (ou “encriptografia digital”)

**Encriptação** é o **processo específico** de transformar um dado legível, chamado **plaintext** (texto claro), em um formato ilegível, chamado **ciphertext** (texto cifrado), usando um algoritmo criptográfico e uma chave. Depois, quem possui a chave correta pode fazer a **desencriptação/decriptação**, recuperando o conteúdo original. Em resumo: **criptografia é o campo mais amplo; encriptação é uma das técnicas/processos dentro dele**. ([NIST CSRC](https://csrc.nist.gov/glossary/term/encryption?utm_source=chatgpt.com "encryption - Glossary | CSRC"))

## “Criptografia” e “encriptação” são a mesma coisa?

No uso comum, muita gente trata como sinônimos, mas tecnicamente há uma diferença útil:

- **Criptografia** = a disciplina/área de estudo e aplicação.
    
- **Encriptação** = a operação de cifrar dados.
    
- **Desencriptação/decriptação** = a operação inversa.
    

Em português, você também vai ver os termos **criptografar**, **encriptar** e até “encriptografia”. O termo mais técnico e mais estável em segurança costuma ser **criptografia** para a área e **encriptação/criptografar** para o ato de cifrar. Fontes em português da Microsoft usam “encriptação” para o processo, enquanto dicionários registram “encriptar” e “criptografar” como formas válidas no uso corrente. ([Microsoft Learn](https://learn.microsoft.com/pt-br/purview/encryption?utm_source=chatgpt.com "Criptografia no Microsoft 365"))

## Como a encriptação funciona na prática

A lógica básica é:

**texto claro + algoritmo + chave = texto cifrado**

A **chave criptográfica** é um valor que controla a operação de encriptação e desencriptação. Sem a chave correta, o dado pode até ser interceptado, mas permanece ilegível. ([Cloudflare](https://www.cloudflare.com/learning/ssl/what-is-a-cryptographic-key/?utm_source=chatgpt.com "What is a cryptographic key? | Keys and SSL encryption"))

Exemplo simples:

- Mensagem original: `Minha senha é 123`
    
- Após encriptação: algo como `8F2A9C...`
    
- Com a chave correta, o sistema reconstrói a mensagem original.
    

Esse “resultado embaralhado” não é aleatório puro; ele é gerado por um algoritmo matemático controlado por chave. ([NIST CSRC](https://csrc.nist.gov/glossary/term/encryption?utm_source=chatgpt.com "encryption - Glossary | CSRC"))

## Principais objetivos da criptografia

A criptografia moderna costuma atender quatro objetivos centrais:

**1. Confidencialidade**  
Garantir que só pessoas ou sistemas autorizados consigam ler os dados. A encriptação é a técnica mais ligada a esse objetivo. ([NIST CSRC](https://csrc.nist.gov/glossary/term/encryption?utm_source=chatgpt.com "encryption - Glossary | CSRC"))

**2. Integridade**  
Permitir verificar se o conteúdo foi alterado. Isso costuma envolver funções hash e assinaturas digitais. ([NIST CSRC](https://csrc.nist.gov/glossary/term/hash_function?utm_source=chatgpt.com "hash function - Glossary | CSRC"))

**3. Autenticidade**  
Confirmar que a mensagem ou arquivo realmente veio de quem afirma ter enviado. ([NIST CSRC](https://csrc.nist.gov/glossary/term/digital_signature?utm_source=chatgpt.com "digital signature - Glossary | CSRC"))

**4. Não repúdio**  
Dificultar que o autor negue depois que assinou digitalmente um conteúdo. ([NIST CSRC](https://csrc.nist.gov/glossary/term/digital_signature?utm_source=chatgpt.com "digital signature - Glossary | CSRC"))

## Tipos principais de criptografia

### 1) Criptografia simétrica

Na **criptografia simétrica**, a mesma chave secreta é usada para encriptar e desencriptar. Ela é muito eficiente e rápida, por isso é bastante usada para proteger grandes volumes de dados. ([NIST CSRC](https://csrc.nist.gov/glossary/term/symmetric_cryptography?utm_source=chatgpt.com "Symmetric Cryptography - Glossary - CSRC - NIST"))

Exemplos de uso:

- criptografia de arquivos no disco
    
- bancos de dados
    
- backups
    
- parte da proteção de tráfego em conexões seguras
    

Exemplo de algoritmo:

- **AES** (Advanced Encryption Standard), padrão amplamente reconhecido pelo NIST para proteger dados eletrônicos. O AES possui versões com chaves de **128, 192 e 256 bits**. ([NIST](https://www.nist.gov/publications/advanced-encryption-standard-aes?utm_source=chatgpt.com "Advanced Encryption Standard (AES) | NIST"))
    

### 2) Criptografia assimétrica

Na **criptografia assimétrica** existem **duas chaves relacionadas matematicamente**:

- uma **chave pública**, que pode ser divulgada
    
- uma **chave privada**, que deve permanecer secreta
    

O que é encriptado com uma chave só pode ser decriptado com a outra correspondente, ou usado para assinatura/verificação digital. Esse modelo é a base de várias tecnologias de Internet, como certificados e HTTPS/TLS. ([NIST CSRC](https://csrc.nist.gov/glossary/term/asymmetric_cryptography?utm_source=chatgpt.com "asymmetric cryptography - Glossary | CSRC"))

Exemplos de uso:

- troca segura de chaves
    
- certificados digitais
    
- assinatura digital
    
- autenticação de sites e serviços
    

## Exemplos reais do dia a dia

### HTTPS

Quando você acessa um site com **HTTPS**, a comunicação usa **TLS**, que protege os dados em trânsito, ajuda a autenticar o site e reduz risco de interceptação e adulteração da comunicação. Hoje, HTTPS protegido por TLS é prática padrão na web. ([Cloudflare](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/?utm_source=chatgpt.com "What is Transport Layer Security (TLS)?"))

### Apps de mensagens

Aplicativos de mensagem usam criptografia para que terceiros não consigam ler o conteúdo em trânsito. Em sistemas de ponta a ponta, a ideia é que apenas remetente e destinatário tenham acesso ao conteúdo legível. ([NIST CSRC](https://csrc.nist.gov/glossary/term/encryption?utm_source=chatgpt.com "encryption - Glossary | CSRC"))

### Discos e arquivos

Sistemas operacionais e serviços em nuvem usam criptografia para proteger dados “em repouso”, isto é, armazenados em disco. Isso reduz o impacto caso um dispositivo seja perdido, roubado ou acessado sem autorização. ([Microsoft Learn](https://learn.microsoft.com/pt-br/windows/security/operating-system-security/data-protection/personal-data-encryption/?utm_source=chatgpt.com "Descrição Geral da Encriptação de Dados Pessoais"))

### E-mail corporativo

Plataformas como Microsoft 365 usam encriptação para transformar texto claro em cifratexto, permitindo que apenas usuários autorizados façam a desencriptação. ([Microsoft Learn](https://learn.microsoft.com/pt-br/purview/encryption?utm_source=chatgpt.com "Criptografia no Microsoft 365"))

## O que são chaves criptográficas

Uma **chave criptográfica** é o valor usado para controlar operações como encriptação, decriptação, geração e verificação de assinatura digital. Sem o gerenciamento correto das chaves, até um algoritmo forte pode ser mal aproveitado. Em segurança real, proteger a chave é tão importante quanto escolher um bom algoritmo. ([NIST CSRC](https://csrc.nist.gov/glossary/term/key?utm_source=chatgpt.com "key - Glossary | CSRC"))

## Criptografia não é a mesma coisa que hash

Isso confunde muita gente.

**Encriptação** é **reversível** com a chave correta.  
**Hash** não foi feito para “voltar” ao original; ele gera um resumo fixo do conteúdo, útil para verificar integridade. O NIST define função hash como um algoritmo que calcula um valor numérico representativo do arquivo ou mensagem e dependente de todo o conteúdo. ([NIST CSRC](https://csrc.nist.gov/glossary/term/hash_function?utm_source=chatgpt.com "hash function - Glossary | CSRC"))

Exemplo:

- arquivo original → gera hash
    
- se o arquivo mudar um único caractere → o hash muda
    

Por isso, **senha bem armazenada normalmente deve ser protegida com hash adequado**, e não simplesmente “criptografada” como um arquivo comum. Hash e encriptação têm propósitos diferentes. ([NIST CSRC](https://csrc.nist.gov/glossary/term/hash_function?utm_source=chatgpt.com "hash function - Glossary | CSRC"))

## Criptografia também não é o mesmo que codificação

**Codificação/encoding** serve para representar dados em outro formato, geralmente para compatibilidade ou transporte. **Não é, por si só, uma técnica de segurança.** Já a encriptação existe para manter sigilo, usando algoritmo criptográfico e chave. ([Stack Overflow](https://stackoverflow.com/questions/4657416/difference-between-encoding-and-encryption?utm_source=chatgpt.com "Difference between encoding and encryption"))

Exemplo clássico:

- **Base64** = codificação
    
- **AES** = criptografia
    

Base64 pode ser revertido facilmente por qualquer pessoa; AES exige a chave correta. ([Stack Overflow](https://stackoverflow.com/questions/4657416/difference-between-encoding-and-encryption?utm_source=chatgpt.com "Difference between encoding and encryption"))

## Assinatura digital: relacionada, mas diferente

**Assinatura digital** não serve para ocultar o conteúdo. Ela serve para comprovar **autenticidade**, **integridade** e **não repúdio**. Em geral, usa chave privada para assinar e chave pública para verificar. Portanto:

- **encriptação** protege sigilo
    
- **assinatura digital** prova origem e integridade
    

Muitos sistemas usam as duas juntas. ([NIST CSRC](https://csrc.nist.gov/glossary/term/digital_signature?utm_source=chatgpt.com "digital signature - Glossary | CSRC"))

## Exemplos de algoritmos conhecidos

Alguns exemplos importantes:

- **AES**: algoritmo simétrico muito usado para proteção de dados eletrônicos. ([NIST](https://www.nist.gov/publications/advanced-encryption-standard-aes?utm_source=chatgpt.com "Advanced Encryption Standard (AES) | NIST"))
    
- **RSA / ECC**: famílias muito usadas em criptografia de chave pública, certificados e assinaturas. O NIST trata RSA e curvas elípticas em suas orientações de gerenciamento e transição. ([NIST Publicações Técnicas](https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-57pt3r1.pdf?utm_source=chatgpt.com "Part 3: Application-Specific Key Management Guidance"))
    
- **SHA-2 / SHA-3**: famílias de hash aprovadas pelo NIST para gerar resumos criptográficos. ([NIST CSRC](https://csrc.nist.gov/projects/hash-functions?utm_source=chatgpt.com "Hash Functions | CSRC"))
    

## Limitações: criptografia não faz milagres

Mesmo sendo essencial, criptografia **não resolve tudo sozinha**. Ela pode falhar na prática quando:

- a chave é roubada ou vazada
    
- a senha da chave é fraca
    
- o algoritmo é bom, mas a implementação é ruim
    
- os dados são protegidos em trânsito, mas expostos no dispositivo já desbloqueado
    
- há erro humano ou configuração inadequada
    

O próprio NIST mantém guias de transição porque algoritmos e tamanhos de chave precisam ser atualizados ao longo do tempo para acompanhar novos riscos. ([NIST Publicações Técnicas](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-131Ar2.pdf?utm_source=chatgpt.com "Transitioning the Use of Cryptographic Algorithms and Key ..."))

## Tendência atual: criptografia pós-quântica

Uma mudança importante dos últimos anos é a preparação para a era da **computação quântica**. Em agosto de 2024, o NIST publicou seus primeiros padrões principais de **criptografia pós-quântica**, voltados a mecanismos de estabelecimento de chaves e assinaturas digitais, justamente porque certos algoritmos de chave pública usados hoje poderão se tornar vulneráveis no futuro. ([NIST](https://www.nist.gov/news-events/news/2024/08/nist-releases-first-3-finalized-post-quantum-encryption-standards?utm_source=chatgpt.com "NIST Releases First 3 Finalized Post-Quantum Encryption ..."))

## Definição resumida para usar em trabalho ou apresentação

Você pode usar assim:

**Criptografia** é o conjunto de técnicas e algoritmos usados para proteger informações, garantindo sigilo, integridade, autenticidade e não repúdio.  
**Encriptação digital** é o processo de transformar dados legíveis em texto cifrado por meio de algoritmos e chaves criptográficas, permitindo que apenas usuários autorizados recuperem o conteúdo original. ([NIST CSRC](https://csrc.nist.gov/glossary/term/cryptography?utm_source=chatgpt.com "cryptography - Glossary | CSRC"))

## Exemplo final, bem simples

Imagine um app bancário:

1. Você digita sua senha e dados.
    
2. O app envia essas informações via **HTTPS/TLS**. ([Cloudflare](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/?utm_source=chatgpt.com "What is Transport Layer Security (TLS)?"))
    
3. Os dados trafegam encriptados, então um invasor que intercepte o tráfego não lê facilmente o conteúdo. ([Cloudflare](https://www.cloudflare.com/learning/ssl/how-does-ssl-work/?utm_source=chatgpt.com "How does SSL work? | SSL certificates and TLS"))
    
4. No servidor, senhas idealmente não são guardadas em texto puro; usam mecanismos apropriados de proteção e verificação, tipicamente com hash para integridade/verificação e não simples codificação. ([NIST CSRC](https://csrc.nist.gov/glossary/term/hash_function?utm_source=chatgpt.com "hash function - Glossary | CSRC"))
    
5. Arquivos ou bancos podem ainda ficar criptografados em repouso no disco. ([Microsoft Learn](https://learn.microsoft.com/pt-br/azure/security/fundamentals/encryption-overview?utm_source=chatgpt.com "Visão geral da criptografia do Azure"))
    

Se quiser, eu posso transformar isso agora em um **resumo para seminário**, **texto acadêmico ABNT** ou **mapa mental**.