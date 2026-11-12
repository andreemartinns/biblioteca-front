# Biblioteca Comunitária: Front-end

Interface web para a **API de Gestão de Biblioteca Comunitária**. Permite cadastrar e consultar livros, autores, categorias, usuários e empréstimos.

## Links

- **Front-end (Vercel):** https://biblioteca-front-two.vercel.app
- **API (Render):** https://biblioteca-api-0ikp.onrender.com
- **Documentação da API (Swagger):** https://biblioteca-api-0ikp.onrender.com/swagger-docs.html

> A API fica hospedada no plano gratuito da Render e "dorme" quando ninguém a usa. No primeiro acesso, a conexão pode levar cerca de 1 minuto. O banco também começa vazio, então é preciso cadastrar os dados.

## Funcionalidades

- **Livros:** cadastro, listagem paginada e exclusão.
- **Empréstimos:** registro de empréstimo e registro de devolução, com status (Ativo, Devolvido, Atrasado).
- **Cadastros:** categorias, autores e usuários.
- **Chave de API:** geração direta pela interface, guardada no navegador.
- **Validação nos formulários:** o usuário recebe uma mensagem de erro clara antes de qualquer envio à API.

## Como usar

1. Abra o site e aguarde a mensagem **"Conectado à API."**
2. Clique em **Gerar chave** e informe um nome (3 a 100 caracteres). A chave é preenchida sozinha.
3. Na aba **Cadastros**, crie uma **categoria**, um **autor** e um **usuário**.
4. Na aba **Livros**, cadastre um livro.
5. Na aba **Empréstimos**, registre um empréstimo e depois a devolução.

As consultas (GET) funcionam sem chave. Criar, alterar e excluir exigem chave. A exclusão de livros exige chave de administrador.

## Regras de validação

| Campo | Regra |
|---|---|
| Título | 2 a 150 caracteres |
| ISBN | Somente números, 10 ou 13 dígitos |
| Ano | Somente números, 4 dígitos, entre 1000 e o próximo ano |
| Nome (categoria) | Somente letras, 2 a 60 caracteres |
| Nome (autor e usuário) | Somente letras, 3 a 100 caracteres |
| Nacionalidade | Somente letras, 2 a 60 caracteres |
| E-mail | Formato válido, até 120 caracteres |
| Telefone | Somente números, DDD + número (10 ou 11 dígitos) |
| Endereço | 5 a 150 caracteres |
| Nascimento | Não pode ser no futuro |
| Devolução prevista | Não pode ser no passado |

Essas regras também existem no back-end. O front apenas evita envios inválidos e melhora a experiência de uso.

## Tecnologias

- HTML, CSS e JavaScript puro, em um único arquivo (`index.html`), sem frameworks.
- Comunicação com a API via `fetch`, em JSON.
- Publicação na **Vercel**, com deploy automático a cada push.

## Como rodar localmente

1. Clone o repositório:
   `git clone https://github.com/andreemartinns/biblioteca-front.git`
2. Abra o arquivo `index.html` no navegador.

O front já aponta para a API publicada na Render, então não é preciso rodar mais nada.

## Autor

André Martins: https://github.com/andreemartinns