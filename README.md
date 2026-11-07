# TESTE-CAIXA-CINZA-COM-SUPABASE-E-POSTMAN
Testes de caixa cinza em API de autenticação utilizando Supabase e Postman.
---
#1. Introdução
---
#2. Objetivo da Atividade
---
#3. Configuração do Supabase
---
**3.1 Como o projeto foi criado:**
Foi criado um novo projeto na plataforma Supabase para a realização da atividade de testes caixa cinza em uma API de autenticação. O projeto foi utilizado para disponibilizar o ambiente de autenticação, gerenciar o usuário de teste e obter as informações necessárias para realizar as requisições HTTP pelo Postman.

**3.2 Qual tipo de autenticação foi utilizada:**
Foi utilizada a autenticação por e-mail e senha, disponibilizada pelo Supabase Auth. Nesse método, o usuário informa seu endereço de e-mail e sua senha para realizar o login. A opção de confirmação de e-mail foi mantida ativa no ambiente durante a execução das requisições. Como o usuário de teste já estava confirmado antes da ativação dessa opção, foi possível realizar o login sem uma nova confirmação por e-mail. A API verifica as credenciais enviadas e retorna uma resposta indicando se a autenticação foi realizada com sucesso ou se ocorreu algum erro.

**3.3 Como o usuário foi criado:**
O usuário de teste foi criado pelo painel de gerenciamento do Supabase, na seção de autenticação de usuários. Durante a criação, foram informados um endereço de e-mail e uma senha para permitir a realização dos testes de login. Como a confirmação de e-mail está habilitada no ambiente, é necessário considerar o estado de confirmação do usuário para executar o teste de autenticação. Esse usuário foi utilizado como referência para o cenário de login válido no Postman.

**3.4 Qual o objetivo da configuração realizada:**
O objetivo da configuração do Supabase foi preparar um ambiente de autenticação para a execução de testes caixa cinza em uma API. A criação do usuário de teste e a configuração da autenticação por e-mail e senha permitiram realizar requisições pelo Postman, verificando o comportamento da API diante de credenciais válidas e inválidas, os códigos de status HTTP, as respostas JSON e as mensagens de erro retornadas.

**3.5 Evidências obrigatórias:**

As evidências da configuração do Supabase estão disponíveis na pasta 'prints/' deste repositório. Elas incluem capturas de tela da criação do projeto, do painel da plataforma, da autenticação habilitada, do usuário de teste, das credenciais da API e da identificação do aluno no ambiente.
---
#4. Configuração do Postman
---
#5. Configuração das Requisições
---
#6. Execução dos Testes
---
#7. Registro dos Testes
---
#8. Resultados Obtidos
---
#9. Conclusão
---
