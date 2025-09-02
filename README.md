# Classificação de Imagens Histopatológicas utilizando Transfer Learning com ResNet-50

Este repositório contém um Jupyter Notebook que detalha o processo de criação e treinamento de um modelo de classificação de imagens para diagnosticar câncer de mama a partir de imagens histopatológicas.

## 🎯 Objetivo do Projeto

O objetivo principal é desenvolver um modelo de Deep Learning capaz de classificar imagens histopatológicas do dataset público [BreakHis](https://www.kaggle.com/datasets/ambarish/breakhis) em duas categorias: **benigno** e **maligno**.

## 🛠️ Metodologia

A técnica central utilizada é o **Transfer Learning**, que aproveita o conhecimento de uma rede neural profunda já treinada em um grande volume de dados.

-   **Arquitetura Base:** ResNet-50, pré-treinada no dataset ImageNet.
-   **Pipeline de Treinamento:** O processo é dividido em duas fases estratégicas:
    1.  **Treinamento do Classificador:** Inicialmente, as camadas extratoras de características (convolucionais) da ResNet-50 são "congeladas". Apenas a nova camada de classificação, adicionada ao final da rede, é treinada. Isso permite uma adaptação rápida e estável do modelo ao novo dataset.
    2.  **Ajuste Fino (Fine-Tuning):** Após a fase inicial, toda a rede é "descongelada". O modelo completo é então re-treinado com uma taxa de aprendizado (*learning rate*) muito baixa, permitindo um ajuste sutil dos pesos para especializar a rede no domínio específico das imagens histopatológicas.

-   **Pré-processamento e Data Augmentation:** Foram aplicadas técnicas de aumento de dados (rotações, flips, etc.) para aumentar a diversidade do conjunto de treinamento e melhorar a capacidade de generalização do modelo.

## 📊 Avaliação

A performance do modelo é avaliada em um conjunto de teste separado, utilizando métricas padrão de classificação:
-   Relatório de Classificação (Precisão, Recall, F1-Score)
-   Matriz de Confusão

## 🚀 Como Usar

1.  Clone este repositório.
2.  Abra o notebook `Classificação de Imagens Histopatológicas utilizando Transfer Learning com ResNet-50.ipynb` no Google Colab ou em um ambiente Jupyter local.
3.  Execute as células em sequência para treinar e avaliar o modelo.

Ao final da execução, o modelo treinado será salvo em disco para futuras aplicações de inferência.
