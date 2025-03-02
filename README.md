# Sistema de Gerenciamento de Estoque

Este é um sistema de gerenciamento de estoque desenvolvido em C# utilizando **Windows Forms**, **SQLite** como banco de dados e **Git** para controle de versão. O sistema permite o cadastro, remoção e alteração de produtos no estoque, registro de vendas e geração de relatórios, com diferentes perfis de usuário (Admin e Vendedor).

## Objetivo do Projeto

Desenvolver uma aplicação desktop para gerenciar o estoque de uma loja, permitindo o cadastro de produtos, controle de vendas, relatórios, e a diferenciação de perfis de usuário (Admin e Vendedor).

## Funcionalidades

### Cadastro de Produtos
- O administrador pode cadastrar produtos com os seguintes campos:
  - Nome do Produto
  - Código do Produto (único)
  - Preço
  - Quantidade em Estoque

### Remoção de Produtos
- O administrador pode remover produtos do estoque.

### Alteração de Produtos
- O administrador pode alterar o preço e a quantidade em estoque dos produtos.

### Perfis de Usuário
- **Admin**: Acesso total ao sistema (cadastrar, remover, alterar produtos, e ver relatórios de vendas).
- **Vendedor**: Pode registrar vendas e visualizar o estoque.

### Registro de Vendas
- O vendedor pode registrar uma venda, informando o CPF e nome do cliente, o produto vendido e a quantidade. O estoque será atualizado automaticamente.

### Relatórios de Vendas
- O sistema permite a geração de relatórios de vendas realizadas, com informações como CPF do cliente, produto, quantidade e valor.

## Tecnologias Utilizadas

- **Linguagem**: C# (.NET Framework)
- **Banco de Dados**: SQLite
- **IDE**: Visual Studio
- **Versionamento**: Git/GitHub
- **Interface Gráfica**: Windows Forms

## Estrutura do Banco de Dados

O banco de dados SQLite é composto pelas seguintes tabelas:

### Produtos
- `Id` (INTEGER, PRIMARY KEY, AUTOINCREMENT)
- `Nome` (TEXT)
- `Codigo` (TEXT, UNIQUE)
- `Preco` (REAL)
- `Quantidade` (INTEGER)

### Usuarios
- `Id` (INTEGER, PRIMARY KEY, AUTOINCREMENT)
- `Nome` (TEXT)
- `Perfil` (TEXT) - Valores possíveis: "Admin", "Vendedor"
- `Senha` (TEXT)

### Pedidos
- `Id` (INTEGER, PRIMARY KEY, AUTOINCREMENT)
- `ClienteCPF` (TEXT)
- `ClienteNome` (TEXT)
- `ProdutoId` (INTEGER, FOREIGN KEY para Produtos)
- `QuantidadeVendida` (INTEGER)
- `Valor` (REAL)

## Como Rodar o Projeto

### Pré-requisitos

- Visual Studio (com suporte a C# e .NET Framework)
- Banco de dados SQLite (o projeto já inclui a configuração do banco)
- Pacote NuGet **System.Data.SQLite** instalado.

### Passos para Execução

1. Clone o repositório para sua máquina local:
   ```bash
   git clone https://github.com/seuusuario/gerenciamento-estoque.git

2.Abra o projeto no Visual Studio.

3.Execute o projeto no Visual Studio pressionando F5 ou clicando em Iniciar.

4.O banco de dados será criado automaticamente na primeira execução. Caso contrário, ele pode ser criado manualmente com os scripts de criação de tabelas.

5.Faça o login com um usuário administrador ou vendedor e comece a utilizar o sistema.

```bash
gerenciamento-estoque/
│
├── BancoDeDados/
│   └── estoque.db               # Banco de dados SQLite
│
├── FormularioLogin/
│   └── FormLogin.cs             # Formulário de Login
│
├── FormularioPrincipal/
│   └── FormPrincipal.cs         # Tela Principal
│
├── Produtos/
│   └── Produto.cs               # Classe Produto
│
├── Pedidos/
│   └── Pedido.cs                # Classe Pedido
│
├── Usuarios/
│   └── Usuario.cs               # Classe Usuario
│
├── ConexaoBanco/
│   └── ConexaoSQLite.cs         # Conexão com o Banco de Dados
│
├── Program.cs                   # Ponto de entrada do aplicativo
└── README.md                    # Este arquivo
```
