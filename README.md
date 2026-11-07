# TESTE-CAIXA-CINZA-COM-SUPABASE-E-POSTMAN
Testes de caixa cinza em API de autenticação utilizando Supabase e Postman.
---
#1. Introdução
---
Esta atividade consiste na realização de testes caixa cinza em uma API de autenticação utilizando o Supabase e o Postman. O Supabase foi utilizado para disponibilizar o serviço de autenticação por e-mail e senha, enquanto o Postman foi utilizado para enviar requisições HTTP e analisar as respostas da API.

Durante a atividade, foram realizados testes com diferentes cenários de autenticação, permitindo observar os códigos de status HTTP, as respostas em JSON e as mensagens de erro retornadas pelo sistema.

---
#2. Objetivo da Atividade
---

Esta atividade tem como objetivo fazer com que o aluno compreenda e aplique testes de caixa cinza em APIs de autenticação, utilizando ferramentas modernas de mercado para configuração, execução e validação de testes funcionais. Durante a atividade o aluno deverá:

- configurar um ambiente de autenticação utilizando Supabase;
- criar usuários para testes;
- compreender o funcionamento de requisições HTTP;
- utilizar o Postman para execução de testes;
- validar respostas de autenticação;
- documentar tecnicamente todo o processo realizado.

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
As evidências da configuração do Supabase estão disponíveis na pasta 'prints/supabase' deste repositório. Elas incluem capturas de tela da criação do projeto, do painel da plataforma, da autenticação habilitada, do usuário de teste, das credenciais da API e da identificação do aluno no ambiente.

---
#4. Configuração do Postman
---
**4.1 Como o Workspace foi criado:**
Foi criado um Workspace no Postman Desktop para organizar as requisições HTTP utilizadas na atividade. Esse espaço permite reunir e gerenciar as requisições relacionadas aos testes de autenticação da API do Supabase, facilitando a execução e a análise dos resultados.

**4.2 Como o Environment foi configurado:**
Foi criado um Environment no Postman para armazenar as variáveis utilizadas nas requisições de autenticação. Foram configuradas as variáveis base_url, api_key, email e password, correspondentes à URL do projeto Supabase, à chave da API e às credenciais do usuário de teste. Essa configuração facilita a reutilização dos dados durante a execução dos testes.

**4.3 Qual a finalidade das variáveis:**
As variáveis foram configuradas para facilitar a utilização dos dados nas requisições HTTP realizadas pelo Postman. Cada variável possui uma finalidade específica:

-base_url: armazena a URL do projeto Supabase.
-api_key: armazena a chave da API utilizada nas requisições.
-email: armazena o e-mail do usuário de teste.
-password: armazena a senha do usuário de teste.

O uso dessas variáveis permite reutilizar os dados nas requisições, facilitando a organização e a execução dos testes de autenticação.

**4.4 Como o Postman será utilizado nos testes:**
O Postman será utilizado para enviar requisições HTTP à API de autenticação do Supabase e analisar as respostas recebidas. Serão realizados testes com credenciais válidas e inválidas para verificar o comportamento da API em diferentes cenários. Os resultados serão avaliados por meio dos códigos de status HTTP, das respostas em JSON e das mensagens de erro retornadas, permitindo comparar os resultados obtidos com os resultados esperados.

**4.5 Evidências obrigatórias:**
As evidências da configuração do Postman estão disponíveis na pasta 'prints/postman' deste repositório. Elas incluem capturas de tela do Workspace criado, do Environment configurado, das variáveis utilizadas (base_url, api_key, email e password) e da organização das requisições no Postman.

---
#5. Configuração das Requisições

**5.1 Endpoint utilizado:**
/auth/v1/token?grant_type=password

Esse endpoint pertence à API de autenticação do Supabase e é utilizado para realizar o login de usuários por meio de e-mail e senha.

**5.2 Método HTTP utilizado:**
Foi utilizado o método POST para enviar as credenciais do usuário (e-mail e senha) à API de autenticação do Supabase, permitindo a realização do login.

**5.3 Headers utilizados:**
Foram configurados três headers na requisição HTTP:

-apikey: utiliza a variável {{api_key}}, que armazena a chave da API do projeto Supabase.
-Authorization: utiliza o formato Bearer {{api_key}} para enviar a chave no cabeçalho de autorização.
-Content-Type: utiliza o valor application/json, indicando que o corpo da requisição está no formato JSON.

**5.4 Body JSON utilizado:**
O corpo da requisição foi configurado no formato JSON, utilizando as variáveis {{email}} e {{password}}, que correspondem ao e-mail e à senha do usuário de teste armazenados no Environment do Postman.
{
  "email": "{{email}}",
  "password": "{{password}}"
}

**5.5 Finalidade da requisição:**
A requisição tem como finalidade realizar a autenticação de um usuário na API do Supabase por meio do e-mail e da senha. A partir da resposta recebida, é possível verificar se as credenciais são válidas, analisar o código de status HTTP e observar os dados retornados pela API.

---
#6. Execução dos Testes
---
#7. Registro dos Testes
---
#8. Resultados Obtidos
---
#9. Conclusão
---
