# Resultados — Andromeda-Net

Esta pasta armazena os artefatos gerados pelas análises: figuras, tabelas e datasets processados.

## Estrutura

```
resultados/
├── figuras/        # Plots gerados pelos notebooks (PNG/SVG)
└── tabelas/        # Tabelas de centralidade exportadas (CSV)
```

## Principais Achados

### Pergunta de Pesquisa
> O domínio histórico na Fórmula 1 se constrói através da retenção de poucos pilotos talentosos (núcleos isolados) ou pela alta rotatividade de talentos que conectam diferentes equipes?

### Métricas da Rede Bipartida (Piloto–Construtor)

| Métrica | Valor |
|---|---|
| Total de Nós | 1.072 (861 pilotos + 211 construtoras) |
| Total de Arestas | 2.150 conexões de sucesso |
| Nós Isolados | 0 |

### Top Construtoras por Grau Ponderado (corridas pontuadas)

| Construtora | Corridas pontuadas |
|---|---|
| Ferrari | 2.439 |
| McLaren | 1.923 |
| Williams | 1.676 |
| Tyrrell | 881 |
| Team Lotus | 871 |

### Top Pilotos por Betweenness Centrality (maior "ponte" entre escuderias)

| Piloto | Betweenness | Degree | Eigenvector |
|---|---|---|---|
| Giancarlo Fisichella | 0.0115 | 0.2209 | 0.0667 |
| Bob Bondurant | 0.0025 | 0.1953 | 0.0779 |
| Valtteri Bottas | 0.0019 | 0.1244 | 0.0305 |

### Interpretação
- **Ferrari, McLaren e Williams** dominam a rede em número de corridas pontuadas, confirmando seu papel de *hubs* históricos na F1.
- **Giancarlo Fisichella** tem o maior **Betweenness Centrality** na rede projetada de pilotos, indicando que ele foi o maior "conector" entre diferentes bolhas de escuderias ao longo de sua carreira (passou por Benetton, Jordan, Sauber, Renault, Force India, Ferrari e outras).
- A rede **não é composta por núcleos isolados**: as grandes construtoras compartilham pilotos entre si ao longo do tempo, criando uma rede altamente conectada.

> Os resultados completos e gráficos estão disponíveis nos notebooks da pasta `notebooks/`.
