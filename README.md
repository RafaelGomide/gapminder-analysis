# Análise Exploratória — Gapminder

Notebook de estudo com foco em pandas avançado, NumPy vetorizado e visualização de dados,
utilizando o dataset [Gapminder](https://www.gapminder.org/data/) — dados socioeconômicos
de 142 países entre 1952 e 2007.

## Técnicas cobertas

**pandas**
- `groupby().agg()` com múltiplas métricas simultâneas
- `transform()` para normalização dentro de grupos
- `apply()` com funções customizadas por grupo
- `rolling()` para médias móveis em séries temporais

**NumPy**
- Operações vetorizadas sem loop
- Boolean indexing para filtragem condicional
- Broadcasting entre arrays de shapes diferentes

**Visualização**
- `matplotlib` com controle explícito de `fig, ax`
- `seaborn` para heatmap de correlação e scatter estatístico
- `plotly.express` para gráficos interativos com hover

## Principais análises

| Análise | Técnica |
|---------|---------|
| GDP per capita por continente (média, máx, mín) | `groupby().agg()` |
| Normalização do GDP dentro de cada continente | `groupby().transform()` |
| Variação percentual da expectativa de vida por país | `groupby().apply()` |
| Média móvel de 3 períodos da expectativa de vida no Brasil | `rolling(window=3)` |
| Correlação entre expectativa de vida, população e GDP | `seaborn.heatmap()` |
| Relação GDP × expectativa de vida em 2007 | `plotly.express.scatter()` |
| Evolução da expectativa de vida por continente | `matplotlib` multi-linha |

## Principais insights

- Oceania e Europa têm o maior GDP per capita médio histórico (US$ 18.6k e US$ 14.5k respectivamente)
- África apresenta GDP médio ~8x menor que a Oceania, com mínimos abaixo de US$ 250
- Correlação de 0.58 entre GDP per capita e expectativa de vida — relação relevante mas não determinística
- População praticamente não correlaciona com expectativa de vida (r = 0.06)
- Brasil aumentou expectativa de vida de 50.9 para 72.4 anos entre 1952 e 2007 (+42%)
- Expectativa de vida na África estagnou nos anos 90, possivelmente associada à epidemia de HIV/AIDS

## Dataset

- **Fonte:** [Gapminder via Jenny Bryan (GitHub)](https://github.com/jennybc/gapminder)
- **Formato:** TSV, 1.704 linhas × 6 colunas
- **Colunas:** `country`, `continent`, `year`, `lifeExp`, `pop`, `gdpPercap`
- **Cobertura:** 142 países, 5 continentes, 12 anos (1952–2007, intervalo de 5 anos)

## Como executar

```bash
git clone https://github.com/RafaelGomide/gapminder-analysis
cd gapminder-analysis
pip install -r requirements.txt
jupyter notebook analise_gapminder.ipynb
```

## Tecnologias

`Python 3.11` `pandas` `numpy` `matplotlib` `seaborn` `plotly`
