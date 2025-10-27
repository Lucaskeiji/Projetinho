# SEGUNDA SPRINT (24/08/2025)

O sprint concentrou-se na **configuração do ambiente técnico** e na construção da **interface de acesso básica** (Login e Cadastro), cumprindo os primeiros passos para a interação do usuário e a comunicação com a infraestrutura de dados definida (Re003).

As tarefas principais foram desdobradas para garantir uma validação *end-to-end* (ponta a ponta) da arquitetura, focando no **esboço do aplicativo** e na **persistência básica de dados**.

Os entregáveis desta sprint foram:

1.  **Protótipo do Aplicativo Navegável:** Telas de Login e Cadastro baseadas no *design* do Figma.
2.  **Backend Validado:** CRUD básico de usuários implementado e testado com sucesso no banco de dados em nuvem.

## Requisitos Atendidos

Embora o foco desta sprint fosse principalmente técnico e de configuração, ela estabeleceu a base para a implementação dos requisitos de prioridade 3 e 1:

| Requisito Atendido | Descrição do Alinhamento |
| :--- | :--- |
| **Re003 (MS SQL Server em Nuvem)** | A **camada de acesso a dados (CRUD)** foi implementada e testada, comprovando a conectividade e a funcionalidade do banco de dados na nuvem. |
| **Re006 (Níveis de Acesso)** | Foram desenvolvidas as **telas de Login e Cadastro**, que são a **porta de entrada** para o sistema, estabelecendo o primeiro passo para a futura diferenciação de níveis de acesso. |

## Modelagem de Entidade de Usuário

* Os dados de usuário foram modelados para atender às necessidades iniciais de segurança e cadastro, conforme o **Re006 (Níveis de Acesso)**.

| Campo | Tipo de Dado | Observação |
| :--- | :--- | :--- |
| `ID_Usuario` | INT | Chave primária. |
| `Nome` | VARCHAR | Nome completo do funcionário/usuário. |
| `Email` | VARCHAR | Usado como *login* (deve ser único). |
| `Senha_Hash` | VARCHAR | Armazenamento da senha **criptografada** (hashing). |
| `Nivel_Acesso` | VARCHAR | Inicialmente preenchido como 'Funcionário'. Preparado para os valores 'Responsável Técnico' e 'Administrador'. |

 # 🏃‍DoR atendidos na Sprint 2
- **✅ Telas no Figma anexadas ou utilizadas para desenvolvimento**
- **✅ Modelagem do banco de dados atualizada (entidade Usuário)**
- **✅ Subtarefas definidas para Login e Cadastro**
- **✅ Critérios de aceitação atendidos para CRUD inicial de usuário**
- **✅ User Stories elegíveis para início (login e cadastro)**

# 🏆DoD atendidos na Sprint 2
- **✅ Código implementado e funcionando (CRUD básico de usuários)**
- **✅ Documentação da API atualizada para operações de usuário**
- **✅ Banco de dados atualizado e testes de conectividade com nuvem**
- **✅ Vídeo de entrega registrado (demonstração end-to-end prevista no relatório)**
- **✅ Protótipo navegável entregue (Login e Cadastro funcionando)**

## Ferramentas utilizadas

* **HTML/CSS:** Para o desenvolvimento das interfaces *frontend* (Login e Cadastro).
* **[Nome da Tecnologia Backend] (ex: .NET, Node.js, Python/Django):** Para o desenvolvimento da API de *backend* e a lógica de CRUD.
* **MS SQL Server:** Banco de dados em nuvem para persistência dos dados de usuário.
* **Figma:** Utilizado como base para a estilização e *layout* das telas de acesso.
