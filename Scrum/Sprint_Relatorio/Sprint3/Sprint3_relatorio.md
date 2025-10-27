# TERCEIRA SPRINT (03/09/2025)

O foco desta sprint foi a integração do **motor de inteligência artificial (BlackBox AI)**, essencial para cumprir o requisito de prioridade máxima de **tratamento automatizado de chamados (Re002)**. O objetivo foi transformar o esqueleto do aplicativo em uma ferramenta funcional de suporte, criando o **Módulo de Suporte Funcional (MVP)**.

As tarefas principais envolveram o desenvolvimento do fluxo de comunicação entre o *frontend*, o *backend* e a BlackBox AI, bem como a persistência de dados dessas interações.

Os entregáveis desta sprint foram:

1.  **Módulo de Suporte Funcional (MVP):** O usuário pode acessar a interface, inserir uma descrição de problema (pergunta) e receber uma resposta ou classificação inicial da IA.
2.  **Log de Interações da IA:** Estrutura de banco de dados e lógica implementada para registrar todas as interações do módulo de IA.

## Requisitos Atendidos

Esta sprint avançou significativamente no requisito de maior complexidade e prioridade do projeto:

| Requisito Atendido | Descrição do Alinhamento |
| :--- | :--- |
| **Re002 (Tratamento de Chamados via I.A)** | O **módulo de comunicação** com a BlackBox AI foi desenvolvido e integrado. O *backend* agora consegue receber a entrada do usuário e obter uma **classificação/resposta formatada** da IA (que simula a atribuição de prioridade e categoria). |
| **Re001 (Criação de Chamados)** | A **interface de Chat/Chamado** foi criada no *frontend*, representando a primeira forma de **entrada de um chamado** pelo usuário, embora o registro completo do chamado virá na próxima sprint. |
| **Re003 (MS SQL Server em Nuvem)** | A nova tabela de **Log de Interações da IA** foi criada e populada, comprovando a capacidade de persistir dados complexos gerados pelo motor de IA no banco de dados em nuvem. |

## Modelagem do Log de Interações da IA

Para garantir a rastreabilidade e o futuro treinamento/monitoramento do modelo de IA, foi modelada e implementada a seguinte tabela:

| Campo | Tipo de Dado | Observação |
| :--- | :--- | :--- |
| `ID_Log` | INT | Chave primária. |
| `ID_Usuario` | INT | Chave estrangeira para rastrear quem interagiu (Re006). |
| `Texto_Entrada` | VARCHAR | Descrição do problema fornecida pelo usuário. |
| `Categoria_IA` | VARCHAR | Categoria atribuída pela IA (Software, Hardware, Rede). |
| `Prioridade_IA` | VARCHAR | Prioridade sugerida pela IA (Baixa, Média, Alta). |
| `Resposta_IA` | TEXT | Resposta ou instrução preliminar da IA ao usuário. |
| `Data_Interacao` | DATETIME | Carimbo de data/hora da interação. |

# 🏃‍DoR atendidos na Sprint 3
- **✅ User Stories prontas para desenvolvimento (Re002, Re001)**
- **✅ Critérios de aceitação definidos para módulo de IA e log de interações**
- **✅ Modelagem do banco de dados atualizada com tabela de Log de Interações da IA**
- **✅ Subtarefas definidas para fluxo IA frontend-backend**
- **✅ Diagrama de rotas atualizado para integração com serviço de IA**

# 🏆DoD atendidos na Sprint 3
- **✅ Código implementado e funcionando para Módulo de Suporte Funcional (MVP)**
- **✅ Banco de dados atualizado com registro de interações da IA**
- **✅ Documentação da API atualizada para novos endpoints da IA**
- **✅ Protótipo funcional: interação com IA respondendo ao usuário**
- **✅ Vídeo de entrega da sprint demonstrando fluxo completo**

## Ferramentas utilizadas

* **BlackBox AI API:** Serviço de inteligência artificial utilizado para processamento e classificação de texto.
* **[Tecnologia Backend]:** Utilizada para hospedar a lógica de integração e *proxy* que comunica o *frontend* com a BlackBox AI.
* **HTML/CSS:** Implementação da interface de Chat/Chamado no *frontend*.
* **MS SQL Server:** Utilizado para persistir os logs de interações da IA.

---

Com o esqueleto pronto e o motor de inteligência central integrado, a próxima sprint pode focar na formalização do processo, convertendo as interações da IA em **registros formais de chamados** para que os Técnicos possam começar a gerenciá-los (Re004).
