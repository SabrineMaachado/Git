Primeiramente, devemos gerar um novo par de chaves usando o comando ssh-keygen:

ssh-keygen -t rsa -b 4096 -C "seu-email@seu-servidor.com"

O comando irá perguntar em qual arquivo você deseja salvar sua chave. Se você não tem nenhuma chave configurada, não tem problema usar o nome padrão (id_rsa). Em seguida, ele perguntará se você deseja usar uma senha que será perguntada toda vez que você fizer uma autenticação baseada nas suas chaves. Recomendo configurar uma senha se você compartilha seu computador com outras pessoas.

Enter passphrase (empty for no passphrase): [digite sua senha]
Enter same passphrase again: [digite sua senha novamente]
Finalmente, sua chave será salva na pasta ~/.ssh:

Your identification has been saved in /Users/raffa-ferreira/.ssh/id_rsa.
Your public key has been saved in /Users/raffa-ferreira/.ssh/id_rsa.pub.
The key fingerprint is:
01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db seu-email@seu-servidor.com
Feito isso, vamos colocar as chaves no GitHub. Logue em sua conta, vá para as configurações de Chaves SSH e clique no botão Add SSH key. Lá você terá um campo de título, opcional, e o campo da chave, no qual você deverá colar a chave pública (e não a privada) que acabamos de gerar. Para facilitar o processo, copie a chave pública para a área de transferência usando o comando pbcopy:

pbcopy < ~/.ssh/id_rsa.pub
Depois da sua chave ter sido configurada no GitHub, já é possível dar um git push normalmente.

Caso de erro use:

cat ~/.ssh/id_rsa.pub