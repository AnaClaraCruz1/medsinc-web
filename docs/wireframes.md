# Wireframes — MEDSiNC Web

Wireframes estruturais iniciais da Etapa 8. A identidade visual final é aplicada em CSS.

## 1. Acesso — index.html
```
┌──────────────────────────────────────────────────────┐
│ MEDSiNC                                  ACESSO       │
│                                                      │
│              [ símbolo / identificação ]             │
│           Gestão integrada de pacientes              │
│                                                      │
│              E-mail [________________]               │
│              Senha  [________________]               │
│                     [ Entrar ]                       │
│                                                      │
│       Demonstração acadêmica — sem autenticação      │
└──────────────────────────────────────────────────────┘
```

## 2. Painel — dashboard.html
```
┌───────────────┬──────────────────────────────────────┐
│ MEDSiNC       │ Visão geral                          │
│               │                                      │
│ Painel        │ [ Pacientes cadastrados ] [ Ações ]  │
│ Cadastrar     │                                      │
│ Consultar     │ [ Atalho: novo paciente ]            │
│               │ [ Atalho: consultar pacientes ]      │
│               │                                      │
│               │ Aviso: dados demonstrativos          │
└───────────────┴──────────────────────────────────────┘
```

## 3. Cadastro — pages/cadastro-paciente.html
```
┌───────────────┬──────────────────────────────────────┐
│ Navegação     │ Cadastro de paciente                │
│               │ Nome completo     CPF                │
│               │ Data nascimento  Telefone            │
│               │ Endereço                              │
│               │ E-mail (opcional) Convênio            │
│               │ [ Limpar ]              [ Salvar ]   │
└───────────────┴──────────────────────────────────────┘
```

## 4. Consulta — pages/consulta-pacientes.html
```
┌───────────────┬──────────────────────────────────────┐
│ Navegação     │ Pacientes cadastrados                │
│               │ Pesquisar por ID, CPF ou nome        │
│               │ [____________________] [Limpar]      │
│               │                                      │
│               │ ID | Nome | CPF | Nascimento | Idade | Telefone | Convênio   │
│               │ ...                                  │
└───────────────┴──────────────────────────────────────┘
```

## Melhorias incorporadas
- Identificador sequencial para cada registro demonstrativo.
- Exibição da data de nascimento e cálculo automático da idade na consulta.
- Validação do CPF e prevenção de duplicidade na base local.
- Tratamento de falhas no armazenamento do navegador e escape de conteúdo exibido.
- Avisos explícitos para não utilizar dados pessoais reais.

## Observação
Os desenhos representam a organização e hierarquia das telas, não medidas finais. O front-end usa registros fictícios no navegador e não substitui a persistência Java/MySQL.
