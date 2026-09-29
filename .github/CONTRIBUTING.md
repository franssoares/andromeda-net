# Guia de Contribuição - Andromeda-Net

Obrigado por ajudar no **Andromeda-Net**! Sendo este um projeto de disciplina, nossa contribuição é focada no trabalho em equipe de até 3 pessoas.

## Configuração do Ambiente Local
1. Clone este repositório.
2. Certifique-se de ter o Python 3.x instalado.
3. Crie e ative um ambiente virtual (`python -m venv venv`, depois `source venv/bin/activate` ou `venv\Scripts\activate`).
4. Instale as dependências executando `pip install -r requirements.txt`. (O arquivo deve ser mantido atualizado à medida que usamos novas libs do ecossistema de dados).

## Branches e Commits
- Use prefixos claros para novas branches (ex: `analise/betweenness-pilotos`, `dados/etl-kaggle`).
- Commits devem ser descritivos. Adotamos o padrão Conventional Commits (ex: `feat:`, `fix:`, `docs:`, `chore:`).

## Abrindo um Pull Request (PR)
- Sempre abra um PR para integrar funcionalidades importantes à branch `main`.
- O que é revisado antes do merge?
  - A reprodutibilidade do código (o notebook deve rodar completo sem erros).
  - Se a modelagem de rede adicionada justifica nós e arestas (exigência da disciplina).
  - Se a documentação no código (markdown nas células) está legível.
- Pelo menos um outro membro do grupo deve aprovar visualmente e teoricamente o PR antes do merge.
