# Plano de evolução — MEDSiNC Web

## Diretriz do projeto
A versão Web é a continuidade do MEDSiNC autoral, desenvolvido originalmente em Java Swing, JDBC e MySQL. Ela não será limitada às telas mínimas do enunciado: manterá os módulos do sistema original e incorporará melhorias de experiência, organização e segurança.

## Referência funcional do sistema original
O projeto Java original contém telas de login, menu, pacientes, consultas, estoque e histórico médico. O esquema SQL também prevê usuários, relatórios e backups.

## Escopo funcional da versão Web

| Módulo | Funcionalidades previstas |
|---|---|
| Acesso e usuários | Login demonstrativo na etapa front-end; gestão de usuários, perfis e permissões planejadas para integração futura com servidor. |
| Painel | Indicadores, atalhos, alertas de estoque mínimo e visão resumida das atividades. |
| Pacientes | Cadastro, consulta, edição, exclusão controlada e identificação; manter os campos exigidos no requisito revisado e documentar a diferença em relação ao modelo Java legado. |
| Consultas | Agendamento, listagem, pesquisa, alteração de status (agendada, realizada, cancelada) e associação com paciente e profissional. |
| Estoque | Cadastro e manutenção de itens, quantidade, unidade de medida, quantidade mínima, entradas/saídas e alertas de estoque baixo. |
| Histórico médico | Registro cronológico por paciente, profissional responsável, data e descrição; acesso visual restrito por perfil na arquitetura futura. |
| Relatórios | Visões de atividades e desempenho, filtros por período e exportação/impressão no navegador quando viável. |
| Backups | Área de orientação e histórico demonstrativo; geração/restauração real de backup depende de servidor e banco, não do navegador isolado. |

## Melhorias planejadas
- Navegação consistente entre módulos e layout responsivo.
- Componentes e estilos compartilhados para reduzir duplicação.
- Validação de formulários e mensagens acessíveis.
- Pesquisa, filtros, ordenação e estados vazios.
- Confirmação antes de ações destrutivas e trilha visual de alterações quando aplicável.
- Controle de acesso preparado por perfil, sem simular segurança real no cliente.
- Proteção contra injeção de HTML ao renderizar dados.
- Dados fictícios claramente identificados durante a demonstração.

## Limites técnicos e segurança
A etapa atual é front-end estático. Dados no `localStorage` são apenas demonstrativos, não criptografados e não adequados para prontuários ou dados pessoais reais. Login, permissões, auditoria confiável, backups e persistência compartilhada exigem API e servidor. A versão de produção deverá usar HTTPS, autenticação no servidor, senhas com hash forte, autorização por perfil, validação no servidor, banco protegido, registros de auditoria e controles compatíveis com a LGPD.

A autenticação legada do Java é compatível com senhas em texto simples. A versão Web não deve reproduzir essa prática nem armazenar credenciais reais no navegador.

## Estratégia de implementação
1. Consolidar a arquitetura visual, navegação e componentes compartilhados.
2. Implementar módulos operacionais com dados fictícios e persistência local apenas para demonstração.
3. Validar os fluxos completos, estados de erro, acessibilidade e responsividade.
4. Atualizar wireframes, README e documentação de evolução.
5. Preparar a arquitetura para futura API, sem declarar integração inexistente com Java/MySQL.

## Compatibilidade com os requisitos acadêmicos
Os requisitos específicos da Etapa 8 continuam atendidos e preservados. As funcionalidades adicionais representam evolução autoral do MEDSiNC e serão identificadas como melhorias incrementais, não como exigências atribuídas ao professor.
