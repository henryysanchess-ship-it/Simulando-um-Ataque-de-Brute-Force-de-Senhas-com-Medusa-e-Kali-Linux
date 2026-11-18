# Simulando um Ataque de Brute Force de Senhas com Medusa e Kali Linux
Implementar, documentar e compartilhar um projeto prático utilizando Kali Linux e a ferramenta Medusa, em conjunto com ambientes vulneráveis (por exemplo, Metasploitable 2 e DVWA), para simular cenários de ataque de força bruta e exercitar medidas de prevenção.
Etapa 1 – Identificação do endereço IP do alvo

Inicialmente, acessei o terminal do Metasploitable 2 e utilizei o comando:

ip a

O comando permite visualizar as interfaces de rede e identificar o endereço IP atribuído à máquina.

Endereço IP identificado:

192.168.56.101

Etapa 2 – Teste de conectividade

Com o endereço IP do Metasploitable identificado, retornei ao Kali Linux para verificar a comunicação entre as máquinas.

Utilizei:

ping -c 4 192.168.56.101

O teste retornou respostas do endereço de destino (64 bytes from), confirmando a conectividade entre o Kali Linux e o Metasploitable 2.

Etapa 3 – Reconhecimento e enumeração com Nmap

Com a comunicação estabelecida, utilizei o Nmap para realizar uma varredura no endereço IP do alvo.

sudo nmap -n -Pn -sV -F 192.168.56.101

O objetivo dessa etapa foi identificar:

Portas abertas.

Serviços disponíveis.

Versões dos serviços identificados.

Etapa 4 – Testes de autenticação com Medusa

Após o reconhecimento, utilizei o Medusa para realizar testes de autenticação no serviço FTP.

A ferramenta permite testar combinações de usuários e senhas utilizando listas de credenciais.

O objetivo foi identificar uma combinação válida de usuário e senha para o serviço analisado.

Ferramenta utilizada: Medusa.

Etapa 5 – Acesso ao serviço FTP

Após identificar credenciais válidas durante os testes de autenticação, utilizei o cliente FTP para estabelecer uma conexão com o Metasploitable 2.

Comando utilizado:

ftp 192.168.56.101

Em seguida, informei o usuário e a senha identificados anteriormente.
O acesso permitiu estabelecer uma sessão FTP com a máquina-alvo e verificar as funcionalidades disponíveis no serviço.
