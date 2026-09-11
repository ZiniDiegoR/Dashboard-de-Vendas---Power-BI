# Dashboard de Vendas — Power BI

Meu primeiro projeto de portfólio em análise de dados: um dashboard interativo de desempenho de vendas, construído do zero — desde a limpeza dos dados brutos até a modelagem e o design final dos visuais.

## 🎯 Objetivo

Praticar o fluxo completo de um projeto de BI: identificar e tratar problemas reais de qualidade de dados, construir um modelo relacional coerente e transformar isso em um painel visual claro e interativo, sem depender de fórmulas DAX.

## 🧹 Limpeza de dados (Power Query)

A base original continha diversos problemas comuns em dados do mundo real, todos tratados no Power Query:

- Textos com espaços extras e capitalização inconsistente (ex: categorias escritas de formas diferentes)
- Datas em múltiplos formatos dentro da mesma coluna
- Valores numéricos armazenados como texto (incluindo símbolo de moeda e vírgula decimal)
- Campos de código (como CEP) perdendo zeros à esquerda por estarem tipados como número
- Linhas duplicadas e linhas totalmente vazias
- Valores nulos avaliados e tratados conforme o contexto de negócio (não apenas removidos por padrão)

## 🔗 Modelagem de dados

- Identifiquei um relacionamento **muitos-para-muitos** indevido entre as tabelas de Vendas e Gerentes (ambas conectadas pela coluna Região)
- Resolvi criando uma **tabela dimensão** própria para Região, isolando os valores únicos e conectando-a às duas tabelas de fatos
- Resultado: um modelo em **esquema estrela**, com relações Um-para-Muitos limpas e sem ambiguidade

## 📊 Visuais do dashboard

- **KPIs**: Total de Vendas, Lucro, Ticket Médio e Total de Pedidos (usando Contagem Distinta para refletir pedidos únicos)
- **Evolução de vendas no tempo**: gráfico de área mês a mês
- **Vendas por Categoria** e **Vendas por Região**: gráficos de barra ordenados
- **Pedidos por Forma de Envio**: gráfico de pizza
- **Top 5 Produtos**: ranking dos produtos com maior valor de venda
- **Filtros interativos**: Data (intervalo), Categoria do Produto e Região

Todos os visuais foram construídos usando apenas agregações nativas do Power BI (Soma, Contagem Distinta, Média), sem uso de DAX.

## 🎨 Design

Priorizei um visual limpo e consistente: paleta de cores reduzida, sem bordas ou sombras nos cartões, gridlines removidas, e títulos diretos — buscando uma leitura rápida e profissional.
---

*Projeto feito para fins de aprendizado e portfólio.*
