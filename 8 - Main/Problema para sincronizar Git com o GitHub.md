14-08-2024 

Status: #inicial 

Tags: #git #github

# Não permite fazer o Git Push
Aparentemente de uns anos para cá não é possível mais fazer um `git push` colocando as credenciais normais para autenticar no repositório do GitHub. A forma de fazer atualmente é criando um Token para isso.

1 - É necessário criar um Token no GitHub para ser a nova forma de autenticação
	Settings >> Developer Settings >> Personal Acess Tokens >> Generate new Token(Classic)

2 - Por enquanto marcar todas as opções(necessário estudo sobre as outras opções)

 3- Com o Token gerado ir no repositório do computador e setar no repositório esse comando(`git remote ser-url origin https://<tokie>@github.com/<username>/<repositorio>.git`)
 
```git
git remote set-url origin https://<tokie>@github.com/dougstyle47/citacoes.git
```

4 - Tentar fazer o `git push origin master`
	O comando `git push origin main` por algum motivo não funciona

# Observações

- O problema que normalmente aparece quando se está tentando fazer o `push` e tenta colocar as credenciais é o seguinte
``` git
	Username for 'https://github.com': dougstyle47
	Password for 'https://dougstyle47@githu': 
	remote: Support for password authentication was removed on August 13, 2021.
	remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
	fatal: Authentication failed for 'https://github.com/dougstyle47/citacoes.git/'
```