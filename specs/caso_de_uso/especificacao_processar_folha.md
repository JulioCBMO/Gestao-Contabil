# Especificação de Caso de Uso: Processar Folha de Pagamento

**Sistema:** ContabSys - Sistema Integrado de Gestão Contábil  
**Caso de Uso:** UC-020 - Processar Folha de Pagamento  
**Versão:** 1.0  
**Data:** 09/11/2025  
**Autor:** Equipe de Desenvolvimento

---

## 1. Descrição

Este caso de uso permite que o auxiliar contábil processe a folha de pagamento mensal de uma empresa, calculando automaticamente salários, descontos (INSS, IRRF, vale-transporte, vale-refeição), encargos patronais e gerando os contracheques dos funcionários.

---

## 2. Atores

- **Ator Principal:** Auxiliar Contábil
- **Atores Secundários:** Contador (supervisor), Sistema de Cálculo Trabalhista

---

## 3. Pré-condições

- O usuário deve estar autenticado no sistema
- O usuário deve ter permissões de auxiliar contábil ou superior
- A empresa deve estar cadastrada no sistema
- Os funcionários da empresa devem estar cadastrados
- As tabelas de INSS e IRRF devem estar atualizadas para o período
- Os eventos variáveis do mês devem ter sido lançados (horas extras, faltas, etc.)

---

## 4. Pós-condições

### Sucesso:
- A folha de pagamento é processada e salva no sistema
- Os contracheques são gerados em PDF
- Os totalizadores de encargos são calculados
- As guias de FGTS e GPS são geradas
- O sistema registra o processamento no histórico
- Notificações são enviadas ao contador responsável

### Falha:
- Nenhuma alteração é realizada no banco de dados
- Mensagem de erro é exibida ao usuário
- O processamento pode ser retomado do ponto de falha

---

## 5. Fluxo Principal (Cenário de Sucesso)

1. O usuário acessa o menu "Trabalhista" > "Folha de Pagamento"
2. O sistema exibe a tela de processamento de folha
3. O usuário seleciona:
   - Empresa (obrigatório)
   - Mês/Ano de competência (obrigatório)
   - Tipo de folha: Mensal, Férias, 13º Salário, Rescisão
4. O sistema exibe a lista de funcionários ativos da empresa
5. O sistema apresenta o status de cada funcionário:
   - Pronto para processar (todos os dados completos)
   - Pendente (faltam informações ou eventos)
   - Bloqueado (erros cadastrais)
6. O usuário clica em "Calcular Folha"
7. O sistema exibe diálogo de confirmação: "Deseja processar a folha de [Empresa] referente a [Mês/Ano]?"
8. O usuário confirma
9. O sistema inicia o processamento com barra de progresso
10. Para cada funcionário, o sistema calcula:
    - **Proventos:**
      - Salário base (proporcional aos dias trabalhados)
      - Horas extras (50%, 100%)
      - Adicional noturno
      - DSR sobre horas extras
      - Comissões
      - Gratificações
      - Outros proventos cadastrados
    - **Descontos:**
      - INSS (conforme faixa salarial)
      - IRRF (conforme faixa e dependentes)
      - Vale-transporte (6% sobre salário base, se houver)
      - Vale-refeição (se houver desconto)
      - Plano de saúde (se houver)
      - Faltas e atrasos
      - Adiantamento salarial
      - Pensão alimentícia
      - Outros descontos cadastrados
    - **Líquido a receber:** Total de proventos - Total de descontos
    - **Encargos patronais:**
      - INSS Patronal (20% + RAT + 3ª parte)
      - FGTS (8% sobre salário)
      - Salário Educação
      - Sistema S (SESI, SENAI, etc.)
11. O sistema valida todos os cálculos
12. O sistema gera os contracheques em PDF individuais
13. O sistema consolida os totalizadores:
    - Total de proventos
    - Total de descontos
    - Total líquido
    - Total de encargos patronais
    - Total de FGTS
    - Total de INSS a recolher
14. O sistema gera as guias de recolhimento:
    - GPS (INSS)
    - FGTS (SEFIP/GRF)
15. O sistema salva todos os dados no banco
16. O sistema exibe relatório de processamento com:
    - Número de funcionários processados
    - Total da folha
    - Valores de encargos
    - Links para download de contracheques e guias
17. O sistema envia notificação ao contador responsável
18. O usuário pode:
    - Visualizar contracheques individuais
    - Fazer download em lote de todos os contracheques
    - Visualizar e imprimir guias
    - Exportar relatórios
19. Caso de uso encerrado

---

## 6. Fluxos Alternativos

### FA01 - Folha já processada para o período (passo 7)

7a. O sistema detecta que já existe folha processada para empresa/período
7b. O sistema exibe mensagem: "Já existe folha processada para este período. Deseja:"
   - Visualizar folha existente
   - Reprocessar (substituir a existente)
   - Cancelar
7c. Se usuário escolher "Reprocessar":
   - Sistema solicita confirmação adicional
   - Sistema marca a folha anterior como "Substituída"
   - Continua no passo 8 do fluxo principal
7d. Se usuário escolher "Visualizar":
   - Sistema exibe a folha já processada
   - Caso de uso encerrado

### FA02 - Funcionários com pendências (passo 5)

5a. O sistema identifica funcionários com status "Pendente" ou "Bloqueado"
5b. O sistema exibe lista detalhada das pendências:
   - Funcionário sem dados bancários
   - Funcionário sem dependentes cadastrados (para IRRF)
   - Eventos variáveis não lançados
   - Salário não informado
5c. O usuário pode:
   - Corrigir as pendências e retornar ao processamento
   - Processar apenas funcionários sem pendências
   - Cancelar o processamento
5d. Retorna ao passo 6 do fluxo principal

### FA03 - Ajuste manual de valores (após passo 10)

10a. O usuário identifica necessidade de ajuste em algum cálculo
10b. O usuário clica em "Editar" no funcionário específico
10c. O sistema exibe tela de ajustes permitindo:
   - Adicionar/remover proventos manualmente
   - Adicionar/remover descontos manualmente
   - Ajustar valores calculados (com justificativa)
10d. O sistema registra os ajustes no log de auditoria
10e. O sistema recalcula os valores do funcionário
10f. Retorna ao passo 11 do fluxo principal

### FA04 - Exportar para conferência antes de finalizar (passo 11)

11a. O usuário clica em "Exportar Prévia"
11b. O sistema gera planilha Excel com todos os cálculos
11c. O usuário revisa os valores externamente
11d. O usuário retorna ao sistema
11e. Se necessário ajuste: vai para FA03
11f. Se está correto: retorna ao passo 12 do fluxo principal

### FA05 - Processamento em lotes (passo 9)

9a. O usuário marca opção "Processar em lotes"
9b. O sistema divide os funcionários em lotes de 50
9c. O sistema processa lote por lote com intervalo de 2 segundos
9d. O sistema atualiza barra de progresso a cada lote
9e. Retorna ao passo 10 do fluxo principal

---

## 7. Fluxos de Exceção

### FE01 - Tabela de INSS/IRRF desatualizada (passo 10)

10a. O sistema detecta que as tabelas de INSS ou IRRF não estão atualizadas para o período
10b. O sistema interrompe o processamento
10c. O sistema exibe mensagem: "Tabelas de INSS/IRRF desatualizadas para [Mês/Ano]. Atualize as tabelas antes de processar."
10d. O sistema direciona o usuário para a tela de atualização de tabelas
10e. Após atualização, usuário pode retornar e reiniciar o processamento
10f. Caso de uso encerrado

### FE02 - Erro de cálculo em funcionário específico (passo 10)

10a. O sistema encontra erro ao calcular folha de um funcionário específico
10b. O sistema registra o erro no log
10c. O sistema marca o funcionário como "Erro no processamento"
10d. O sistema continua processando os demais funcionários
10e. Ao final, o sistema exibe lista de funcionários com erro
10f. O usuário deve corrigir os problemas e reprocessar apenas os funcionários com erro
10g. Retorna ao passo 6 do fluxo principal

### FE03 - Falha ao gerar contracheques PDF (passo 12)

12a. O sistema falha ao gerar um ou mais contracheques em PDF
12b. O sistema registra a falha no log
12c. O sistema continua o processamento e salva os dados
12d. O sistema exibe aviso: "Folha processada com sucesso, mas houve falha ao gerar alguns contracheques"
12e. O sistema permite regenerar os PDFs posteriormente
12f. Continua no passo 13 do fluxo principal

### FE04 - Falha ao salvar no banco de dados (passo 15)

15a. O sistema tenta salvar mas ocorre erro no banco de dados
15b. O sistema registra o erro detalhado no log
15c. O sistema exibe mensagem: "Erro ao salvar a folha. Os dados foram preservados temporariamente."
15d. O sistema armazena os cálculos em cache
15e. O sistema permite tentar salvar novamente
15f. Se erro persistir, usuário deve contatar suporte
15g. Retorna ao passo 15 do fluxo principal

### FE05 - Timeout no processamento (passo 10)

10a. O processamento excede o tempo máximo permitido (10 minutos)
10b. O sistema interrompe o processamento
10c. O sistema salva o progresso até o momento
10d. O sistema exibe mensagem: "Processamento interrompido por timeout. [X] funcionários processados de [Y]"
10e. O sistema permite retomar do ponto de parada
10f. Usuário pode ajustar filtros ou processar em lotes menores
10g. Retorna ao passo 6 do fluxo principal

---

## 8. Requisitos Especiais

### Requisitos de Interface:
- Barra de progresso deve mostrar percentual e funcionário sendo processado
- Contracheques devem seguir layout padrão do Ministério do Trabalho
- Interface deve permitir visualização individual de cada contracheque antes da finalização
- Sistema deve destacar visualmente funcionários com pendências ou erros

### Requisitos de Desempenho:
- O processamento deve calcular até 1000 funcionários em menos de 10 minutos
- Cada cálculo individual deve levar menos de 500ms
- A geração de PDF de contracheque deve levar menos de 2 segundos
- O sistema deve permitir processamento em segundo plano para folhas grandes

### Requisitos de Segurança:
- Apenas usuários autorizados podem processar folha de pagamento
- Todas as alterações manuais devem ser registradas em log de auditoria
- Contracheques devem ser protegidos por senha (CPF do funcionário)
- Dados salariais devem ser criptografados no banco de dados

### Requisitos de Precisão:
- Cálculos devem ter precisão de 2 casas decimais
- Arredondamentos devem seguir regras da CLT
- Totalizadores devem conferir com soma dos individuais
- Sistema deve validar se INSS + IRRF não ultrapassam limites legais

---

## 9. Regras de Negócio

| ID | Regra | Descrição |
|----|-------|-----------|
| RN020-01 | Cálculo INSS | INSS calculado por faixa salarial conforme tabela vigente, respeitando teto máximo |
| RN020-02 | Cálculo IRRF | IRRF calculado por faixa após dedução de INSS e dependentes, conforme tabela vigente |
| RN020-03 | Vale-Transporte | Desconto de 6% sobre salário base, limitado ao valor efetivo do VT |
| RN020-04 | DSR | Domingos e Feriados Remunerados incidentes sobre horas extras |
| RN020-05 | Proporcionalidade | Funcionário admitido/demitido no mês tem cálculo proporcional aos dias |
| RN020-06 | Adicional Noturno | Hora noturna (22h às 5h) vale 20% a mais e tem duração de 52min30s |
| RN020-07 | Hora Extra | Hora extra normal: 50%, hora extra domingo/feriado: 100% |
| RN020-08 | Encargos Patronais | INSS Patronal 20% + RAT (varia) + Terceiros 5,8% + FGTS 8% |
| RN020-09 | Salário Família | Pago conforme tabela e número de filhos até 14 anos |
| RN020-10 | Pensão Alimentícia | Descontada antes de INSS e IRRF se determinado judicialmente |

---

## 10. Cálculos Detalhados

### Exemplo de Cálculo Completo (Novembro/2025):

**Funcionário:** João Silva  
**Salário Base:** R$ 3.500,00  
**Dias trabalhados:** 30/30  
**Dependentes IRRF:** 2

**PROVENTOS:**
```
Salário Base:              R$ 3.500,00
Horas Extras (10h a 50%):  R$   238,64
DSR s/ Horas Extras:       R$    39,77
TOTAL PROVENTOS:           R$ 3.778,41
```

**DESCONTOS:**
```
INSS (12%):                R$   420,00
IRRF:                      R$    45,83
  Base cálculo: 3.778,41 - 420,00 - 378,00 = 2.980,41
  Faixa: 2.826,65 a 3.751,05 (15%)
  Cálculo: (2.980,41 × 15%) - 381,44 = 45,83
Vale Transporte (6%):      R$   210,00
TOTAL DESCONTOS:           R$   675,83

LÍQUIDO A RECEBER:         R$ 3.102,58
```

**ENCARGOS PATRONAIS:**
```
INSS Patronal (20%):       R$   755,68
RAT (2%):                  R$    75,57
Terceiros (5,8%):          R$   219,15
FGTS (8%):                 R$   302,27
TOTAL ENCARGOS:            R$ 1.352,67
```

---

## 11. Pontos de Extensão

- **PE01:** Sistema pode integrar com ponto eletrônico para importar automaticamente horas trabalhadas
- **PE02:** Sistema pode enviar contracheques por e-mail automaticamente aos funcionários
- **PE03:** Sistema pode gerar arquivo SEFIP automaticamente para envio à Caixa Econômica
- **PE04:** Sistema pode integrar com folha anterior para trazer adiantamentos e empréstimos

---

## 12. Frequência de Uso

- **Frequência Estimada:** 1 vez por mês por empresa cadastrada
- **Pico de Uso:** Dias 20 a 30 de cada mês (fechamento mensal)
- **Criticidade:** Muito Alta - Processamento deve ser 100% confiável

---

## 14. Validações Críticas

### Antes do Processamento:
- ✓ Empresa ativa no sistema
- ✓ Período competência válido (não futuro)
- ✓ Tabelas INSS/IRRF atualizadas
- ✓ Funcionários ativos têm salário cadastrado
- ✓ Não existe folha fechada para o período

### Durante o Processamento:
- ✓ Salário base maior que salário mínimo
- ✓ Soma de proventos e descontos conferem
- ✓ INSS não ultrapassa teto
- ✓ IRRF não resulta em valor negativo
- ✓ Líquido a receber maior que zero

### Após o Processamento:
- ✓ Total individual = total consolidado
- ✓ Todos os contracheques foram gerados
- ✓ Guias de recolhimento estão corretas
- ✓ Dados salvos no banco

---

## 16. Rastreabilidade

### Requisitos Funcionais Relacionados:
- **RF019:** Cadastrar funcionários
- **RF020:** Processar folha de pagamento mensal
- **RF021:** Calcular férias, 13º salário e rescisões
- **RF023:** Gerar guias de FGTS e GPS
- **RF024:** Gerar contracheques em PDF

### Requisitos Não-Funcionais Relacionados:
- **RNF006:** Atender LGPD
- **RNF012:** Dados criptografados
- **RNF039:** Processar 1000 funcionários em até 10 minutos
- **RNF068:** Garantir confiabilidade nos cálculos
- **RNF070:** Taxa de erros inferior a 0,1%

---
