# MEDSiNC Web

Aplicação front-end do MEDSiNC, sistema de gestão em saúde desenvolvido com HTML5, CSS3 e JavaScript.

## Módulos
- **Painel:** visão geral e atalhos para os módulos.
- **Pacientes:** cadastro e consulta por ID, CPF ou nome, com validações de identificação.
- **Consultas:** cadastro, listagem, filtro e controle de status (agendada, realizada ou cancelada).
- **Medicamentos e estoque:** cadastro de itens, quantidades, unidades, níveis mínimos e alerta de estoque baixo.
- **Histórico médico:** registros por paciente, profissional, data e descrição.
- **Usuários e perfis:** cadastro demonstrativo de usuários com perfis funcionais.
- **Relatórios:** indicadores calculados com base nos registros locais e opção de impressão/salvamento em PDF.
- **Backups:** registro demonstrativo de atividades; não executa cópia real de banco de dados.

## Como executar
1. Baixe ou extraia o repositório.
2. Abra `index.html` em um navegador moderno.
3. Informe um e-mail e uma senha quaisquer para entrar no ambiente demonstrativo.
4. Utilize a navegação lateral para acessar os módulos.

Não é necessário instalar dependências ou configurar banco de dados para esta demonstração.

## Recursos de qualidade
- Layout responsivo e navegação consistente.
- Formulários com campos obrigatórios e validações.
- Pesquisa e filtros nos módulos com listagens.
- Confirmação antes de excluir registros.
- Escape de conteúdo dinâmico antes de exibir dados na tabela.
- Identificação automática de registros e alertas para estoque mínimo.
- Tratamento de falhas do armazenamento local.
- Indicadores e impressão de relatórios.

## Armazenamento e segurança
Os registros dos módulos são armazenados no `localStorage` do navegador. Os dados de pacientes usam armazenamento local próprio; os demais módulos usam uma área de demonstração separada. Os dados não são sincronizados entre computadores ou usuários e podem ser apagados pelo navegador.

**Não utilize dados pessoais reais, CPFs reais, prontuários, informações clínicas ou credenciais.** O login é apenas uma passagem demonstrativa: não autentica, não protege páginas e não implementa autorização real por perfil. O armazenamento local não é criptografado e não é apropriado para dados sensíveis.

Uma implantação real exige API e servidor, autenticação segura, senhas armazenadas com hash forte, autorização no back-end, HTTPS, validação no servidor, banco de dados protegido, trilhas de auditoria e controles adequados à LGPD. Backups reais também devem ser executados e verificados no servidor.

## Arquitetura atual
Esta entrega é uma aplicação front-end independente. Não existe integração ativa com o projeto Java, MySQL ou qualquer API. A separação permite evoluir a interface sem alterar o sistema Java existente.

## Tecnologias
HTML5 · CSS3 · JavaScript vanilla · Web Storage API
