# Especificação de Caso de Uso: Cadastrar Empresa

**Sistema:** ContabSys - Sistema Integrado de Gestão Contábil  
**Caso de Uso:** UC-001 - Cadastrar Empresa  
**Versão:** 1.0  
**Data:** 09/11/2025  
**Autor:** Equipe de Desenvolvimento

---

## 1. Descrição

Este caso de uso permite que o administrador ou contador cadastre uma nova empresa cliente no sistema ContabSys, registrando todas as informações necessárias para a gestão contábil, fiscal e trabalhista.

---

## 2. Atores

- **Ator Principal:** Administrador, Contador
- **Atores Secundários:** Sistema de Validação de CNPJ (Receita Federal)

---

## 3. Pré-condições

- O usuário deve estar autenticado no sistema
- O usuário deve ter permissões de administrador ou contador
- O sistema deve estar conectado à internet para validação do CNPJ

---

## 4. Pós-condições

### Sucesso:
- A empresa é cadastrada no sistema com status "Ativa"
- Um registro único de empresa é criado no banco de dados
- O sistema envia e-mail de confirmação ao responsável da empresa
- A empresa fica disponível para seleção em outros módulos do sistema

### Falha:
- Nenhuma alteração é realizada no banco de dados
- Mensagem de erro é exibida ao usuário

---

## 5. Fluxo Principal (Cenário de Sucesso)

1. O usuário acessa o menu "Empresas" no sistema
2. O sistema exibe a tela de listagem de empresas
3. O usuário clica no botão "+ Nova Empresa"
4. O sistema exibe o formulário de cadastro de empresa com abas:
   - Dados Básicos
   - Endereço
   - Tributação
   - Responsáveis
5. O usuário preenche os **Dados Básicos**:
   - CNPJ (obrigatório)
   - Razão Social (obrigatório)
   - Nome Fantasia
   - Inscrição Estadual
   - Inscrição Municipal
   - Telefone
   - E-mail
   - Data de Abertura
6. O sistema valida o CNPJ em tempo real consultando a base da Receita Federal
7. O sistema preenche automaticamente a Razão Social se disponível na consulta
8. O usuário navega para a aba "Endereço" e preenche:
   - CEP
   - Logradouro
   - Número
   - Complemento
   - Bairro
   - Cidade
   - Estado
9. O sistema busca automaticamente o endereço ao digitar o CEP
10. O usuário navega para a aba "Tributação" e seleciona:
    - Regime Tributário (obrigatório): Simples Nacional, Lucro Presumido ou Lucro Real
    - Anexo do Simples (se aplicável)
    - Atividade Principal (CNAE)
    - Atividades Secundárias
11. O usuário navega para a aba "Responsáveis" e cadastra:
    - Nome do responsável legal
    - CPF
    - E-mail
    - Telefone
    - Cargo
12. O usuário clica no botão "Salvar"
13. O sistema valida todos os campos obrigatórios
14. O sistema verifica se não existe empresa já cadastrada com o mesmo CNPJ
15. O sistema salva os dados no banco de dados
16. O sistema gera um código único de identificação para a empresa
17. O sistema exibe mensagem de sucesso: "Empresa cadastrada com sucesso!"
18. O sistema retorna para a tela de listagem de empresas
19. O sistema envia e-mail de boas-vindas ao responsável da empresa
20. Caso de uso encerrado

---

## 6. Fluxos Alternativos

### FA01 - CNPJ inválido (passo 6)

6a. O sistema detecta que o CNPJ digitado é inválido
6b. O sistema exibe mensagem de erro abaixo do campo: "CNPJ inválido. Verifique os dígitos."
6c. O sistema marca o campo em vermelho
6d. O usuário corrige o CNPJ
6e. Retorna ao passo 6 do fluxo principal

### FA02 - CNPJ já cadastrado (passo 14)

14a. O sistema detecta que já existe empresa cadastrada com este CNPJ
14b. O sistema exibe mensagem: "Já existe uma empresa cadastrada com este CNPJ. Deseja visualizar o cadastro existente?"
14c. O usuário escolhe:
   - Se "Sim": o sistema redireciona para a tela de visualização da empresa existente
   - Se "Não": o sistema retorna ao formulário de cadastro
14d. Caso de uso encerrado

### FA03 - Busca de CEP falha (passo 9)

9a. O sistema não consegue encontrar o endereço pelo CEP
9b. O sistema exibe mensagem: "CEP não encontrado. Preencha manualmente."
9c. O sistema habilita os campos de endereço para preenchimento manual
9d. O usuário preenche manualmente todos os campos de endereço
9e. Retorna ao passo 10 do fluxo principal

### FA04 - Usuário cancela o cadastro (qualquer passo)

Xa. O usuário clica no botão "Cancelar"
Xb. O sistema exibe mensagem de confirmação: "Deseja realmente cancelar? Os dados não salvos serão perdidos."
Xc. O usuário confirma:
   - Se "Sim": o sistema descarta os dados e retorna à listagem de empresas
   - Se "Não": o sistema retorna ao formulário de cadastro
Xd. Caso de uso encerrado

### FA05 - Validação de campos obrigatórios falha (passo 13)

13a. O sistema detecta que campos obrigatórios não foram preenchidos
13b. O sistema exibe mensagem de erro: "Preencha todos os campos obrigatórios"
13c. O sistema marca em vermelho todos os campos obrigatórios não preenchidos
13d. O sistema rola a tela até o primeiro campo com erro
13e. O usuário preenche os campos faltantes
13f. Retorna ao passo 12 do fluxo principal

---

## 7. Fluxos de Exceção

### FE01 - Erro de conexão com a base da Receita Federal (passo 6)

6a. O sistema não consegue conectar com a API da Receita Federal
6b. O sistema exibe mensagem: "Não foi possível validar o CNPJ online. Deseja continuar sem validação?"
6c. O usuário escolhe:
   - Se "Sim": o sistema permite continuar o cadastro sem validação automática
   - Se "Não": o sistema aguarda nova tentativa
6d. Retorna ao passo 7 do fluxo principal

### FE02 - Erro ao salvar no banco de dados (passo 15)

15a. O sistema tenta salvar os dados mas ocorre erro no banco de dados
15b. O sistema registra o erro no log do sistema
15c. O sistema exibe mensagem: "Erro ao salvar a empresa. Tente novamente."
15d. Os dados preenchidos são mantidos no formulário
15e. O usuário pode tentar salvar novamente
15f. Retorna ao passo 12 do fluxo principal

### FE03 - Erro ao enviar e-mail (passo 19)

19a. O sistema não consegue enviar o e-mail de boas-vindas
19b. O sistema registra a falha no log
19c. O sistema exibe mensagem de aviso: "Empresa cadastrada, mas não foi possível enviar e-mail de confirmação"
19d. A empresa permanece cadastrada normalmente
19e. Caso de uso encerrado

---

## 8. Requisitos Especiais

### Requisitos de Interface:
- O formulário deve ser responsivo e funcionar em diferentes tamanhos de tela
- Campos obrigatórios devem ser claramente marcados com asterisco (*)
- O sistema deve exibir feedback visual durante validações e salvamento

### Requisitos de Desempenho:
- A validação do CNPJ deve ocorrer em no máximo 3 segundos
- O salvamento dos dados deve ser concluído em no máximo 2 segundos
- A busca de CEP deve retornar resultado em no máximo 2 segundos

### Requisitos de Segurança:
- Apenas usuários com perfil Administrador ou Contador podem cadastrar empresas
- Todas as ações devem ser registradas em log de auditoria
- Dados sensíveis devem ser criptografados no banco de dados

### Requisitos de Usabilidade:
- O sistema deve permitir navegação por teclado (Tab, Enter)
- Mensagens de erro devem ser claras e orientar o usuário na correção
- O sistema deve salvar automaticamente rascunhos a cada 2 minutos

---
