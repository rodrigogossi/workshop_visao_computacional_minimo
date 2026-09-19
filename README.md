# workshop_visao_computacional_minimo

Repositório enxuto, feito só para o exercício de treinamento ao vivo do
**Workshop de Visão Computacional Aplicada** (UTFPR Dois Vizinhos, set/2026).
Recorte independente do repositório principal
[`treinamentoDL_scripts`](https://github.com/rodrigogossi/treinamentoDL_scripts) —
aqui só entra o essencial pra rodar o notebook rápido, com um `git clone` leve.

## Conteúdo

- **[`imagens_entrada/`](imagens_entrada)** — as 5 fotos de carros usadas no exercício, antes de qualquer rotulagem.
- **[`dataset/`](dataset)** — export do [Label Studio](https://labelstud.io/) no formato YOLO: cada imagem com seu `.txt` de caixa normalizada, classe única `placa`.
- **[`treinamento_workshop_ao_vivo.ipynb`](treinamento_workshop_ao_vivo.ipynb)** — notebook para Google Colab. Clona este próprio repositório, divide o mini-dataset em treino/val, treina um YOLOv8n por 100 épocas (~1-2 min) e mostra uma predição.
- **[`resultados_treino/`](resultados_treino)** — resultado de uma execução real do notebook acima, mantido aqui como referência:
  - `treino/weights/best.pt` e `last.pt` — pesos treinados (YOLOv8n, 100 épocas, mAP50 = 99,5%, mAP50-95 = 69,7% no conjunto de validação de 1 imagem — números altos porque o dataset é propositalmente minúsculo, não um resultado "de produção").
  - `treino/results.png`, `confusion_matrix.png`, `train_batch*.jpg`, `val_batch0_pred.jpg` — gráficos e amostras gerados automaticamente pelo Ultralytics durante o treino.
  - `predicoes/` — predição do modelo treinado sobre as 5 imagens do mini-dataset.

## Como usar

Abra o notebook direto no Colab a partir do GitHub (assim que este repositório estiver publicado) e rode as células em ordem — a primeira célula instala as dependências, a segunda clona este repositório.

## Contexto

Este exercício é a "prova de conceito" que antecede o treinamento real do
workshop (feito com 25 mil imagens). O objetivo aqui não é robustez — é
provar que o fluxo rotular → dividir → treinar → prever funciona de ponta
a ponta, ao vivo, em menos de 2 minutos por pessoa.
