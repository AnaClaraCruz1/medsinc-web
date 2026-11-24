# MEDSiNC Web

Aplicação web demonstrativa para gestão integrada de informações de saúde, desenvolvida como parte do Projeto Integrador — Etapa 8.

**Autoria:** Ana Clara Cruz

## Visão geral

O MEDSiNC Web apresenta uma interface responsiva para organizar rotinas administrativas de um ambiente de saúde. A aplicação reúne os módulos de painel, pacientes, consultas, medicamentos e estoque, histórico médico, usuários, relatórios e registro demonstrativo de backups.

Este repositório contém uma implementação front-end independente, construída com HTML5, CSS3 e JavaScript. Não depende de instalação de pacotes ou de um servidor de aplicação para executar a demonstração.

## Funcionalidades

- **Acesso demonstrativo:** formulário de entrada que direciona ao painel. Não realiza autenticação nem valida credenciais.
- **Painel:** visão geral e atalhos para os módulos.
- **Pacientes:** cadastro com validação dos campos, formatação de CPF e telefone, prevenção de CPF duplicado (sem validação matemática dos dígitos, permitindo CPFs fictícios nos testes) e consulta por ID, CPF ou nome.
- **Consultas:** cadastro, listagem, filtro e acompanhamento de status.
- **Medicamentos e estoque:** cadastro de itens, quantidades, unidades, níveis mínimos e sinalização de estoque baixo.
- **Histórico médico:** registro demonstrativo de informações associadas a pacientes.
- **Usuários e perfis:** cadastro ilustrativo de usuários e perfis, sem controle real de permissões.
- **Relatórios:** indicadores calculados a partir dos registros locais e opção de impressão ou salvamento em PDF pelo navegador.
- **Backups:** histórico demonstrativo de atividades; não gera cópias reais de banco de dados.

## Protótipo visual

As telas da Etapa 8 estão documentadas no Figma, organizadas em uma página e agrupadas por área funcional: acesso e painel, gestão de pacientes e módulos administrativos.

[Visualizar o projeto MEDSiNC no Figma](https://www.figma.com/design/4e4KWfnlretIXu1XjbmKBz)

## Tecnologias

- HTML5
- CSS3
- JavaScript (vanilla)
- Web Storage API (localStorage)

## Estrutura do projeto

    medsinc-web/
    ├── index.html
    ├── dashboard.html
    ├── pages/
    │   ├── cadastro-paciente.html
    │   ├── consulta-pacientes.html
    │   └── modulos.html
    └── assets/
        ├── css/
        │   ├── styles.css
        │   └── modules.css
        └── js/
            ├── app.js
            └── modules.js

Os módulos administrativos compartilham a página pages/modulos.html e são selecionados pelo parâmetro mod da URL.

## Como executar

1. Faça o download ou clone este repositório.
2. Abra a pasta do projeto.
3. Inicie a aplicação abrindo index.html em um navegador moderno. Para uma experiência local consistente, também é possível utilizar a extensão Live Server do Visual Studio Code.
4. Na tela de acesso, informe um endereço de e-mail válido no formato e qualquer senha não vazia para entrar na demonstração.
5. Utilize o menu lateral e os atalhos do painel para navegar pelos módulos.

Não é necessário instalar dependências nem configurar banco de dados.

## Armazenamento e limitações

Os dados desta versão são armazenados no localStorage do próprio navegador. Isso significa que:

- os registros ficam restritos ao navegador e ao dispositivo utilizados;
- não há sincronização entre computadores ou usuários;
- os dados podem ser removidos ao limpar os dados de navegação;
- o armazenamento local não oferece criptografia ou proteção adequada para informações sensíveis.

O acesso é apenas demonstrativo. Não existe autenticação real, gerenciamento efetivo de sessões ou autorização de acesso por perfil. A aplicação também não possui API, integração ativa com MySQL ou conexão com o sistema Java.

**Utilize exclusivamente dados fictícios. Não insira nomes, CPFs, contatos, prontuários, informações clínicas ou credenciais reais.**

## Considerações para uma implantação real

Para uso em ambiente produtivo, será necessário implementar, no mínimo:

- API e serviços no back-end;
- autenticação segura e gerenciamento de sessão;
- armazenamento de senhas com hash apropriado;
- autorização e validação no servidor;
- banco de dados protegido e controle de acesso;
- comunicação HTTPS;
- trilhas de auditoria e política de retenção;
- rotinas de backup, restauração e verificação;
- medidas técnicas e organizacionais compatíveis com a LGPD.

Os módulos de relatórios e backups desta versão têm finalidade exclusivamente demonstrativa.

## Autoria

Projeto desenvolvido por **Ana Clara Cruz** como atividade acadêmica do Projeto Integrador — Etapa 8.
