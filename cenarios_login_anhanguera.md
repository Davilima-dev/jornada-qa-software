# Suíte de Testes Anhanguera

## CT-01: Validar tentativa de login com senha incorreta (Fluxo Negativo)
* **PréCondição:** Usuário cadastrado no banco de dados.
* **Passo a passo:**
    1. Acessar a URL de login da anhanguera.
    2. Clicar na caixa referente ao cpf.
    3. Inserir um CPF válido.
    4. Clicar no botão "Avançar".
    5. Inserir uma senha incorreta.
    6. Clicar no botão "Entrar"
* **Resultado Esperado:** O sistema não deve permitir o login. O campo de senha deve exibir a mensagem de validação: "Senha incorreta", e o foco do cursor deve ser direcionado para ele.



## Aplicação de Técnicas - Campo de Idade de Cadastro

**Requisito do Sistema:** O usuário só pode se cadastrar no sistema se tiver idade entre 18 e 60 anos (inclusive).

### Partição de Equivalência (Classes de Equivalência)
* **Classe Inválida (Menor):** Idade de 16 anos.
    * *Resultado Esperado:* O sistema deve recusar o cadastro e exibir mensagem de erro indicando idade mínima.
* **Classe Válida (Dentro):** Idade de 40 anos.
    * *Resultado Esperado:* O sistema deve aceitar o dado e avançar no cadastro.
* **Classe Inválida (Maior):** Idade de 80 anos.
    * *Resultado Esperado:* O sistema deve recusar o cadastro e exibir mensagem de erro indicando idade máxima.

## Desafio do CPF (11 dígitos)

**Requisito do Sistema:** O campo de CPF deve aceitar uma string contendo exatamente 11 caracteres numéricos.

* **Partição Menor (Inválida):** Testar com um CPF de 10 dígitos.
* **Partição Válida:** Testar com um CPF de 11 dígitos.
* **Partição Maior (Inválida):** Testar com um CPF de 12 dígitos.

## Report de Bug Simulado (Exemplo Real)

**ID do Bug:* BUG-01
**Título:** [Login] - Sistema exibe Erro 500 internodo servidor ao inserir senha incorreta.
**Gravidade:** Crítica (Impede o fluxo correto de tratamento de erro)

### Descrição
Ao tentar realizar o login com uma senha inválida, o sistema quebra retornando um erro de infraestrutura (HTTP 500) em vez de existir a mensagem amigável de "Senha incorreta".

### Passo a Passo para Reproduzir
1. Acessar a página de login da Anhanguera.
2. Inserir um CPF válido e cadastrado.
3. Clicar em "Prosseguir".
4. Inserir uma senha incorreta (ex: '123456').
5. Clicar no botão "Entrar".

### Resultados
* **Resultado Atual:** O sistema renderiza uma tela branca com o texto 'Erro 500: Internet Server Error'.
* **Resultado Esperado:** O sistema deve permanecer na tela, limpar o campo de senha e exibir o alerta: '"Senha Incorreta. Tente novamente."'