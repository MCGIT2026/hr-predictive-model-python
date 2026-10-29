# Projeto RH — Grupo 07 — versão 3.0

**Data desta revisão:** 21 de outubro de 2026  
**Problema:** prever se um candidato declara procurar mudar de emprego (`procura_mudanca_emprego`).

Esta é uma revisão posterior à entrega original, preparada como projeto autónomo. Contém três modelos preditivos — regressão logística, árvore de decisão e Random Forest — comparados com um `DummyClassifier` como baseline. Não contém a apresentação PowerPoint.

## Origem dos dados e alcance

O ficheiro `Data/input/Dados_RH_Mudanca_Emprego.csv` foi fornecido/autorizado pela professora como alternativa à recolha própria, conforme confirmação do grupo. O grupo não fez *web scraping* nem recolha por API. A origem anterior ao fornecimento, a licença, a data e o método de amostragem não constam do CSV. O alvo representa intenção declarada, não uma saída efetiva de emprego.

## Organização

| Ficheiro/pasta | Conteúdo |
| --- | --- |
| `01_P_business_understanding.ipynb` | Objetivo, questões de negócio, hipóteses, métricas, critérios e limitações. |
| `02_P_data_understanding.ipynb` | Qualidade, distribuição e padrões exploratórios dos dados. |
| `03_P_data_preparation.ipynb` | Separação treino/teste, preparação e exportações. |
| `04_P_modeling.ipynb` | Baseline e comparação dos três modelos por validação cruzada no treino. |
| `05_P_evaluation.ipynb` | Avaliação do vencedor, critérios de sucesso, erros e variáveis relevantes. |
| `06_P_deployment.ipynb` | Demonstração de previsão em lote e exportação de resultados. |
| `preparacao_rh.py` | Função de preparação usada pelos pipelines. |
| `Data/input/` | CSV original fornecido/autorizado. |
| `Data/analytics/` | Gráficos produzidos pelos notebooks. |
| `Data/output/` | Divisões de dados, comparação, avaliação, previsões e relatórios de validação. |
| `Data/models/` | Pipeline final e metadados. |

## Como executar

Foi validado com Python 3.14.7 e as versões em `requirements.txt`. A partir da pasta deste projeto, instalar as dependências com `python -m pip install -r requirements.txt`, iniciar Jupyter e executar os notebooks por ordem, de 01 a 06, usando essa instalação de Python. Para verificar a consistência dos ficheiros exportados, executar `python validar_entrega.py` na mesma pasta.

Os notebooks incluídos já estão executados e os ficheiros em `Data/` foram gerados de novo nesta versão. Uma nova execução pode atualizar carimbos de data e recriar gráficos/exportações.

## Resultado resumido

O conjunto tem 19 158 registos. A separação estratificada usa 15 326 para treino e 3 832 para teste. O modelo foi escolhido **pela média do F1 da classe Sim em cinco folds de validação cruzada no treino**, com limiar de classificação 0,50 predefinido. Não se escolheu o modelo pelos resultados no teste.

| Candidato | F1 médio na validação cruzada |
| --- | ---: |
| Baseline | 0,000 |
| Regressão logística | 0,466 |
| Árvore de decisão | 0,611 |
| Random Forest | **0,618** |

O Random Forest foi o selecionado. No teste desta versão, obteve **recall 0,746**, **F1 0,605** e **ROC-AUC 0,785**, acima das metas numéricas pedagógicas (0,60; 0,50; 0,75). As métricas e a matriz de confusão exatas estão em `Data/output/RH_Mudanca_Emprego_resumo_validado.json`.

