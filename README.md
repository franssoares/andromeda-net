# Andromeda-Net: O Ecossistema de Sucesso na F1

## Integrantes
Franklin Luiz Soares do Nascimento Filho

## Vídeo
🎥 [Link para o vídeo no Google Drive](https://drive.google.com/) *(atualizar após upload)*

## Problema e pergunta
O domínio histórico na Fórmula 1 se constrói através da retenção de poucos pilotos talentosos (núcleos isolados) ou pela alta rotatividade de talentos que conectam diferentes equipes? O objetivo é descobrir se as maiores equipes da história compartilham os mesmos pilotos de ponta ou se fecham em seus próprios ecossistemas.

## Dados (fonte, como obter, limpeza)
Os dados são do dataset da Fórmula 1 (obtidos via Kaggle), armazenados localmente na pasta `data/`. A limpeza descrita no notebook inicial consiste em filtrar resultados (`results.csv`), mantendo apenas as corridas em que o piloto pontuou, garantindo que o grafo capture apenas as relações que geraram sucesso esportivo e descartando pilotos que apenas participaram mas não pontuaram por uma escuderia.

## Modelagem (nó, aresta, peso, direção, o que ficou de fora)
A rede principal é um **Grafo Bipartido, Ponderado e Não-Direcionado**.
* **Nós:** Divididos em duas partições - Pilotos e Construtoras (Equipes).
* **Arestas:** Uma aresta liga um piloto a uma construtora se ele marcou pontos correndo por ela em campeonatos oficiais.
* **Peso:** O total de pontos conquistados pelo piloto naquela escuderia.
* **Direção:** Não há direção.
* **O que ficou de fora:** Pilotos de testes, participações apenas em treinos livres, e corridas onde o piloto terminou fora da zona de pontuação (pois o foco é a conexão via *sucesso*).

## Conteúdo do curso utilizado
| conceito | semana | onde aparece | para que serviu |
|---|---|---|---|
| Redes Bipartidas | 6 | notebooks/EDA/02_eda_e_redes.ipynb, cél. 3 | Modelar o ecossistema base relacionando pilotos e equipes. |
| Projeção de Rede | 6 | notebooks/EDA/02_eda_e_redes.ipynb, cél. 4 | Transformar a rede bipartida em uma rede apenas de pilotos para achar pontes. |
| Centralidade de Grau | 2 | notebooks/EDA/02_eda_e_redes.ipynb, cél. 5 | Avaliar a concentração de pilotos nas top equipes. |
| Betweenness Centrality | 4 | notebooks/EDA/02_eda_e_redes.ipynb, cél. 5 | Identificar os pilotos que atuaram como ponte entre diferentes escuderias. |
| Eigenvector Centrality | 4 | notebooks/EDA/02_eda_e_redes.ipynb, cél. 5 | Medir a influência dos pilotos dentro da rede de elite. |

## Como executar
1. Certifique-se de ter `pandas`, `networkx`, `matplotlib` e `seaborn` instalados (`pip install pandas networkx matplotlib seaborn`).
2. Os dados em CSV já devem estar extraídos na pasta `data/`.
3. Execute as células de `notebooks/ETL/01_coleta_e_limpeza.ipynb` para gerar a base unificada em `data/processed/`.
4. Execute `notebooks/EDA/02_eda_e_redes.ipynb` sequencialmente.

## Resultados
Veja o detalhamento completo em [resultados/README.md](resultados/README.md).

**Destaques:**
- Ferrari (2.439), McLaren (1.923) e Williams (1.676) dominam a rede como *hubs* históricos.
- **Giancarlo Fisichella** obteve o maior Betweenness Centrality na rede projetada de pilotos, sendo o maior "conector" entre escuderias de diferentes eras.
- A rede **não é de núcleos isolados**: as grandes construtoras compartilham talentos entre si ao longo do tempo.

## Limitações e próximos passos
- O dataset cobre somente até 2021. Temporadas mais recentes podem alterar o ranking de centralidade.
- A modelagem atual usa **todas as corridas com pontuação > 0** como critério de "sucesso". Uma variação futura poderia filtrar apenas pódios (top 3) para uma análise mais restrita.
- O próximo passo é adicionar visualizações da rede com `nxviz` no notebook `notebooks/Visualizacao/03_visualizacao_rede.ipynb`.

## Referências
* [Kaggle: Formula 1 Dataset](https://www.kaggle.com/rohanrao/formula-1-world-championship-1950-2020)
