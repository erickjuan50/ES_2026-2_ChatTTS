# Auditoria de Maturidade ChatTTS - Engenharia de Software (COMP0503)

[cite_start]Este repositório contém os resultados de uma auditoria de maturidade realizada no ecossistema **ChatTTS**[cite: 3]. [cite_start]A análise segue os princípios dos modelos **CMMI** e **MPS.BR** para avaliar como um projeto de código aberto de LLM (Large Language Model) lida com processos de engenharia de software[cite: 2, 15].

## 👥 Equipe de Auditoria
* [cite_start]**Erick Juan Gois Oliveira**: Análise do Eixo IV - Verificação [cite: 6]
* [cite_start]**Wanessa Silva Santos**: Análise do Eixo V - Qualidade de Software [cite: 6]
* [cite_start]**Carlos Henrico Fontes Cabral**: Análise do Eixo I - Gestão de Projeto [cite: 6]
* [cite_start]**Luiz Felipe da Conceição Souza**: Análise do Eixo III - Arquitetura e Modelagem [cite: 6]
* [cite_start]**João Pedro Brandão Almeida**: Análise do Eixo II - Gestão de Requisitos [cite: 6]
* [cite_start]**Lucas da Silva Batista**: Conclusão e Plano de Melhoria [cite: 6]

---

## 📊 Resumo da Auditoria por Eixo

### Eixo I: Ciclo de Vida e Metodologias Ágeis
* [cite_start]**Status**: Aderência Parcial[cite: 22].
* [cite_start]**Achados**: O projeto opera com um ciclo de vida predominantemente adaptativo e possui um roadmap público[cite: 12]. [cite_start]No entanto, há pouca evidência de planejamento formal por marcos (milestones) ou uso de ferramentas como GitHub Projects[cite: 12].

### Eixo II: Engenharia de Requisitos
* [cite_start]**Status**: Aderência Parcial[cite: 39].
* [cite_start]**Achados**: Os requisitos são tratados de forma incremental via Issues e Pull Requests[cite: 29]. [cite_start]Embora a rastreabilidade técnica seja boa (ex: suporte a NPU), não apresenta um processo formal de baseline ou padrão de especificação[cite: 32, 37].

### Eixo III: Arquitetura e Modelagem
* [cite_start]**Status**: Boa Aderência Técnica[cite: 56].
* [cite_start]**Achados**: Arquitetura modular e centrada na classe `Chat`, que funciona como uma **Fachada (Facade)**[cite: 46, 48]. [cite_start]Existe um bom isolamento entre a interface externa (FastAPI) e o núcleo de inferência[cite: 50, 54].

### Eixo IV: Verificação e Validação (V&V)
* [cite_start]**Status**: Boa (Verificação) / Parcial (Validação)[cite: 73].
* [cite_start]**Achados**: Forte em fluxos de CI para verificação técnica (formatação, testes unitários)[cite: 65, 66]. [cite_start]Contudo, carece de métricas automáticas para validar a qualidade da saída da IA, como a inteligibilidade do áudio gerado[cite: 64, 68].

### Eixo V: Qualidade de Software
* [cite_start]**Status**: Aderência Parcial[cite: 90].
* [cite_start]**Achados**: Apresenta automação de estilo e testes, mas a governança de qualidade é mais operacional do que formalizada[cite: 80, 101]. [cite_start]Ausência de um arquivo `CONTRIBUTING.md` e de ferramentas de análise estática avançada como CodeQL ou SonarQube[cite: 84, 97, 98].

---

## 🚀 Plano de Melhoria Sugerido

[cite_start]Com base no diagnóstico, recomendam-se duas ações prioritárias para elevar a maturidade do projeto[cite: 106, 109]:

1.  [cite_start]**Institucionalizar a Gestão**: Criar um arquivo `CONTRIBUTING.md`, padronizar templates de Issues/PRs e utilizar Milestones para tornar o roadmap rastreável[cite: 111, 114].
2.  [cite_start]**Pipeline de Validação e Assurance**: Expandir o CI para incluir métricas de qualidade de áudio e integrar ferramentas de análise estática de código[cite: 118, 120, 121].

---

## 🔍 Como verificar estas informações (Tutorial)

Caso deseje pesquisar estas informações diretamente no repositório do ChatTTS, siga este guia:

1.  [cite_start]**Verificar Gestão (GPR)**: Acesse a aba **Releases** e o roadmap no `README.md`[cite: 14]. [cite_start]Observe a ausência de uso das abas **Projects** ou **Milestones** do GitHub para confirmar a baixa formalização gerencial[cite: 12].
2.  [cite_start]**Rastrear Requisitos (GRE)**: Vá em **Pull Requests** e procure por vínculos com **Issues**[cite: 32]. [cite_start]Exemplos como o suporte a "Ascend NPU" mostram como uma demanda se materializa no código[cite: 34, 35].
3.  [cite_start]**Analisar Arquitetura (PJR)**: Explore o código-fonte e localize a classe `Chat`[cite: 46]. [cite_start]Veja como ela orquestra componentes como `Normalizer`, `Tokenizer` e seletores de dispositivo[cite: 53].
4.  [cite_start]**Auditar CI/CD (V&V)**: Navegue até a pasta `.github/workflows/`[cite: 66]. [cite_start]Abra arquivos como `unitest.yml` para ver quais testes e versões de Python são verificados automaticamente[cite: 66].
5.  [cite_start]**Avaliar Governança de Qualidade (GQA)**: Verifique as labels nas **Issues** (ex: `bug`, `enhancement`, `performance`)[cite: 87]. [cite_start]Isso demonstra como a dívida técnica é visível, apesar da falta de indicadores formais[cite: 86, 94].
