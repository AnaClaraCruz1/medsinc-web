# Wireframes — MEDSiNC Web

## Objetivo e método

Este documento apresenta os wireframes estruturais reconstruídos a partir da interface front-end implementada. O processo foi feito de forma reversa: primeiro foram analisadas as páginas HTML, os componentes montados por JavaScript e a organização visual definida nos arquivos CSS; em seguida, a estrutura de cada tela foi representada em baixa fidelidade.

Os desenhos registram hierarquia, distribuição dos elementos, campos, ações e navegação. Não representam medidas exatas, cores finais ou integração com serviços externos.

## Padrão de navegação das telas internas

As telas internas compartilham uma estrutura com menu lateral, identificação do sistema, área principal, cabeçalho contextual e aviso de ambiente demonstrativo. Em telas menores, a navegação passa para uma faixa horizontal e o conteúdo ocupa a largura disponível.

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ CAMINHO / MÓDULO                 [Ação]      │
│                  │ Título da página                              │
│ MENU             │ Descrição breve                               │
│                  │                                               │
│ Painel           │                                               │
│ Pacientes        │              CONTEÚDO DA TELA                 │
│ Consultas        │                                               │
│ Medicamentos     │                                               │
│ Histórico        │                                               │
│ Usuários         │                                               │
│ Relatórios       │                                               │
│ Backups          │                                               │
│                  │                                               │
│ Administração    │ Aviso: ambiente demonstrativo                 │
└──────────────────┴──────────────────────────────────────────────┘
```

## 1. Acesso — `index.html`

```text
┌──────────────────────────────────┬──────────────────────────────┐
│ MEDSiNC                           │                              │
│                                  │ BEM-VINDA(O)                  │
│ GESTÃO EM SAÚDE                  │ Acesse o MEDSiNC              │
│                                  │                              │
│ Cuidado organizado começa        │ E-mail                       │
│ com informação bem cuidada.      │ [________________________]   │
│                                  │                              │
│ Uma interface simples para      │ Senha                        │
│ apoiar a gestão de pacientes.    │ [________________________]   │
│                                  │                              │
│ Projeto Integrador · Etapa 8     │ [ Acessar demonstração → ]   │
│                                  │                              │
│                                  │ Ambiente demonstrativo       │
│                                  │ Sem autenticação real        │
└──────────────────────────────────┴──────────────────────────────┘
```

**Elementos e comportamento:** campos de e-mail e senha; botão para entrar na demonstração; validação básica de preenchimento e formato de e-mail pelo navegador; redirecionamento ao painel. Não existe autenticação real.

## 2. Painel — `dashboard.html`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ MEDSiNC / PAINEL                  [Sair]     │
│                  │ Visão geral                                   │
│ MENU PRINCIPAL   ├──────────────────────────────────────────────┤
│ Painel           │ BEM-VINDA(O) AO MEDSiNC                       │
│ Cadastrar        │ Organização para cuidar melhor.              │
│ paciente         │ Acesso aos módulos de gestão.                 │
│ Consultar        ├──────────────────────────────────────────────┤
│ pacientes        │ RESUMO — Indicadores demonstrativos           │
│ Consultas        │                                              │
│ Medicamentos     │ [Pacientes] [Novo cadastro] [Consulta]        │
│ e estoque        │                                              │
│ Histórico        ├──────────────────────────────────────────────┤
│ médico           │ [Gerenciar consultas] [Medicamentos/estoque] │
│ Usuários         │ [Histórico médico]     [Relatórios]           │
│ Relatórios       │ [Usuários e perfis]     [Backups]              │
│ Backups          │ [Cadastrar paciente]    [Consultar pacientes] │
│                  │                                              │
│ Administração    │ Aviso: demonstração front-end                │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** resumo da quantidade de pacientes no armazenamento local, atalhos para cadastro e consulta, cartões de acesso aos demais módulos e aviso de que não há conexão com banco de dados ou autenticação real.

## 3. Cadastro de paciente — `pages/cadastro-paciente.html`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ PACIENTES / CADASTRO       [Voltar ao painel]│
│                  │ Cadastro de paciente                         │
│ MENU PRINCIPAL   │ Informe os dados para incluir um registro.   │
│ Painel           ├──────────────────────────────────────────────┤
│ Cadastrar        │ DADOS PESSOAIS                                │
│ paciente         │                                              │
│ Consultar        │ Nome completo *                               │
│ pacientes        │ [________________________________________]   │
│                  │ CPF *                 Data de nascimento *   │
│                  │ [________________]    [___________________]  │
│                  │ Telefone *            E-mail                 │
│                  │ [________________]    [___________________]  │
│                  │ Endereço *                                    │
│                  │ [________________________________________]   │
│                  │ Convênio *                                    │
│                  │ [ Selecione um convênio                 v ]  │
│                  │                                              │
│                  │ [Limpar formulário]          [Salvar paciente]│
│                  │ Mensagem de validação / resultado             │
│                  │ Aviso: não inserir dados reais ou sensíveis   │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** nome, CPF, nascimento, telefone, endereço e convênio obrigatórios; e-mail opcional. O formulário aplica máscara de CPF e telefone, valida dígitos verificadores do CPF, impede CPF duplicado, rejeita nascimento futuro e valida os demais campos. O cadastro fica no armazenamento local do navegador.

## 4. Consulta de pacientes — `pages/consulta-pacientes.html`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ PACIENTES / CONSULTA        [ + Novo paciente]│
│                  │ Pacientes cadastrados                        │
│ MENU PRINCIPAL   │ Visualize e localize registros demonstrativos│
│ Painel           ├──────────────────────────────────────────────┤
│ Cadastrar        │ Pesquisar por ID, CPF ou nome                 │
│ paciente         │ [________________________________] [Limpar]  │
│ Consultar        │                                              │
│ pacientes        │ X registros encontrados      Dados demo.     │
│                  │                                              │
│                  │ ID | Nome | CPF | Nascimento | Idade          │
│                  │    | Telefone | Convênio                     │
│                  │ -------------------------------------------- │
│                  │ #1 | Nome fictício | *** | dd/mm/aaaa | ...  │
│                  │ #2 | Nome fictício | *** | dd/mm/aaaa | ...  │
│                  │                                              │
│                  │ Aviso: dados locais, sem consulta ao MySQL   │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** pesquisa dinâmica por ID, CPF ou nome; contador de resultados; botão para limpar o filtro; tabela com idade calculada automaticamente; estado vazio quando não há correspondências. A tela não consulta o banco Java/MySQL.

## 5. Consultas — `pages/modulos.html?mod=consultas`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ MEDSiNC / GESTÃO                 [Painel]    │
│                  │ Consultas                                     │
│ GESTÃO           │ Agende e acompanhe os atendimentos.           │
│ Painel           ├──────────────────────────────────────────────┤
│ Pacientes        │ NOVO REGISTRO                                 │
│ Consultas        │ Paciente *            Profissional *          │
│ Medicamentos     │ [________________]    [________________]     │
│ e estoque        │ Data *                Horário *               │
│ Histórico        │ [________________]    [________________]     │
│ médico           │ Status *                                      │
│ Usuários         │ [Agendada / Realizada / Cancelada          v] │
│ Relatórios       │ [Salvar registro]                             │
│ Backups          │                                              │
│                  │ REGISTROS                 [Filtrar registros]│
│                  │ ID | Paciente | Profissional | Data | Hora   │
│                  │ Status | Ações (Excluir)                     │
│                  │ Aviso de ambiente demonstrativo              │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** cadastro de paciente (texto), profissional, data, horário e status; listagem, filtro e exclusão com confirmação. Os dados são demonstrativos e ficam no navegador.

## 6. Medicamentos e estoque — `pages/modulos.html?mod=estoque`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ MEDSiNC / GESTÃO                 [Painel]    │
│                  │ Medicamentos e estoque                        │
│ GESTÃO           │ Controle itens, quantidades e níveis mínimos.│
│ Painel           ├──────────────────────────────────────────────┤
│ Pacientes        │ NOVO REGISTRO                                 │
│ Consultas        │ Medicamento / item *                          │
│ Medicamentos     │ [________________________________________]   │
│ e estoque        │ Quantidade atual *    Unidade de medida *    │
│ Histórico        │ [________________]    [________________]     │
│ médico           │ Estoque mínimo *                              │
│ Usuários         │ [________________]                            │
│ Relatórios       │ [Salvar registro]                             │
│ Backups          │                                              │
│                  │ REGISTROS                 [Filtrar registros]│
│                  │ ID | Item | Quantidade | Unidade | Mínimo    │
│                  │ Situação (Normal / Estoque baixo) | Excluir  │
│                  │ Aviso de ambiente demonstrativo              │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** cadastro do item, quantidade atual, unidade e estoque mínimo; filtro e exclusão; sinalização automática quando a quantidade é menor ou igual ao mínimo. Não há movimentação separada de entrada e saída nesta versão.

## 7. Histórico médico — `pages/modulos.html?mod=historico`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ MEDSiNC / GESTÃO                 [Painel]    │
│                  │ Histórico médico                              │
│ GESTÃO           │ Registros demonstrativos por paciente.        │
│ Painel           ├──────────────────────────────────────────────┤
│ Pacientes        │ NOVO REGISTRO                                 │
│ Consultas        │ Paciente *            Profissional responsável│
│ Medicamentos     │ [________________]    [________________]     │
│ e estoque        │ Data do registro *                            │
│ Histórico        │ [________________]                            │
│ médico           │ Descrição *                                   │
│ Usuários         │ [________________________________________]   │
│ Relatórios       │ [________________________________________]   │
│ Backups          │ [Salvar registro]                             │
│                  │                                              │
│                  │ REGISTROS                 [Filtrar registros]│
│                  │ ID | Paciente | Profissional | Data          │
│                  │ Descrição | Ações (Excluir)                  │
│                  │ Aviso de ambiente demonstrativo              │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** registro textual de paciente, profissional responsável, data e descrição; listagem, filtro e exclusão com confirmação. Não é prontuário eletrônico integrado nem deve receber dados clínicos reais.

## 8. Usuários e perfis — `pages/modulos.html?mod=usuarios`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ MEDSiNC / GESTÃO                 [Painel]    │
│                  │ Usuários e perfis                             │
│ GESTÃO           │ Cadastro demonstrativo de usuários.          │
│ Painel           ├──────────────────────────────────────────────┤
│ Pacientes        │ NOVO REGISTRO                                 │
│ Consultas        │ Nome *                E-mail *                │
│ Medicamentos     │ [________________]    [________________]     │
│ e estoque        │ Perfil de acesso *                           │
│ Histórico        │ [Administrador / Médico / Recepção ...    v] │
│ médico           │ Situação *                                    │
│ Usuários         │ [Ativo / Inativo                            v]│
│ Relatórios       │ [Salvar registro]                             │
│ Backups          │                                              │
│                  │ REGISTROS                 [Filtrar registros]│
│                  │ ID | Nome | E-mail | Perfil | Situação       │
│                  │ Ações (Excluir)                              │
│                  │ Aviso: não armazenar senhas                  │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** nome, e-mail, perfil (Administrador, Médico, Recepcionista, Farmacêutico ou Técnico) e situação (Ativo/Inativo); listagem, filtro e exclusão. Os perfis são apenas classificações demonstrativas, sem autorização real.

## 9. Relatórios — `pages/modulos.html?mod=relatorios`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ MEDSiNC / GESTÃO                 [Painel]    │
│                  │ Relatórios                                    │
│ GESTÃO           │ Indicadores dos dados locais da demonstração. │
│ Painel           ├──────────────────────────────────────────────┤
│ Pacientes        │                                              │
│ Consultas        │ [Total de pacientes] [Total de consultas]    │
│ Medicamentos     │ [Itens em estoque]    [Estoque baixo]        │
│ e estoque        │ [Registros de histórico]                     │
│ Histórico        │                                              │
│ médico           │ [ Imprimir / salvar em PDF ]                 │
│ Usuários         │                                              │
│ Relatórios       │ Indicadores não oficiais; dados deste        │
│ Backups          │ navegador.                                   │
│                  │                                              │
│                  │ Aviso de ambiente demonstrativo              │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** cartões com totais de pacientes, consultas, itens em estoque, itens abaixo do mínimo e registros de histórico; ação de impressão ou salvamento em PDF pelo navegador. Os indicadores são locais e demonstrativos.

## 10. Backups — `pages/modulos.html?mod=backups`

```text
┌──────────────────┬──────────────────────────────────────────────┐
│ MEDSiNC          │ MEDSiNC / GESTÃO                 [Painel]    │
│                  │ Backups                                       │
│ GESTÃO           │ Registro demonstrativo de atividades.        │
│ Painel           ├──────────────────────────────────────────────┤
│ Pacientes        │ REGISTRO DE BACKUP DEMONSTRATIVO              │
│ Consultas        │ Descrição *                                   │
│ Medicamentos     │ [________________________________________]   │
│ e estoque        │ Responsável *                                 │
│ Histórico        │ [________________________________________]   │
│ médico           │ [Registrar atividade]                         │
│ Usuários         │                                              │
│ Relatórios       │ HISTÓRICO DE ATIVIDADES                       │
│ Backups          │ • Descrição — Responsável — Data/Hora         │
│                  │ • ...                                         │
│                  │                                              │
│                  │ Aviso: não gera cópia real de banco de dados  │
└──────────────────┴──────────────────────────────────────────────┘
```

**Elementos e comportamento:** formulário para registrar uma atividade simulada e lista cronológica com descrição, responsável e data/hora. Não cria, exporta ou restaura cópias de segurança.

## Regras visuais e responsividade

- Identidade visual baseada em azul profundo, verde/azulado, superfícies claras e cartões com cantos arredondados.
- Tipografia principal DM Sans, com títulos em Manrope.
- Menu lateral fixo em telas amplas; navegação horizontal em telas pequenas.
- Formulários em duas colunas quando há espaço, reorganizados em uma coluna em dispositivos menores.
- Tabelas dentro de áreas com rolagem horizontal quando necessário.
- Botões e campos com estados de foco e mensagens de retorno.

## Limites funcionais representados

- Aplicação front-end em HTML, CSS e JavaScript.
- Dados fictícios e registros inseridos pelo usuário são armazenados no navegador por meio de `localStorage`.
- O acesso é demonstrativo e não autentica usuários.
- Não existe integração ativa com API, Java ou MySQL.
- Não há controle real de permissões, prontuário seguro, trilha de auditoria ou backup de banco.
- Não inserir dados pessoais, CPFs reais, informações clínicas ou credenciais.

## Arquivos relacionados

- `index.html` — acesso demonstrativo.
- `dashboard.html` — painel principal.
- `pages/cadastro-paciente.html` — cadastro de pacientes.
- `pages/consulta-pacientes.html` — consulta de pacientes.
- `pages/modulos.html` — estrutura compartilhada dos módulos complementares.
- `assets/css/styles.css` e `assets/css/modules.css` — apresentação visual e responsividade.
- `assets/js/app.js` e `assets/js/modules.js` — interações e armazenamento local.
