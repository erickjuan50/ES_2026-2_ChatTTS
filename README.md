# Auditoria de Maturidade ChatTTS - Engenharia de Software (COMP0503)

Este repositório apresenta os resultados da Atividade Avaliativa 1 (A1), focada na Auditoria de Maturidade em Ecossistemas LLM do projeto ChatTTS. A análise foi estruturada seguindo critérios de modelos como CMMI e MPS.BR.

## Equipe e Contribuições Individuais
* Erick Juan Gois Oliveira: Análise do Eixo IV - Verificação e Validação.
* Wanessa Silva Santos: Análise do Eixo V - Qualidade de Software.
* Carlos Henrico Fontes Cabral: Análise do Eixo I - Gestão de Projeto.
* Luiz Felipe da Conceição Souza: Análise do Eixo III - Arquitetura e Modelagem.
* João Pedro Brandão Almeida: Análise do Eixo II - Engenharia de Requisitos.
* Lucas da Silva Batista: Conclusão e Plano de Melhoria.

---

## Resumo dos Achados de Auditoria

O ChatTTS demonstra uma qualidade operacional elevada, mas com lacunas significativas em formalização de processos.

| Eixo de Auditoria | Julgamento de Maturidade | Principais Observações |
| :--- | :--- | :--- |
| I - Gestão (GPR) | Aderência Parcial | Ciclo adaptativo com roadmap, mas sem planejamento por milestones. |
| II - Requisitos (GRE) | Aderência Parcial | Rastreabilidade via Issues/PRs, mas sem processo formal de baseline. |
| III - Arquitetura (PJR) | Boa Aderência | Arquitetura modular (Facade) com bom isolamento de componentes. |
| IV - Verificação (V&V) | Boa (VER) / Parcial (VAL) | CI forte para código, mas fraco em validar a qualidade do áudio gerado. |
| V - Qualidade (GQA) | Aderência Parcial | Automação de estilo presente, mas sem análise estática avançada. |

---

## Tutorial de Pesquisa: Como Validar esta Auditoria

Para que qualquer interessado possa chegar às mesmas conclusões ou auditar o projeto de forma independente, os passos abaixo detalham como navegar no repositório oficial do ChatTTS no GitHub.

### 1. Como auditar Gestão e Requisitos (Eixos I e II)
* Onde pesquisar: Abas de Issues e Pull Requests.
* O que fazer: Procure por solicitações de novas funcionalidades ou correções de bugs. 
* Conclusão: Verifique se as alterações no código (PRs) estão vinculadas a uma demanda específica (Issue). Note a ausência de Milestones ou abas de Projects configuradas, o que evidencia que o planejamento é orientado por necessidades técnicas imediatas da comunidade e não por um cronograma formal.

### 2. Como auditar a Arquitetura (Eixo III)
* Onde pesquisar: Estrutura de pastas do código-fonte.
* O que fazer: Localize a classe central Chat.
* Conclusão: Analise como essa classe funciona como uma fachada (Facade) para orquestrar módulos como Normalizer, Tokenizer e os modelos GPT/DVAE. Se os componentes são carregados de forma independente e modular, a boa aderência à modelagem técnica é confirmada.

### 3. Como auditar Verificação e Validação (Eixo IV)
* Onde pesquisar: Pasta .github/workflows/.
* O que fazer: Inspecione arquivos YAML como unitest.yml e push-format.yml.
* Conclusão: Estes arquivos mostram a execução automatizada de testes e formatação de código (Verificação). No entanto, ao observar a ausência de testes de regressão que avaliem a inteligibilidade ou naturalidade do áudio, confirma-se a lacuna na Validação da saída da IA.

### 4. Como auditar a Garantia da Qualidade (Eixo V)
* Onde pesquisar: Raiz do repositório.
* O que fazer: Procure por arquivos como CONTRIBUTING.md ou evidências de ferramentas como SonarQube ou CodeQL.
* Conclusão: A ausência de um guia de contribuição oficial e de gates de qualidade automatizados de análise estática fundamenta o achado de que a qualidade é mantida de forma operacional e comunitária, sem formalismos processuais robustos.

---

## Plano de Melhoria Sugerido
As ações prioritárias para elevar a maturidade do projeto incluem a institucionalização da gestão (uso de Milestones e Templates) e a implementação de um pipeline de validação objetiva para a saída de áudio gerada pelo modelo.
