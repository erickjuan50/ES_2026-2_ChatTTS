# Auditoria de Maturidade ChatTTS - Engenharia de Software (COMP0503)

Este repositório contém os resultados de uma auditoria de maturidade realizada no ecossistema **ChatTTS**. A análise segue os princípios dos modelos **CMMI** e **MPS.BR** para avaliar como um projeto de código aberto de LLM (Large Language Model) lida com processos de engenharia de software.

## 👥 Equipe de Auditoria
* **Erick Juan Gois Oliveira**: Análise do Eixo IV - Verificação
* **Wanessa Silva Santos**: Análise do Eixo V - Qualidade de Software
* **Carlos Henrico Fontes Cabral**: Análise do Eixo I - Gestão de Projeto
* **Luiz Felipe da Conceição Souza**: Análise do Eixo III - Arquitetura e Modelagem
* **João Pedro Brandão Almeida**: Análise do Eixo II - Gestão de Requisitos
* **Lucas da Silva Batista**: Conclusão e Plano de Melhoria

---

## 📊 Resumo da Auditoria por Eixo

### Eixo I: Ciclo de Vida e Metodologias Ágeis
* **Status**: Aderência Parcial.
* **Achados**: O projeto opera com um ciclo de vida predominantemente adaptativo e possui um roadmap público. No entanto, há pouca evidência de planejamento formal por marcos (milestones) ou uso de ferramentas como GitHub Projects.

### Eixo II: Engenharia de Requisitos
* **Status**: Aderência Parcial.
* **Achados**: Os requisitos são tratados de forma incremental via Issues e Pull Requests. Embora a rastreabilidade técnica seja boa (ex: suporte a NPU), não apresenta um processo formal de baseline ou padrão de especificação.

### Eixo III: Arquitetura e Modelagem
* **Status**: Boa Aderência Técnica.
* **Achados**: Arquitetura modular e centrada na classe `Chat`, que funciona como uma **Fachada (Facade)**. Existe um bom isolamento entre a interface externa (FastAPI) e o núcleo de inferência.

### Eixo IV: Verificação e Validação (V&V)
* **Status**: Boa (Verificação) / Parcial (Validação).
* **Achados**: Forte em fluxos de CI para verificação técnica (formatação, testes unitários). Contudo, carece de métricas automáticas para validar a qualidade da saída da IA, como a inteligibilidade do áudio gerado.

### Eixo V: Qualidade de Software
* **Status**: Aderência Parcial.
* **Achados**: Apresenta automação de estilo e testes, mas a governança de qualidade é mais operacional do que formalizada. Ausência de um arquivo `CONTRIBUTING.md` e de ferramentas de análise estática avançada como CodeQL ou SonarQ
