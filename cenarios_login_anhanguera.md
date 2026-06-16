# Suíte de Teste - Tela de Login Anhanguera

## CT-03: Validar tentativa de login com senha incorreta (Fluxo Negativo)
* **PréCondição:** Usuário cadastrado no banco de dados.
* **Passo a passo:**
    1. Acessar a URL de login da anhanguera.
    2. Clicar na caixa referente ao cpf.
    3. Inserir um CPF válido.
    4. Clicar no botão "Avançar".
    5. Inserir uma senha incorreta.
    6. Clicar no botão "Entrar"
* **Resultado Esperado:** O sistema não deve permitir o login. O campo de senha deve exibir a mensagem de validação: "Senha incorreta", e o foco do cursor deve ser direcionado para ele.