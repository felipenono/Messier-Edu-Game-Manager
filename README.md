# Messier-Edu-Game-Manager
Sistema Desktop para Gestão de Assinaturas de Jogos Educacionais

> **Projeto Interdisciplinar** desenvolvido para o 1º semestre de Análise e Desenvolvimento de Sistemas, simulando uma plataforma de gestão de assinaturas de jogos digitais para escolas.

---

## 📖 Visão Geral

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/070ee677-db75-421d-a23d-d37e73baf023" />



O projeto consiste no desenvolvimento de um aplicativo desktop para gestão de assinaturas de jogos educacionais, criado para atender a uma demanda da empresa Messier Data & Creative. O sistema tem como foco gerenciar o acesso de escolas de ensino fundamental e médio a uma plataforma de jogos digitais, permitindo o controle de pacotes de jogos, limites de acessos mensais, IPs autorizados e a geração de relatórios de consumo.

As funcionalidades principais dividem-se em um módulo administrativo para cadastros (CRUD) de jogos, pacotes e escolas, e um módulo escola para autenticação de login com validação de pacote ativo e verificação de IP de origem. O controle de acesso é realizado via registro automático de logs, garantindo o bloqueio imediato caso o limite do pacote contratado seja atingido.

Desenvolvido com a linguagem C# (.NET) e interface em WinForms ou WPF, o projeto utiliza SQLite para persistência de dados e Git/GitHub para controle de versão. A solução adota uma abordagem interdisciplinar, integrando conceitos de modelagem de banco de dados, segmentação de redes, lógica de proposição da matemática discreta e estruturas de decisão e repetição de algoritmos.

### 🎯 Problema Resolvido
Como garantir que apenas escolas com assinatura ativa e de locais autorizados acessem os jogos, respeitando os limites contratados e fornecendo dados de consumo para tomada de decisão?

### ✨ Principais Funcionalidades

- **Painel Administrativo (Messier):** Cadastro completo de `Games`, `Pacotes de Assinatura` e `Escolas`.
- **Módulo Escola:** Autenticação segura com validação por **IP autorizado** e verificação de pacote ativo.
- **Catálogo Inteligente:** Exibição dinâmica de jogos conforme o pacote adquirido pela escola.
- **Controle de Acessos:** Registro de cada acesso em log, com contabilização e **bloqueio automático** ao atingir o limite mensal do pacote.
- **Relatórios Gerenciais:** Relatórios de consumo por escola e por período, auxiliando na análise de uso da plataforma.

---

## 🛠 Estrutura de pastas

```text
PI-Messier-1ADS/
│
├── README.md                          # ← Você está aqui
│
├── src
└── DOCUMENTOS/
    │
    └── Entrega 1/
        │
        ├── Redes/
        │   └── SimulacaoIP/           
        │     
        │
        ├── BancoDeDados/
        │   └── README.md              # Modelagem conceitual (DER)
        │
        ├── Algoritmos/
        │   └── Entrega1_Algoritmos.pdf   # Estruturas sequencial, decisão, repetição
        │
        ├── ModelagemSoftware/
        │   └── DocumentoAbertura.pdf     # Requisitos funcionais e não funcionais
        │
        └── MatematicaDiscreta/
            └── RegrasLogica.pdf          # Lógica proposicional, tabela-verdade, cenários.

```


---

## 🚀 Tecnologias

| Stack | Tecnologia | Motivo |
|-------|------------|--------|
| **Linguagem** | C# (.NET 8.0) | Plataforma robusta para desenvolvimento Desktop, com forte tipagem e orientação a objetos. |
| **Interface** | Windows Forms (WinForms) | Escolha do projeto para prototipação rápida e foco nos fundamentos. |
| **Banco de Dados** | SQLite | Dispensa instalação de servidores, garantindo que o protótipo funcione offline e em qualquer máquina. |
| **Acesso a Dados** | ADO.NET | Permite controle total sobre as queries SQL e performance, ideal para os fundamentos da disciplina. |
| **Testes** | xUnit | Framework utilizado para garantir a qualidade das regras de negócio. |
| **Versionamento** | Git / GitHub | Controle de versão e colaboração em equipe. |

---

## 🔑 Funcionalidades em Detalhes

### 1. Segurança e Autenticação
- **Login da Escola:** Autenticação por credenciais da escola.
- **Validação por IP:** Verificação se o IP de origem (simulado) pertence à lista de IPs autorizados da escola, registrando tentativas de acesso bloqueadas.

### 2. Gestão de Assinatura e Acesso
- **Catálogo Personalizado:** Após login, a escola visualiza apenas os jogos vinculados ao seu pacote ativo.
- **Contador de Acessos:** Cada jogo acessado é registrado em log com `data/hora`, `escola`, `game` e `status`. Um contador mensal é incrementado.
- **Bloqueio por Limite:** Se o consumo mensal atingir o limite do pacote, o acesso é bloqueado e uma mensagem clara é exibida ao usuário.

### 3. Relatórios Gerenciais
- **Consumo por Escola:** Filtro por período para visualizar o uso em `hh:mm` ou quantidade de acessos.
- **Status de Pacotes:** Relatório que cruza `Escola` vs `Pacote`, exibindo o limite mensal, consumo atual e percentual de utilização.

---

## 📋 Pré-requisitos e Execução

1.  **SDK do .NET 8.0** ou superior.
2.  **Visual Studio 2022** (Community edition) ou VS Code.
3.  Clonar o repositório:
    ```bash
    git clone https://github.com/[SEU_USUARIO]/Messier-Edu-GameManager.git
Abrir a solution Messier-Edu-GameManager.sln.

Executar o script de criação do banco localizado em src/Messier.Data/Scripts/schema.sql para gerar o arquivo messier_edu.db.

Definir o projeto Messier.UI como startup e executar (F5).
