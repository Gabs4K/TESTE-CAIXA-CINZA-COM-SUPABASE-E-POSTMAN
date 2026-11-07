# TESTE-CAIXA-CINZA-COM-SUPABASE-E-POSTMAN
Testes de caixa cinza em API de autenticação utilizando Supabase e Postman.
---
# 1. Introdução
---
Esta atividade consiste na realização de testes caixa cinza em uma API de autenticação utilizando o Supabase e o Postman. O Supabase foi utilizado para disponibilizar o serviço de autenticação por e-mail e senha, enquanto o Postman foi utilizado para enviar requisições HTTP e analisar as respostas da API.

Durante a atividade, foram realizados testes com diferentes cenários de autenticação, permitindo observar os códigos de status HTTP, as respostas em JSON e as mensagens de erro retornadas pelo sistema.

---
# 2. Objetivo da Atividade
---

Esta atividade tem como objetivo fazer com que o aluno compreenda e aplique testes de caixa cinza em APIs de autenticação, utilizando ferramentas modernas de mercado para configuração, execução e validação de testes funcionais. Durante a atividade o aluno deverá:

- configurar um ambiente de autenticação utilizando Supabase;
- criar usuários para testes;
- compreender o funcionamento de requisições HTTP;
- utilizar o Postman para execução de testes;
- validar respostas de autenticação;
- documentar tecnicamente todo o processo realizado.

---
# 3. Configuração do Supabase
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
As evidências da configuração do Supabase estão disponíveis na pasta 'prints/supabase' deste repositório.

---
# 4. Configuração do Postman
---
**4.1 Como o Workspace foi criado:**
Foi criado um Workspace no Postman Desktop para organizar as requisições HTTP utilizadas na atividade. Esse espaço permite reunir e gerenciar as requisições relacionadas aos testes de autenticação da API do Supabase, facilitando a execução e a análise dos resultados.

**4.2 Como o Environment foi configurado:**
Foi criado um Environment no Postman para armazenar as variáveis utilizadas nas requisições de autenticação. Foram configuradas as variáveis base_url, api_key, email e password, correspondentes à URL do projeto Supabase, à chave da API e às credenciais do usuário de teste. Essa configuração facilita a reutilização dos dados durante a execução dos testes.

**4.3 Qual a finalidade das variáveis:**
As variáveis foram configuradas para facilitar a utilização dos dados nas requisições HTTP realizadas pelo Postman. Cada variável possui uma finalidade específica:

- base_url: armazena a URL do projeto Supabase.
- api_key: armazena a chave da API utilizada nas requisições.
- email: armazena o e-mail do usuário de teste.
- password: armazena a senha do usuário de teste.

O uso dessas variáveis permite reutilizar os dados nas requisições, facilitando a organização e a execução dos testes de autenticação.

**4.4 Como o Postman será utilizado nos testes:**
O Postman será utilizado para enviar requisições HTTP à API de autenticação do Supabase e analisar as respostas recebidas. Serão realizados testes com credenciais válidas e inválidas para verificar o comportamento da API em diferentes cenários. Os resultados serão avaliados por meio dos códigos de status HTTP, das respostas em JSON e das mensagens de erro retornadas, permitindo comparar os resultados obtidos com os resultados esperados.

**4.5 Evidências obrigatórias:**
As evidências da configuração do Postman estão disponíveis na pasta 'prints/postman' deste repositório. 

---
# 5. Configuração das Requisições
---

**5.1 Endpoint utilizado:**
/auth/v1/token?grant_type=password

Esse endpoint pertence à API de autenticação do Supabase e é utilizado para realizar o login de usuários por meio de e-mail e senha.

**5.2 Método HTTP utilizado:**
Foi utilizado o método POST para enviar as credenciais do usuário (e-mail e senha) à API de autenticação do Supabase, permitindo a realização do login.

**5.3 Headers utilizados:**
Foram configurados três headers na requisição HTTP:

| Header | Valor |
|---|---|
| `apikey` | `{{api_key}}` |
| `Authorization` | `Bearer {{api_key}}` |
| `Content-Type` | `application/json` |

A variável `{{api_key}}` armazena a chave da API do projeto Supabase. O header `Authorization` utiliza o formato `Bearer` para enviar a chave, enquanto `Content-Type` indica que o corpo da requisição está no formato JSON.

**5.4 Body JSON utilizado:**
O corpo da requisição foi configurado no formato JSON, utilizando as variáveis `{{email}}` e `{{password}}`, que correspondem ao e-mail e à senha do usuário de teste armazenados no Environment do Postman.

```json
{
  "email": "{{email}}",
  "password": "{{password}}"
}
```

**5.5 Finalidade da requisição:**
A requisição tem como finalidade realizar a autenticação de um usuário na API do Supabase por meio do e-mail e da senha. A partir da resposta recebida, é possível verificar se as credenciais são válidas, analisar o código de status HTTP e observar os dados retornados pela API.

**5.6 Evidências:**
As evidências da configuração das requisições HTTP estão disponíveis na pasta 'prints/postman' deste repositório.

---
# 6. Execução dos Testes
---

**6.1 Quais cenários foram executados:**
Foram executados cinco cenários para verificar a autenticação da API do Supabase: login válido, senha incorreta, usuário inexistente, campos vazios e credenciais inválidas.

**6.2 Quais entradas foram utilizadas:**
Foram utilizadas diferentes combinações de e-mail e senha, incluindo credenciais válidas, senha incorreta, e-mail não cadastrado, campos vazios e credenciais inválidas.

**6.3 Quais resultados foram obtidos:**
- Login válido: retornou 200 OK, com os dados da sessão e o access_token.
- Senha incorreta: retornou 400 Bad Request, com a mensagem invalid_credentials.
- Usuário inexistente: retornou 400 Bad Request, com a mensagem invalid_credentials.
- Campos vazios: retornou 400 Bad Request, com a mensagem missing email or phone.
- Credenciais inválidas: retornou 400 Bad Request, com a mensagem invalid_credentials.

**6.4 Quais erros foram encontrados:**
- Senha incorreta: invalid_credentials.
- Usuário inexistente: invalid_credentials.
- Campos vazios: missing email or phone.
- Credenciais inválidas: invalid_credentials.
As mensagens retornadas pela API corresponderam às tentativas de autenticação inválidas realizadas durante os testes, sem erros inesperados identificados.

### 6.5 Tabela de Cenários

| Cenário | Entrada Utilizada | Resultado Esperado | Resultado Obtido | Status |
|---|---|---|---|---|
| Login válido | E-mail e senha corretos | Status 200 + access token | 200 OK + access token | OK |
| Senha incorreta | E-mail cadastrado e senha incorreta | Erro de autenticação | 400 Bad Request — `invalid_credentials` | OK |
| Usuário inexistente | E-mail não cadastrado | Acesso negado | 400 Bad Request — `invalid_credentials` | OK |
| Campos vazios | E-mail e senha vazios | Erro de validação | 400 Bad Request — `missing email or phone` | OK |
| Credenciais inválidas | Credenciais incorretas | Mensagem de erro | 400 Bad Request — `invalid_credentials` | OK |


**6.6 Evidências obrigatórias:**
As evidências dos testes estão disponíveis na pasta 'prints/postman' deste repositório.

---
# 7. Registro dos Testes
---

**7.1 Como os testes foram registrados:**
Os testes foram executados no Postman e seus resultados foram registrados em uma planilha, contendo o ID do teste, cenário, entrada utilizada, resultado esperado, resultado obtido, status e observações.

**7.2 Qual a importância da documentação dos testes:**
A documentação dos testes é importante para facilitar a compreensão dos cenários executados, organizar os resultados, comparar o que era esperado com o que foi obtido e identificar possíveis falhas na API.

**7.3 Quais falhas foram identificadas:**
As únicas falhas identificadas foram as respostas de erro previstas nos cenários de teste, como senha incorreta, usuário inexistente, credenciais inválidas e campos vazios. A API apresentou o comportamento esperado em todas as situações, sem falhas inesperadas.

**7.4 Evidências obrigatórias:**
As evidências do registro dos testes estão disponíveis na pasta 'prints/planilha' deste repositório.

---
# 8. Resultados Obtidos
---

Login válido: a API retornou 200 OK, com os dados da sessão e o access_token, confirmando a autenticação.

Senha incorreta: a API retornou 400 Bad Request, com a mensagem invalid_credentials.

Usuário inexistente: a API retornou 400 Bad Request, com a mensagem invalid_credentials.

Campos vazios: a API retornou 400 Bad Request, com a mensagem missing email or phone, indicando que o e-mail ou telefone não foi informado.

Credenciais inválidas: a API retornou 400 Bad Request, com a mensagem invalid_credentials.

Os resultados demonstraram que a API autenticou o usuário com credenciais válidas e rejeitou as tentativas inválidas, retornando mensagens de erro de acordo com os dados enviados em cada requisição.

---
# 9. Conclusão
---

Os testes caixa cinza foram executados corretamente utilizando o Postman, permitindo verificar o funcionamento da autenticação da API do Supabase em diferentes cenários.
A autenticação funcionou conforme esperado: as credenciais válidas permitiram o login e o retorno do access_token, enquanto as tentativas com credenciais inválidas foram rejeitadas pela API.
Durante a atividade, uma das dificuldades foi compreender e utilizar as plataformas Supabase e Postman, especialmente na configuração das requisições HTTP, no preenchimento dos headers e do body JSON e na interpretação das respostas retornadas pela API.
As falhas identificadas foram as respostas de erro previstas nos cenários de teste, sem erros inesperados.
Como melhorias, poderiam ser implementadas mensagens de validação mais explicativas e novos cenários de teste com diferentes usuários e combinações de credenciais, ampliando a cobertura dos testes.
A atividade demonstrou a importância dos testes caixa cinza em APIs, pois permitem analisar o comportamento da aplicação com base em informações internas e externas, identificar possíveis problemas e verificar se os mecanismos de autenticação funcionam corretamente.
