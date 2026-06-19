## Suíte de Testes Manuais

# CT-01: Validar tentativa de login com senha incorreta (Fluxo Negativo)
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