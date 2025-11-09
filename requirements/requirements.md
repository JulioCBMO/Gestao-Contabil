# Capa

---

<h1>Requisitos de Software</h1>

<h2>ContabSys</h2>

<small>Versão 1.0</small>

---

## Histórico de revisões

|    Data    | Versão |          Descrição          |      Autor       |
| :--------: | :----: | :-------------------------: | :--------------: |
| 09/11/2025 |  1.0   |    Criação do documento     | Júlio, Felipe |

---

## Sumário

- [Capa](#capa)
  - [Histórico de revisões](#histórico-de-revisões)
  - [Sumário](#sumário)
- [Introdução](#introdução)
  - [Definições, Acrônimos e Abreviações](#definições-acrônimos-e-abreviações)
- [Usuários identificados](#usuários-identificados)
- [Requisitos funcionais](#requisitos-funcionais)
- [Requisitos não-funcionais](#requisitos-não-funcionais)
  - [Disponibilidade](#disponibilidade)
  - [Privacidade e segurança](#privacidade-e-segurança)
  - [Usabilidade](#usabilidade)
  - [Suportabilidade](#suportabilidade)
  - [Interoperabilidade](#interoperabilidade)
  - [Manutenibilidade](#manutenibilidade)
  - [Desempenho](#desempenho)
  - [Implementação](#implementação)
  - [Implantação](#implantação)
  - [Conformidade Legal](#conformidade-legal)
  - [Internacionalização](#internacionalização)
  - [Qualidade](#qualidade)
- [Matriz de rastreabilidade](#matriz-de-rastreabilidade)
  - [Rastreabilidade entre RFs e RNFs](#rastreabilidade-entre-rfs-e-rnfs)

---

# Introdução

O objetivo deste documento é apresentar os requisitos de software do produto **ContabSys**.

## Definições, Acrônimos e Abreviações

Esta subseção fornece as definições de todos os termos, acrônimos e abreviações necessárias à adequada interpretação do Documento de Requisitos.

- Identificação dos requisitos: por convenção, a referência a requisitos é feita através do identificador de requisitos, de acordo como descrito abaixo:

  `[IDENTIFICADOR DO TIPO DE REQUISITOS identificador do requisito]`

  O identificador do tipo de requisitos é conforme abaixo:

  - RF – Requisito Funcional
  - RNF – Requisito Não-Funcional
  - NR – Não-Requisito

  O identificador do requisito será uma sequência numérica. Esse número sequencial será único para todo o conjunto de tipos de requisitos.

  **Exemplo**: RF0001, RF1234, RNF1234, NR1212

- Atributos dos Requisitos: os atributos de requisitos estabelecidos são:
  - **Requisitos vinculados**: fornece uma lista dos requisitos que mantém rastreabilidade.
  - **Prioridade**: Essencial, Importante, Desejável
  - **Complexidade**: Complexa, Alta, Média ou Baixa.
  - **Risco**: Alto, Médio, Baixo

- Definições e Acrônimos:

| Termo/Acrônimo | Definição |
| :------------: | --------- |
| SIGC | Sistema Integrado de Gestão Contábil |
| eSocial | Sistema de Escrituração Digital das Obrigações Fiscais, Previdenciárias e Trabalhistas |
| SPED | Sistema Público de Escrituração Digital |
| NF-e | Nota Fiscal Eletrônica |
| LGPD | Lei Geral de Proteção de Dados |
| CNPJ | Cadastro Nacional da Pessoa Jurídica |
| API | Application Programming Interface (Interface de Programação de Aplicações) |
| SSL/TLS | Secure Sockets Layer / Transport Layer Security |
| MVP | Minimum Viable Product (Produto Mínimo Viável) |
| WCAG | Web Content Accessibility Guidelines |
| REST | Representational State Transfer |
| SLA | Service Level Agreement |

# Usuários identificados

Os seguintes usuários foram identificados para o sistema:

- **Usuários do sistema**
  - **Usuários internos do escritório contábil**
    - Contador
    - Auxiliar Contábil
    - Setor Fiscal
    - Administrador do sistema
  - **Usuários externos**
    - Cliente (empresa que utiliza os serviços do escritório contábil)
    - Colaborador do cliente (funcionário autorizado a enviar documentos)
  - **Usuários de suporte**
    - Suporte técnico
    - Gerente de projetos

# Requisitos funcionais

Os requisitos funcionais são descritos a seguir.




# Requisitos não-funcionais

Os requisitos não-funcionais são descritos a seguir.

## Disponibilidade

- **[RNF001]** - O sistema deve estar disponível 24 horas por dia, 7 dias por semana, com disponibilidade mínima de 99,5% (uptime).
- **[RNF002]** - O sistema deve ser desenvolvido de forma que possa ser implantado em qualquer plataforma de servidores atualizada (Windows Server, Linux).
- **[RNF003]** - O sistema deve ser desenvolvido de forma que possa ser escalável, ou seja, deve ser possível aumentar a capacidade de armazenamento de dados e de processamento de requisições sem que haja perda de desempenho.
- **[RNF004]** - O sistema deve implementar arquitetura de alta disponibilidade com redundância de servidores para garantir continuidade operacional.
- **[RNF005]** - O sistema deve implementar monitoramento proativo 24/7 para identificar e corrigir problemas antes que afetem os usuários.

## Privacidade e segurança

- **[RNF006]** - O sistema deve atender rigorosamente aos requisitos da Lei Geral de Proteção de Dados (LGPD), garantindo proteção, privacidade e confidencialidade de dados sensíveis dos usuários.
- **[RNF007]** - O sistema deve implementar criptografia de dados sensíveis (informações fiscais, financeiras e pessoais) tanto em trânsito quanto em repouso.
- **[RNF008]** - O sistema deve implementar certificados SSL/TLS para todas as comunicações via internet.
- **[RNF009]** - O sistema deve implementar controle de acesso baseado em perfis de usuário (administrador, contador, auxiliar contábil, setor fiscal e cliente), com permissões granulares.
- **[RNF010]** - O sistema deve implementar autenticação de dois fatores para aumentar a segurança de acesso.
- **[RNF011]** - O sistema deve realizar backup automático dos dados com redundância geográfica, garantindo recuperação em caso de falhas.
- **[RNF012]** - O sistema deve implementar auditoria completa de acessos e operações, registrando quem, quando e o que foi alterado.
- **[RNF013]** - O sistema deve implementar arquitetura multi-tenant com isolamento total de dados entre diferentes escritórios contábeis.
- **[RNF014]** - O sistema deve proteger senhas de usuários utilizando algoritmos de hash seguros.

## Usabilidade

- **[RNF015]** - O sistema deve ter interface intuitiva e de fácil aprendizado, minimizando a necessidade de treinamentos extensivos para novos usuários.
- **[RNF016]** - O sistema deve ter interface responsiva, funcionando adequadamente em diferentes dispositivos (computadores, tablets e smartphones).
- **[RNF017]** - O sistema deve disponibilizar dashboards visuais com gráficos e indicadores para facilitar a tomada de decisão.
- **[RNF018]** - O sistema deve ser acessível para pessoas com deficiências visuais e motoras, seguindo as diretrizes WCAG 2.1.
- **[RNF019]** - O sistema deve implementar sistema de ajuda contextual e tooltips para orientar os usuários nas funcionalidades.
- **[RNF020]** - O sistema deve ter navegação simplificada e organizada, com estrutura de menus clara e lógica.

## Suportabilidade

- **[RNF021]** - O sistema deve ser desenvolvido de forma que possa ser executado nos principais navegadores web: Google Chrome, Safari, Mozilla Firefox e Microsoft Edge em suas versões atualizadas.
- **[RNF022]** - O sistema deve ser desenvolvido de forma que possa ser executado em computadores com sistema operacional Windows, MacOs ou Linux.
- **[RNF023]** - O sistema deve disponibilizar aplicativo mobile nativo para os sistemas operacionais Android e iOS.
- **[RNF024]** - O sistema deve ser compatível com diferentes resoluções de tela, desde smartphones até monitores widescreen.

## Interoperabilidade

- **[RNF025]** - O sistema deve integrar-se nativamente com a plataforma eSocial para envio e recebimento de informações trabalhistas de forma automatizada.
- **[RNF026]** - O sistema deve integrar-se nativamente com o SPED (Sistema Público de Escrituração Digital) para envio de obrigações fiscais.
- **[RNF027]** - O sistema deve integrar-se nativamente com o sistema de NF-e (Nota Fiscal Eletrônica) para emissão e importação de notas fiscais.
- **[RNF028]** - O sistema deve integrar-se com APIs de instituições bancárias para importação automática de extratos bancários.
- **[RNF029]** - O sistema deve integrar-se com APIs de instituições bancárias para geração e controle de boletos de pagamento.
- **[RNF030]** - O sistema deve implementar APIs RESTful para permitir integração com outros sistemas externos.

## Manutenibilidade

- **[RNF031]** - O sistema deve ser desenvolvido de forma modular, facilitando manutenção e evolução de funcionalidades específicas.
- **[RNF032]** - O sistema deve ser documentado de forma completa, incluindo documentação técnica, manual de usuário e guia de instalação.
- **[RNF033]** - O sistema deve ter código-fonte disponível para auditoria e manutenção futura.
- **[RNF034]** - O sistema deve implementar atualização automática de regras tributárias e tabelas fiscais conforme mudanças na legislação.
- **[RNF035]** - O sistema deve ser desenvolvido de forma que atualizações possam ser realizadas sem interrupção do serviço (zero downtime deployment).
- **[RNF036]** - O sistema deve implementar versionamento controlado com possibilidade de rollback em caso de problemas nas atualizações.
- **[RNF037]** - O sistema deve ser desenvolvido de forma que possa ser facilmente testado e validado, tanto de forma manual quanto automatizada.

## Desempenho

- **[RNF038]** - O sistema deve ter tempo de resposta inferior a 3 segundos para consultas e operações simples.
- **[RNF039]** - O sistema deve ser capaz de processar folha de pagamento para até 1000 funcionários em menos de 10 minutos.
- **[RNF040]** - O sistema deve ser capaz de gerar relatórios gerenciais em menos de 5 segundos para períodos de até 12 meses.
- **[RNF041]** - O sistema deve ser capaz de lidar com grandes volumes de dados (múltiplos clientes, notas fiscais, lançamentos contábeis) sem degradação de performance.
- **[RNF042]** - O sistema deve ser capaz de processar importação de extratos bancários com até 10.000 lançamentos em menos de 2 minutos.
- **[RNF043]** - O sistema deve implementar cache de dados para melhorar o desempenho de consultas frequentes.
- **[RNF044]** - O sistema deve otimizar consultas ao banco de dados para garantir respostas rápidas mesmo com grande volume de informações.

## Implementação

- **[RNF045]** - O sistema deve ser desenvolvido seguindo padrões e boas práticas de engenharia de software.
- **[RNF046]** - O sistema deve ser desenvolvido utilizando arquitetura modular e integrada, com módulos distintos para áreas contábil, fiscal, trabalhista e financeira.
- **[RNF047]** - O sistema deve utilizar uma base de dados centralizada compartilhada por todos os módulos.
- **[RNF048]** - O sistema deve ser desenvolvido com APIs de acesso aos dados para permitir integração com sistemas externos.
- **[RNF049]** - O sistema deve implementar tratamento de erros com mensagens claras e informativas para os usuários.
- **[RNF050]** - O sistema deve implementar logs detalhados de operações para facilitar diagnóstico de problemas.

## Implantação

- **[RNF051]** - O sistema deve ser desenvolvido de forma que possa ser implantado em ambiente de nuvem (cloud) ou em servidores locais (on-premise).
- **[RNF052]** - O sistema deve ser desenvolvido de forma que possa ser implantado em plataformas de hardware x64 e ARM64, com arquitetura mínima de 64 bits.
- **[RNF053]** - O sistema deve incluir guia de instalação detalhado com todos os pré-requisitos de hardware e software necessários.
- **[RNF054]** - O sistema deve incluir processo de migração de dados de sistemas anteriores (Domínio, Alterdata, Fortes, etc.).
- **[RNF055]** - O sistema deve incluir processo de configuração inicial assistido (wizard) para facilitar a implantação.
- **[RNF056]** - O sistema deve incluir ferramentas de verificação de requisitos mínimos de hardware e software antes da instalação.

## Conformidade Legal

- **[RNF057]** - O sistema deve estar sempre atualizado com a legislação tributária brasileira vigente.
- **[RNF058]** - O sistema deve estar sempre atualizado com a legislação trabalhista brasileira vigente.
- **[RNF059]** - O sistema deve estar sempre atualizado com a legislação fiscal brasileira vigente.
- **[RNF060]** - O sistema deve implementar processo contínuo de monitoramento de mudanças legislativas.
- **[RNF061]** - O sistema deve validar cálculos tributários e trabalhistas conforme as regras estabelecidas pela Receita Federal e Ministério do Trabalho.

## Internacionalização

- **[RNF062]** - O sistema deve ser desenvolvido de forma que possa ser traduzido para outros idiomas, priorizando português do Brasil, inglês e espanhol.
- **[RNF063]** - O sistema deve ser compatível com diferentes fusos horários brasileiros.
- **[RNF064]** - O sistema deve apresentar datas, valores monetários e números conforme o padrão brasileiro (formato de data dd/mm/aaaa, separador decimal vírgula).

## Qualidade

- **[RNF065]** - O sistema deve ser desenvolvido em conformidade com normas e padrões de qualidade estabelecidos para desenvolvimento de software.
- **[RNF066]** - O sistema deve implementar testes automatizados para garantir qualidade e identificar erros precocemente.
- **[RNF067]** - O sistema deve passar por processos de garantia de qualidade incluindo testes unitários, testes de integração e testes de aceitação.
- **[RNF068]** - O sistema deve garantir estabilidade e confiabilidade nos cálculos contábeis, fiscais e trabalhistas.
- **[RNF069]** - O sistema deve implementar validações de dados em todas as entradas de informação para evitar inconsistências.
- **[RNF070]** - O sistema deve ter taxa de erros inferior a 0,1% nas operações críticas (cálculos tributários, folha de pagamento, lançamentos contábeis).
