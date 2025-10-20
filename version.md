<h1>Visão do Produto</h1>

<h2>ContabSys</h2>

<small>Versão 1.0</small>

---

## Histórico de revisões

|    Data    | Versão |           Descrição           |      Autor       |
| :--------: | :----: | :---------------------------: | :--------------: |
| 19/10/2025 |  1.0   |     Criação do documento      | Júlio, Felipe |

---

## Sumário

- [Introdução](#introdução)
  - [Propósito](#propósito)
  - [Definições e abreviações](#definições-e-abreviações)
    - [Abreviações](#abreviações)
    - [Definições](#definições)
  - [Escopo do produto](#escopo-do-produto)
- [Posicionamento](#posicionamento)
  - [Oportunidade de negócios](#oportunidade-de-negócios)
  - [Descrição dos benefícios para os clientes e dos problemas resolvidos](#descrição-dos-benefícios-para-os-clientes-e-dos-problemas-resolvidos)
- [Descrição dos stakeholders e dos usuários](#descrição-dos-stakeholders-e-dos-usuários)
  - [Stakeholders](#stakeholders)
  - [Usuários e atores](#usuários-e-atores)
- [Descrição do ambiente de uso](#descrição-do-ambiente-de-uso)
  - [Ambiente de uso](#ambiente-de-uso)
  - [Necessidades principais quanto ao ambiente](#necessidades-principais-quanto-ao-ambiente)
- [Visão geral do produto](#visão-geral-do-produto)
  - [Visão geral](#visão-geral)
  - [Custo e venda](#custo-e-venda)
  - [Licenciamento e instalação](#licenciamento-e-instalação)
  - [Características e funcionalidades de alto nível](#características-e-funcionalidades-de-alto-nível)
  - [Restrições](#restrições)

# Introdução

O Documento de Visão do Produto (DVP) é um documento que descreve o produto de software que será desenvolvido. Ele descreve o problema que será resolvido, as principais necessidades dos stakeholders, as principais funcionalidades do sistema, as restrições do projeto, etc.

## Propósito

O objetivo deste documento é coletar, analisar e definir características e as necessidades de alto nível do **ContabSys.**

Ele se concentra nos recursos necessários aos stakeholders e aos usuários, e nas razões que levam a essas necessidades.

Os detalhes de como o **ContabSys** atingem essas necessidades são descritos nas _especificações de casos de uso_ e nos _requisitos funcionais_.

## Definições e abreviações

### Abreviações

| Termo | Definição                                    |
| :---: | -------------------------------------------- |
| eSocial | Sistema de Escrituração Digital das Obrigações Fiscais, Previdenciárias e Trabalhistas |
| SPED  | Sistema Público de Escrituração Digital      |
| NF-e  | Nota Fiscal Eletrônica                       |
| LGPD  | Lei Geral de Proteção de Dados               |


### Definições

|    Termo    | Definição                                                                                                                       |
| :---------: | ------------------------------------------------------------------------------------------------------------------------------- |
| Contador    | Profissional responsável pela gestão contábil e fiscal das empresas clientes do escritório.                                     |
| Auxiliar Contábil | Profissional que auxilia o contador nas rotinas contábeis e administrativas.                                      |
| Setor Fiscal | Departamento responsável pelas obrigações fiscais e tributárias das empresas.                                              |
| Obrigação Acessória | Declarações e informações que devem ser prestadas ao Fisco periodicamente.                                      |
| Integração Bancária | Conexão automática com instituições bancárias para importação de extratos e conciliação financeira.           |
| Módulo | Componente do sistema responsável por uma área específica (contábil, fiscal, trabalhista ou financeira).                         |

## Escopo do produto

O **ContabSys** é um sistema que tem como objetivo integrar todas as áreas contábil, fiscal, trabalhista e financeira em um único ambiente. Será utilizado por escritórios de contabilidade que necessitam centralizar suas operações, eliminar a dependência de múltiplos sistemas e oferecer aos seus clientes um portal para envio de documentos e acompanhamento de obrigações em tempo real.

---

# Posicionamento

## Oportunidade de negócios

O **ContabSys** apresenta várias oportunidades de negócios, tais como:

1. **Revenda para outros escritórios**: O sistema pode ser comercializado como produto para outros escritórios de contabilidade, gerando receita recorrente através de licenciamento.
2. **Modelo SaaS (Software como Serviço)**: Oferecer o sistema em nuvem com planos de assinatura mensal ou anual, eliminando custos de infraestrutura para os clientes.
3. **Consultoria e implantação**: Serviços de consultoria para customização, implantação e treinamento de equipes em escritórios contábeis.
4. **Integrações personalizadas**: Desenvolvimento de integrações específicas com outros sistemas utilizados pelos clientes, agregando valor ao produto.
5. **Marketplace de serviços**: Criar um ecossistema onde contadores possam oferecer serviços adicionais aos seus clientes através da plataforma.
6. **Módulos adicionais**: Comercializar funcionalidades premium como business intelligence, análise preditiva e automação avançada de processos.

## Descrição dos benefícios para os clientes e dos problemas resolvidos

| Benefícios                    | Problemas Resolvidos                                                    | Afetados                                   |
| ----------------------------- | ----------------------------------------------------------------------- | ------------------------------------------ |
| Redução de custos   | Necessidade de contratar múltiplos sistemas para executar todas as rotinas contábeis, fiscais e trabalhistas | Escritórios de contabilidade |
| Ganho de eficiência e produtividade        | Falta de integração entre sistemas gerando retrabalho e perda de tempo | Contadores e auxiliares contábeis |
| Centralização de informações | Dificuldade para centralizar informações dos clientes em um único ambiente | Escritórios de contabilidade |
| Evitar multas e penalizações    | Risco de atrasos em obrigações legais por conta da dispersão de dados | Contadores e setor fiscal |
| Facilidade de uso | Interface complexa e pouco intuitiva dos sistemas atuais, dificultando o uso para novos funcionários | Contadores, auxiliares contábeis e clientes |
| Transparência para clientes | Falta de visibilidade sobre o andamento de obrigações e documentos | Clientes dos escritórios |
| Automatização de processos | Comunicação descentralizada via e-mail e WhatsApp para receber documentos | Escritórios de contabilidade e clientes |

---

# Descrição dos stakeholders e dos usuários

Esta seção descreve os stakeholders e os usuários do **ContabSys.**

## Stakeholders

Segue abaixo a lista de stakeholders.

| Stakeholder                            | Descrição                                                                                                                                               | Papel                                                           |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| Escritórios de Contabilidade           | Empresas que contratam o sistema para gerenciar suas operações contábeis, fiscais e trabalhistas.                                                       | Cliente e usuário principal do sistema                          |
| Equipe de Desenvolvimento              | Profissionais responsáveis por desenvolver e manter o sistema.                                                                                          | Desenvolvedores                                                 |
| Gerente de Projeto                     | Profissional responsável por gerenciar o projeto e garantir que o sistema seja entregue dentro do prazo e orçamento definidos.                          | Gerente de Projeto                                              |
| Órgãos Governamentais                  | Receita Federal, eSocial, SPED e outros órgãos fiscalizadores que recebem informações do sistema.                                                       | Receptores de obrigações acessórias                             |
| Clientes dos Escritórios               | Empresas e pessoas físicas que utilizam os serviços contábeis e acessam o portal para enviar documentos e acompanhar obrigações.                        | Usuários externos do sistema                                    |


## Usuários e atores

Segue tabela com os usuários e atores do sistema:

| Usuário                  | Descrição                                                                                                    | Responsabilidades                                                                                                                                                                                                                | Stakeholders                                                                                    |
| ------------------------ | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Contador                 | Profissional responsável pela gestão contábil e fiscal das empresas clientes do escritório. | Gerenciar lançamentos contábeis, elaborar demonstrações financeiras, supervisionar obrigações fiscais e trabalhistas, gerar relatórios para clientes. | Escritórios de Contabilidade, Equipe de Desenvolvimento, Gerente de Projeto |
| Auxiliar Contábil     | Profissional que auxilia o contador nas rotinas contábeis e administrativas. | Realizar lançamentos contábeis, organizar documentos fiscais, auxiliar na preparação de obrigações acessórias, processar folha de pagamento. | Escritórios de Contabilidade, Contador, Equipe de Desenvolvimento |
| Setor Fiscal | Departamento responsável pelas obrigações fiscais e tributárias das empresas. | Gerar e transmitir obrigações acessórias (SPED, eSocial, NF-e), acompanhar prazos fiscais, calcular tributos, manter atualizações sobre legislação. | Escritórios de Contabilidade, Órgãos Governamentais, Equipe de Desenvolvimento |
| Cliente (Empresa) | Empresa que utiliza os serviços do escritório contábil e acessa o sistema para enviar documentos e acompanhar obrigações. | Enviar documentos fiscais e trabalhistas digitalizados, acompanhar status de obrigações, visualizar relatórios, consultar prazos e pendências. | Escritórios de Contabilidade, Contador |
| Administrador do Sistema | Profissional responsável por gerenciar e manter o sistema. | Gerenciar usuários e permissões, realizar backup dos dados, configurar integrações, atualizar o sistema, garantir o funcionamento adequado. | Equipe de Desenvolvimento, Gerente de Projeto, Escritórios de Contabilidade |

---

# Descrição do ambiente de uso

## Ambiente de uso

A seguir, são descritos alguns ambientes em que o sistema pode ser utilizado:

1. **Ambiente do Escritório Contábil**: Neste ambiente, o sistema é utilizado pelos contadores, auxiliares contábeis e setor fiscal para executar todas as rotinas contábeis, fiscais, trabalhistas e financeiras. Os usuários podem acessar o sistema através de computadores com sistema operacional Windows ou Linux, utilizando navegadores web como Google Chrome, Mozilla Firefox ou Microsoft Edge. O acesso é feito através da internet mediante login e senha com controle de permissões por perfil de usuário.

2. **Ambiente do Cliente (Portal Web)**: Neste ambiente, o sistema é utilizado pelos clientes dos escritórios contábeis para enviar documentos digitalizados, acompanhar o status de suas obrigações fiscais e trabalhistas, visualizar relatórios e consultar prazos. O acesso é realizado através de navegadores web em computadores, notebooks, tablets ou smartphones com conexão à internet.

3. **Ambiente do Cliente (Aplicativo Mobile)**: O sistema disponibiliza um aplicativo mobile para os sistemas operacionais Android e iOS, permitindo que os clientes enviem documentos através de fotos ou arquivos, recebam notificações sobre prazos e pendências, e acompanhem suas obrigações em tempo real de qualquer lugar.

4. **Ambiente Administrativo**: Neste ambiente, o sistema é utilizado pelos administradores para gerenciar usuários, configurar permissões, realizar backups, monitorar o desempenho do sistema, configurar integrações bancárias e governamentais, e atualizar regras tributárias. O acesso é feito através de um navegador web em computador com credenciais de administrador.

5. **Ambiente de Integração**: Este ambiente é responsável pela comunicação automática do sistema com plataformas governamentais (eSocial, SPED, NF-e) e instituições bancárias, permitindo o envio e recebimento de informações fiscais, trabalhistas e financeiras de forma automatizada.

## Necessidades principais quanto ao ambiente

A seguir, é apresentada uma tabela que descreve as necessidades dos clientes com relação à qualidade, desempenho, segurança, usabilidade e confidencialidade do sistema Contabsys, juntamente com sua prioridade, interesse, solução atual e soluções propostas:

| Necessidade                                                                                                                                              | Prioridade | Interesse                                                                                                                                                | Solução Atual                                                                                                                 | Soluções Propostas                                                                                                                                                                                                                                                       |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Qualidade:** O sistema deve ser confiável, estável e com mínimo de falhas, garantindo cálculos corretos e integrações precisas. | Alta       | Os escritórios contábeis necessitam de um sistema que garanta conformidade com a legislação e evite erros que possam gerar multas e penalizações. | Uso de múltiplos sistemas consolidados no mercado (Domínio, Alterdata, Fortes) com diferentes níveis de confiabilidade. | Implementar testes automatizados, processos rigorosos de garantia de qualidade, validações de dados e homologações constantes com as plataformas governamentais. |
| **Desempenho:** O sistema deve ter respostas rápidas nas consultas e relatórios, além de capacidade para lidar com grandes volumes de dados. | Alta | Os usuários esperam agilidade no processamento de informações, especialmente em períodos de fechamento contábil e envio de obrigações. | Servidores dedicados com monitoramento de desempenho, porém limitações de performance em sistemas separados. | Otimizar arquitetura do sistema, implementar cache de dados, otimizar consultas ao banco de dados, utilizar processamento em lote para grandes volumes e arquitetura escalável em nuvem. |
| **Escalabilidade:** O sistema deve suportar o crescimento do número de empresas cadastradas e volume de transações sem perda de desempenho. | Alta | Os escritórios contábeis precisam adicionar novos clientes sem comprometer a performance do sistema. | Arquitetura escalável com servidores em nuvem e distribuição de carga. | Implementar arquitetura em nuvem elástica com balanceamento automático de carga, banco de dados distribuído e capacidade de expansão horizontal. |
| **Segurança:** O sistema deve proteger dados sensíveis (informações fiscais, financeiras e pessoais), com criptografia, controle de acesso e backup automático. | Alta | Os clientes exigem proteção de informações confidenciais conforme a LGPD e legislações específicas do setor contábil. | Autenticação com login e senha, criptografia de dados sensíveis, acesso restrito e backups periódicos. | Implementar autenticação de dois fatores, criptografia avançada (em trânsito e em repouso), certificados SSL/TLS, controle granular de permissões, auditoria de acessos, backup automático com redundância geográfica e conformidade com LGPD. |
| **Usabilidade:** O sistema deve ter interface intuitiva e de fácil aprendizado, reduzindo a necessidade de treinamentos constantes. | Alta | Os sistemas atuais possuem interfaces complexas que dificultam o uso por novos funcionários e exigem treinamento especializado. | Interface simples em sistemas atuais, porém com curva de aprendizado elevada devido à complexidade das funcionalidades. | Desenvolver interface moderna e intuitiva, com dashboards visuais, navegação simplificada, relatórios gráficos, design responsivo para diferentes dispositivos e sistema de ajuda contextual. |
| **Disponibilidade:** O sistema deve ter disponibilidade contínua com mínimo de interrupções e tempo de inatividade. | Alta | Interrupções no sistema podem causar atrasos no cumprimento de obrigações legais e prejudicar o atendimento aos clientes. | Monitoramento constante e suporte técnico, mas dependência de múltiplos fornecedores aumenta risco de indisponibilidade. | Implementar arquitetura de alta disponibilidade com redundância de servidores, monitoramento proativo 24/7, plano de contingência e SLA (Service Level Agreement) garantindo uptime mínimo de 99,5%. |
| **Manutenibilidade:** O sistema deve permitir atualizações constantes conforme mudanças na legislação tributária, trabalhista e fiscal. | Alta | A legislação brasileira sofre alterações frequentes e o sistema precisa estar sempre atualizado para manter a conformidade. | Atualizações manuais e periódicas dos sistemas, com dependência dos fornecedores. | Implementar sistema de atualização automática de regras tributárias e tabelas fiscais, com versionamento controlado e rollback em caso de problemas, além de equipe dedicada ao monitoramento de mudanças legislativas. |
| **Integração:** O sistema deve integrar-se nativamente com plataformas governamentais (eSocial, SPED, NF-e) e instituições bancárias. | Alta | A falta de integração gera retrabalho manual, aumenta o risco de erros e reduz a produtividade. | Integrações parciais ou ausentes, exigindo digitação manual de dados e uso de planilhas Excel. | Desenvolver integrações nativas e automatizadas com todos os sistemas governamentais obrigatórios e APIs bancárias, com sincronização em tempo real e tratamento de erros. |
| **Confidencialidade:** O sistema deve garantir que informações de cada cliente sejam isoladas e acessíveis apenas a usuários autorizados. | Alta | É fundamental garantir que dados de diferentes empresas não sejam acessados indevidamente. | Controles de acesso básicos e segregação de dados por empresa. | Implementar arquitetura multi-tenant com isolamento total de dados entre clientes, auditoria completa de acessos, política de privacidade rigorosa e conformidade com LGPD. |

---

# Visão geral do produto

## Visão geral

O sistema ContabSys é um sistema integrado de gestão contábil que permite que escritórios de contabilidade gerenciem todas as suas operações em um único ambiente. O sistema é composto por módulos integrados que cobrem as áreas contábil, fiscal, trabalhista e financeira, compartilhando uma base de dados centralizada.

O sistema elimina a necessidade de contratar múltiplos softwares, reduzindo custos e aumentando a eficiência operacional. Oferece ainda um portal web e aplicativo mobile para que os clientes dos escritórios possam enviar documentos digitalizados e acompanhar suas obrigações em tempo real.

A arquitetura do sistema é modular e baseada em nuvem, permitindo acesso através de navegadores web e dispositivos móveis. A integração com plataformas governamentais (eSocial, SPED, NF-e) e instituições bancárias é nativa, automatizando o envio de obrigações acessórias e a conciliação financeira.

O sistema é multiempresa, permitindo o gerenciamento de múltiplos CNPJs em um único ambiente, com relatórios individualizados e controle de acesso por perfil de usuário (administrador, contador, auxiliar contábil, setor fiscal e cliente).

Uma agenda integrada gera alertas e notificações automáticas sobre vencimentos de obrigações, prazos fiscais e tarefas pendentes, reduzindo o risco de atrasos e multas.

As regras tributárias e tabelas fiscais são atualizadas automaticamente conforme mudanças na legislação, garantindo que o sistema esteja sempre em conformidade com as exigências legais.

<img src="/diagrama-sigc.png" alt="Diagrama de Ambientes SIGC" style="max-width:100%; display:block; margin:12px 0;" />
criado por Júlio César no Inkscape

## Custo e venda

A decisão acerca da viabilidade econômica deste produto será definida pelo departamento comercial, gerente de projetos e potenciais clientes (escritórios de contabilidade). O modelo de comercialização poderá ser:

- **Licenciamento perpétuo**: Venda de licenças com valor único e manutenção anual.
- **Modelo SaaS**: Assinatura mensal ou anual por usuário ou por empresa gerenciada.
- **Modelo híbrido**: Combinação de valor inicial de implantação com mensalidade de uso.

O sistema poderá também ser comercializado como produto white label, permitindo que escritórios de contabilidade o revendam para outros escritórios.

## Licenciamento e instalação

O ContabSys poderá ser licenciado através de diferentes modalidades:

1. **Licença SaaS (Software como Serviço)**: O cliente acessa o sistema hospedado em nuvem, sem necessidade de instalação local. A empresa desenvolvedora é responsável pela infraestrutura, manutenção e atualizações.

2. **Licença On-Premise**: O cliente instala o software em seus próprios servidores, tendo controle total sobre a infraestrutura. Requer infraestrutura de TI adequada e equipe técnica para manutenção.

3. **Licença Híbrida**: Combinação de módulos em nuvem com instalação local de componentes específicos, conforme necessidade do cliente.

A instalação do software poderá ser realizada de forma autônoma pelo cliente (no modelo SaaS, apenas cadastro e configuração inicial) ou pela equipe técnica da empresa desenvolvedora, mediante contratação de serviço de implantação.

O processo de implantação incluirá:
- Configuração inicial do sistema
- Migração de dados de sistemas anteriores
- Cadastro de empresas e usuários
- Configuração de integrações bancárias e governamentais
- Treinamento da equipe
- Suporte técnico durante o período de adaptação

Após a instalação, cada usuário receberá credenciais de acesso (login e senha) de acordo com seu perfil, podendo utilizar todas as funcionalidades autorizadas.

## Características e funcionalidades de alto nível

Esta seção define e descreve as características do sistema. Trata-se dos requisitos de alto nível do sistema que são necessários para propiciar benefícios aos usuários.

1. O sistema deve permitir o cadastro de múltiplas empresas (multiempresa) com gerenciamento individualizado de cada CNPJ, incluindo dados cadastrais, regime tributário e configurações específicas.

2. O sistema deve integrar módulos contábil, fiscal, trabalhista e financeiro em uma única plataforma, compartilhando uma base de dados centralizada para eliminar retrabalho e inconsistências.

3. O sistema deve oferecer portal web e aplicativo mobile para que clientes possam enviar documentos digitalizados (notas fiscais, recibos, comprovantes), com armazenamento automático e vinculação à empresa correspondente.

4. O sistema deve integrar-se nativamente com plataformas governamentais (eSocial, SPED, NF-e) para automatizar o envio e recebimento de obrigações fiscais e trabalhistas, com validação prévia e tratamento de erros.

5. O sistema deve gerar relatórios personalizados e configuráveis por período, tipo de dado e empresa, com exportação em PDF e Excel, incluindo demonstrações contábeis, relatórios gerenciais e dashboards visuais.

6. O sistema deve disponibilizar painel interativo para clientes acompanharem em tempo real suas obrigações, documentos enviados, prazos fiscais e situação cadastral.

7. O sistema deve ter integração bancária automática para importação de extratos, geração de boletos, controle de pagamentos e conciliação bancária, com suporte a múltiplas instituições financeiras.

8. O sistema deve implementar agenda integrada que gere alertas e notificações automáticas sobre vencimentos de obrigações fiscais, trabalhistas, prazos e tarefas pendentes, com envio por e-mail e notificações push no aplicativo.

9. O sistema deve implementar controle de acesso baseado em perfis de usuário (administrador, contador, auxiliar contábil, setor fiscal e cliente), com permissões granulares e autenticação segura.

10. O sistema deve atualizar automaticamente regras tributárias, tabelas fiscais e layouts de obrigações acessórias conforme mudanças na legislação, garantindo conformidade legal permanente.

11. O sistema deve garantir segurança das informações através de criptografia de dados, backup automático, controle de acesso por perfis, auditoria de operações e conformidade com a LGPD.

12. O sistema deve ter interface intuitiva e responsiva, funcionando adequadamente em diferentes dispositivos (computadores, tablets e smartphones) e navegadores web.

13. O sistema deve processar grandes volumes de dados (lançamentos contábeis, notas fiscais, folhas de pagamento) com desempenho satisfatório e tempos de resposta rápidos.

14. O sistema deve ser desenvolvido em conformidade com normas e padrões de qualidade estabelecidos para desenvolvimento de software, com documentação técnica completa e código-fonte disponível para auditoria e manutenção.

## Restrições

Algumas possíveis restrições que podem ser aplicadas ao sistema são:

1. **Restrição de orçamento:** O projeto deve ser concluído dentro de um orçamento pré-estabelecido em comum acordo com o cliente, não podendo excedê-lo sem aprovação formal.

2. **Restrição de tempo:** O sistema deve ser desenvolvido e implementado em etapas, com prazo total não superior a um ano, com entregas quinzenais de produtos mínimos viáveis (MVP) para validação incremental.

3. **Restrições de compatibilidade:** O sistema deve funcionar nos sistemas operacionais Windows e Linux, com acesso via navegadores web modernos (Chrome, Firefox, Edge) e aplicativos para Android e iOS.

4. **Restrições de segurança e privacidade:** O sistema deve atender rigorosamente aos requisitos da Lei Geral de Proteção de Dados (LGPD), garantindo proteção, privacidade e confidencialidade de dados sensíveis dos usuários e suas empresas.

5. **Restrições de usabilidade:** O sistema deve ser acessível e de fácil utilização, com interface intuitiva que minimize a necessidade de treinamentos extensivos para novos usuários.

6. **Restrições de interoperabilidade**: O sistema deve ser capaz de integrar-se com sistemas governamentais obrigatórios (eSocial, SPED, NF-e) e APIs de instituições bancárias, seguindo os padrões e protocolos estabelecidos por estas plataformas.

7. **Restrições de desempenho**: O sistema deve atender a requisitos mínimos de desempenho, incluindo tempo de resposta de consultas inferior a 3 segundos, processamento de folha de pagamento para até 1000 funcionários em menos de 10 minutos, e disponibilidade mínima de 99,5%.

8. **Restrições de conformidade legal**: O sistema deve estar sempre atualizado com a legislação tributária, trabalhista e fiscal brasileira vigente, exigindo processo contínuo de monitoramento e atualização.

9. **Restrições geográficas e linguísticas**: O sistema deve estar preparado para operar em todo território nacional, com suporte aos fusos horários brasileiros e idioma português do Brasil. Futuramente poderá ser expandido para idiomas inglês e espanhol.

10. **Restrições tecnológicas**: O sistema não deve utilizar tecnologias proprietárias que criem dependência de fornecedores específicos, priorizando padrões abertos e arquitetura modular que facilite manutenção e evolução futura.

---

Data: 19 de outubro de 2025

**Validado por: Felipe Antonio Ramalho Macedo, Júlio César Batista de Medeiros Oliveria**

<address>
julio@empresa.com.br<br>
felipe@empresa.com.br<br>
Empresa.com<br>
João Pessoa – PB, Brasil<br>
Brasil
</address>

---
Criado em Outubro de 2025
