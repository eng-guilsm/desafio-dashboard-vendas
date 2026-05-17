# Dashboard Interativo: Análise de Assinaturas e Cross-Selling (Xbox Ecosystem)

Este repositório contém a entrega do desafio prático de Excel da DIO, focado na transformação de dados brutos de assinaturas em um painel executivo interativo e dinâmico. O projeto simula a gestão de uma base de clientes do ecossistema Xbox, analisando o faturamento, a recorrência e o impacto de produtos adicionais (*add-ons*).

---

## 📊 O Projeto e a Base de Dados

A análise foi realizada a partir de uma base de dados contendo registros de 295 assinantes ativos. O ecossistema mapeia o plano principal (`Ultimate` vs outros), o tipo de recorrência, cupons de desconto aplicados e a adesão a serviços parceiros via *cross-selling* (`EA Play Season Pass` e `Minecraft Season Pass`).

### KPIs Principais Calculados (Estado Global)
* **Faturamento Total (ARR/MRR):** R$ 7.633,00
* **Ticket Médio (ARPU):** R$ 25,87
* **Taxa de Renovação Automática:** ~50% (Equilíbrio estatístico perfeito na base)

---

## 🛠️ Arquitetura e Funcionalidades do Dashboard

O painel foi construído focado em **limpeza visual, alto contraste e usabilidade (UX)**, adotando a identidade visual clássica da marca Xbox.

1.  **Linha de Evolução Temporal (Faturamento):** Gráfico de linha com suavização por interpolação (*spline*) para análise de tendências de receita ao longo dos períodos, mitigando o ruído visual e destacando o comportamento macro do fluxo de caixa.
2.  **Segmentação Dinâmica (Slicer):** Filtro interativo por `Subscription Type` (Annual, Monthly, Quarterly). Ao clicar, todo o ecossistema do dashboard (KPIs e Gráficos) colapsa instantaneamente para refletir apenas o comportamento da coorte selecionada.
3.  **Gráfico de Rosca de Alta Fidelidade (Retenção):** Isola dinamicamente o volume de `Count of Auto Renewal` (`Yes` vs `No`), permitindo visualizar a volatilidade e o risco de *churn* em tempo real à medida que os filtros são aplicados.

---

## 💡 Insights Analíticos Extraídos

* **O Paradoxo do Cupom:** Identificou-se uma simetria quase perfeita na distribuição de incentivos financeiros. Clientes com renovação automática ativa consumiram praticamente o mesmo volume de cupons (R$ 1.059,00) que os clientes sem renovação (R$ 1.063,00). Isso indica uma oportunidade de otimização de margem, realocando cupons estritamente para o comportamento de retenção ativa.
* **Desacoplamento de Layout:** Para garantir a resiliência do arquivo e evitar sobreposição de séries na renderização do gráfico de rosca, a arquitetura do Excel foi dividida em matrizes de cálculo isoladas e conectadas de forma síncrona via *Report Connections*.

---

## 📂 Arquivos no Repositório

* `README.md`: Documentação e contextualização analítica do projeto.
* `dashboard_xbox_finalizado.xlsx`: Arquivo contendo a base tratada, as tabelas dinâmicas de suporte e o painel visual finalizado.

---

> *"A inteligência visual transforma tabelas frias em ferramentas de sobrevivência de mercado."*
