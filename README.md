# Dashboard Interativa de Vendas Porsche (Excel + AI/HTML Canvas)

Repositório criado para reproduzir uma dashboard de vendas interativa do Expert Felipe Aguiar baseada em dados  de 100 transações da marca Porsche. O projeto combina o tratamento inicial de dados no Excel com a geração de uma interface web personalizada em HTML (via ChatGPT / Canvas), superando as limitações visuais padrão das planilhas.

##  Objetivo do Projeto
Criar um painel interativo, elegante e funcional que responda a perguntas estratégicas de negócio sobre o desempenho de vendas da Porsche, utilizando filtros dinâmicos e uma experiência de usuário (UI/UX) refinada, inspirada no site oficial da Porsche Brasil.

##  Etapas de Desenvolvimento

1. **Tratamento de Dados (Excel):**
   - Utilização de uma base de dados contendo 100 registros de vendas.
   - Formatação e higienização do campo `SalesPriceSanitized` para o formato Contábil.

2. **Engenharia de Prompt e Renderização (ChatGPT / Canvas):**
   - Utilização do recurso Canvas do ChatGPT para renderizar o painel dinâmico em HTML com base no prompt estruturado abaixo.

---

##  Prompt Utilizado na IA (ChatGPT / Canvas)

```text
Utilizando o recurso de Canvas. Renderize uma Dashboard em html .
 
#Filtros
-> Porsche Model
-> Model Year
-> City
-> SalesPriceSanitized
-> Pay Method
 
#Perguntas de Negócio e Kpis
 -> Quais modelos Porsche apresentam maior volume de vendas e maior faturamento?
-> Quais formas de pagamento são mais utilizadas e qual o faturamento associado a cada uma?
-> Quais cidades concentram o maior volume de vendas e faturamento?
 
#Sobre o ui/ux, se baseie no site oficial da Porsche Brasil:
[https://www.porsche.com/brazil/pt/](https://www.porsche.com/brazil/pt/)
#Tenha um ar de elegante e refinado

---

##  Filtros Interativos
- **Porsche Model** (Modelo do veículo)
- **Model Year** (Ano do modelo)
- **City** (Cidade da venda)
- **SalesPriceSanitized** (Faixa de preço de venda)
- **Pay Method** (Forma de pagamento)

---

##  Resolução das Perguntas de Negócio e Lógica Técnica

### 1. Volume de Vendas e Faturamento por Modelo
- **Localização na Dashboard:** Seção *Modelos Porsche em Destaque*.
- **Lógica de Agrupamento e Cálculo:**
  1. Agrupamento de dados pelo campo `PorscheModelSanitized`.
  2. **Volume de Vendas:** Contagem exata de registros (unidades vendidas) por modelo.
  3. **Faturamento Total:** Soma acumulada do campo `SalesPriceSanitized`.
  4. **Classificação e Exibição:** Ordenação primária por volume de vendas, utilizando o faturamento como critério de desempate. Exibição em gráfico de barras para comparação visual imediata da receita gerada por cada modelo.

---

### 2. Formas de Pagamento e Representatividade Financeira
- **Localização na Dashboard:** Seção *Faturamento por Forma de Pagamento*.
- **Lógica de Agrupamento e Cálculo:**
  1. Agrupamento de dados pelo campo `PayMethodSanitized`.
  2. **Métricas Calculadas:**
     - **Quantidade de Vendas:** Total de transações por modalidade.
     - **Faturamento Associado:** Soma do valor das vendas por método.
     - **Participação (%):** Razão entre o faturamento da modalidade e o faturamento total filtrado ($\text{Faturamento da Modalidade} / \text{Faturamento Total} \times 100$).
  3. **Classificação e Exibição:** Barras ordenadas de forma decrescente pelo faturamento absoluto, com a porcentagem de representatividade estampada no rótulo de cada categoria.

---

### 3. Distribuição Geográfica de Vendas (Concentração e Performance)
- **Localização na Dashboard:** Seções *Cidades com Maior Desempenho* e *Detalhamento por Cidade*.
- **Lógica de Agrupamento e Cálculo:**
  1. Agrupamento de dados pelo campo `CitySanitized`.
  2. **Métricas Calculadas:**
     - **Volume de Vendas:** Total de transações realizadas na localidade.
     - **Faturamento:** Soma da receita gerada na cidade.
     - **Ticket Médio:** Razão entre o faturamento total da cidade e a quantidade de vendas realizadas.
  3. **Visualização Combinada (Gráfico + Tabela):**
     - **Gráfico de Barras:** Exibe as 8 principais cidades ordenadas por volume de vendas para identificação rápida de tração de mercado.
     - **Tabela Complementar:** Apresenta até 12 cidades detalhando volume e faturamento.
  4. **Racional de Negócio:** A combinação de gráfico e tabela permite identificar mercados consolidados (alto volume) e praças com alto ticket médio (maior faturamento mesmo com menor volume), direcionando decisões estratégicas de expansão comercial.

---

##  Design e UI/UX
- **Estilo:** Design elegante, refinado e minimalista.
- **Referência:** Identidade visual, tipografia e paleta de cores baseadas no site oficial da [Porsche Brasil](https://www.porsche.com/brazil/pt/).


