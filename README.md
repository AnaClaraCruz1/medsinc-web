# MEDSiNC Web — Etapa 8

Interface web acadêmica do sistema MEDSiNC, desenvolvida separadamente do projeto Java.

## Objetivo
Planejar e implementar uma interface responsiva com HTML5, CSS3 e JavaScript, seguindo os requisitos revisados de cadastro e consulta de pacientes.

## Estrutura
```
medsinc-web/
├── index.html
├── dashboard.html
├── pages/
│   ├── cadastro-paciente.html
│   └── consulta-pacientes.html
├── assets/
│   ├── css/styles.css
│   └── js/app.js
└── docs/
    └── wireframes.md
```

## Escopo desta versão
- Tela de acesso demonstrativa (sem autenticação real).
- Painel inicial e navegação entre as telas.
- Cadastro demonstrativo de pacientes com validação de campos.
- Consulta com filtro por ID, CPF ou nome e ação para limpar o filtro.
- Dados fictícios armazenados apenas no navegador (localStorage).

## Relação com o projeto Java
O repositório Java `medsinc-refatorado` separa domínio, serviços e repositórios. O modelo Java atual de `Paciente` contém ID, nome, idade, endereço, contato e usuário responsável pelo cadastro. O documento de requisitos revisado, por sua vez, prevê CPF, data de nascimento e convênio, atributos que não estão presentes no modelo Java/SQL legado descrito no relatório da Etapa 6.

Por isso, esta etapa mantém a interface alinhada aos requisitos revisados sem alterar nem afirmar integração com o back-end Java. A diferença entre o modelo legado e os requisitos será registrada para transparência acadêmica. Nenhum dado real de paciente deve ser utilizado.

## Melhorias de segurança e identificação
- Identificador sequencial local exibido como ID do registro.
- CPF com máscara, validação dos dígitos verificadores e bloqueio de duplicidade na lista local.
- Data de nascimento exibida em formato brasileiro e idade calculada automaticamente para facilitar a identificação, sem armazenar uma idade desatualizada.
- Conteúdo dinâmico escapado antes de ser inserido na tabela, reduzindo o risco de interpretação de texto cadastrado como HTML.
- Tratamento de falhas de leitura/gravação do armazenamento local, com aviso quando o cadastro permanecer somente na sessão.
- Validação dos dados recuperados do armazenamento antes de utilizá-los.

**Limite de segurança:** essas medidas são validações de interface, não proteção de dados em produção. O `localStorage` não é criptografado e pode ser acessado por quem utiliza o mesmo perfil do navegador. Não inserir dados reais, CPF real, informações clínicas ou credenciais. Uma versão de produção exigiria autenticação, autorização por perfil, HTTPS, API e armazenamento protegido no servidor, além de adequação à LGPD.

## Como executar
Abra `index.html` em um navegador moderno. Não é necessário instalar dependências ou configurar banco de dados.

## Limitações
Esta é uma demonstração front-end. O login não autentica usuários, os convênios são opções ilustrativas e os dados são locais ao navegador. Não há API, servidor ou conexão com MySQL.

## Etapa acadêmica
Projeto desenvolvido para a Etapa 8 do Projeto Integrador: wireframes, páginas HTML, estilização CSS e validações/funcionalidades JavaScript.
