# QUARTA SPRINT (10/09/2025)

Esta sprint foi crucial para garantir a **robustez e a confiabilidade** do sistema. O foco principal foi o **tratamento de exceções**, construindo a rota de **Escalonamento Humano** para os problemas que a IA não consegue resolver ou classificar com segurança (conforme o **Re002**), e solidificando as práticas de **segurança** e **tratamento de erros** na API.

O resultado é a criação de um **fluxo de trabalho completo** que não depende unicamente da inteligência artificial.

Os entregáveis desta sprint foram:

1.  **Fluxo de Chamado Completo:** O sistema é capaz de registrar um chamado, processá-lo pela IA e, se necessário, **escaloná-lo** para a intervenção de um agente humano.
2.  **Painel do Agente Humano:** Interface básica para o Responsável Técnico visualizar e assumir os chamados que foram escalados.

## Requisitos Atendidos

Esta sprint focou em complementar os requisitos de prioridade 1 e 2, garantindo que o processo do chamado seja estável e funcional do início ao fim.

| Requisito Atendido | Descrição do Alinhamento |
| :--- | :--- |
| **Re002 (Tratamento de Chamados via I.A)** | Implementada a **lógica de *fallback*** (retorno) da IA: se a confiança da classificação for baixa ou se a IA não fornecer uma resposta relevante, o chamado é **automaticamente marcado para Escalonamento Humano**. |
| **Re001 (Criação de Chamados)** | O **registro final do chamado** foi implementado, utilizando as informações de descrição, categoria e quem afeta, mas agora com um campo de *status* inicial que pode ser 'Em Análise (IA)', 'Escalonado' ou 'Resolvido'. |
| **Re004 (Gerenciamento de Chamados)** | O **Módulo de Painel do Agente Humano** (para o Responsável Técnico) foi criado, permitindo a visualização dos chamados escalados e o primeiro passo para o gerenciamento. |

## Modelagem e Fluxo de Escalonamento

Para suportar o novo fluxo, a entidade de **Chamados** foi formalmente criada e o processo foi mapeado da seguinte forma:

1.  **Usuário** cria um chamado.
2.  O **Backend** salva o chamado com *Status* = 'Em Análise (IA)'.
3.  O **Backend** envia o texto para a IA (como na Sprint 3).
4.  **Lógica de Escalonamento:**
    * **Se IA responder com alta confiança:** o *Status* muda para 'Em Fila' (ou prioridade definida) e o chamado é direcionado.
    * **Se IA falhar/baixa confiança:** o *Status* muda para **'Escalonado'**.
5.  O **Responsável Técnico** visualiza o chamado no Painel do Agente Humano e pode assumi-lo.

### Melhoria de Segurança (Não Funcional)

A implementação de **validações de segurança** (como *sanitização* de entrada, validação de tipos e formatos de dados) e o **tratamento de erros** robusto na API garantem maior **estabilidade e resiliência** contra falhas de conexão ou entradas de dados maliciosas.

## Ferramentas utilizadas

* **[Tecnologia Backend]:** Implementação da lógica de decisão e tratamento de erros e exceções.
* **MS SQL Server:** Utilizado para persistir o **registro formal do chamado** e seus diferentes *status*.
* **HTML/CSS/JS:** Criação da interface do **Painel do Agente Humano** (*dashboard*).

---

Com a espinha dorsal do fluxo de trabalho (Usuário $\rightarrow$ IA $\rightarrow$ Humano) e a segurança básica estabelecidas, a próxima sprint deve focar na finalização das funcionalidades de gestão para o Responsável Técnico e na oficialização dos níveis de acesso.
