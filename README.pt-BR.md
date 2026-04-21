# Classificação de Veículos Utilizando Técnicas Tradicionais e Deep Learning

🇺🇸 [Read in English](README.md) | 🇧🇷 Português

---

## Visão Geral

Este projeto investiga uma tarefa de classificação de imagens de veículos usando tanto **técnicas tradicionais de visão computacional** quanto **modelos de deep learning**. O objetivo é classificar imagens em sete categorias e comparar abordagens com descritores manuais contra modelos com transfer learning e uma CNN personalizada.

O projeto foi desenvolvido com base no **Vehicles Classification** do Kaggle, com **5.590 imagens** distribuídas em **7 classes**: **Auto Rickshaws, Bikes, Cars, Motorcycles, Planes, Ships e Trains**. As imagens foram padronizadas para **224 × 224** e divididas em **70% treino, 15% validação e 15% teste**.

---

## Objetivos Principais

- Construir um baseline com extração tradicional de características e aprendizado de máquina clássico
- Comparar esse baseline com abordagens de deep learning
- Analisar o impacto do data augmentation offline
- Avaliar qual estratégia generaliza melhor para classificação de veículos

---

## Dataset

- **Fonte:** Vehicles classification no Kaggle, disponível no link: https://www.kaggle.com/datasets/mohamedmaher5/vehicle-classification/data
- **Número de classes:** 7
- **Total de imagens:** 5.590
- **Tamanho de entrada:** 224 × 224
- **Treino após augmentation:** 7.824 imagens no pipeline aumentado

---

## Metodologia

### Abordagem Tradicional

O baseline tradicional utiliza descritores visuais manuais e classificadores clássicos:

**Extração de características**
- Histograma de cor em HSV
- HOG (Histogram of Oriented Gradients)
- LBP (Local Binary Patterns)
- Combinações entre os descritores

**Classificadores**
- SVM
- Random Forest
- KNN

### Abordagem com Deep Learning

Foram explorados três modelos principais:

- **MobileNetV2** com transfer learning
- **EfficientNetB0** com transfer learning
- **SmallCNN**, uma CNN personalizada treinada do zero

---

## Pré-processamento

- Redimensionamento com padding para preservar a proporção
- Conversão para RGB
- Normalização dos pixels
- Conversões para HSV e escala de cinza para os descritores manuais
- Pré-processamentos específicos para MobileNetV2 e EfficientNetB0

---

## Data Augmentation

Foi aplicado data augmentation offline apenas no pipeline de treino com transformações como:

- Flip horizontal
- Rotação
- Translação
- Variações leves de escala
- Ruído gaussiano
- Desfoque leve

O pipeline aumentado expandiu o conjunto de treino em aproximadamente **30%**, mantendo a mesma resolução das imagens.

---

## Principais Resultados

- Os modelos de deep learning superaram de forma consistente os métodos tradicionais
- O **EfficientNetB0 treinado no dataset original** obteve o melhor resultado geral, com **98,69% de acurácia**
- O data augmentation clássico **não** melhorou o desempenho e provocou uma pequena queda em vários modelos

---

## Estrutura do Repositório

```text
.
├── Equipe 9 2025-2-BCC-VC-ProjectPresentationTemplate.pdf
├── Grupo_9_2025_2_BCC_VC_ProjectTemplate.ipynb
├── README.md
└── README.pt-BR.md
```

---

## Como Executar

### Opção 1: Google Colab

1. Abra o notebook no Google Colab
2. Envie seu arquivo `kaggle.json` quando solicitado
3. Execute as células na ordem
4. O notebook baixa o dataset diretamente do Kaggle e executa todo o pipeline

### Opção 2: Ambiente Jupyter Local

1. Crie um ambiente Python
2. Instale as dependências necessárias
3. Configure as credenciais do Kaggle
4. Execute o notebook do início ao fim

---

## Arquivos Incluídos

### `Grupo_9_2025_2_BCC_VC_ProjectTemplate.ipynb`
Notebook principal com:
- aquisição do dataset
- pré-processamento
- extração de características manuais
- treinamento de modelos tradicionais
- data augmentation offline
- treinamento e avaliação de deep learning
- gráficos e matrizes de confusão

### `Equipe 9 2025-2-BCC-VC-ProjectPresentationTemplate.pdf`
Apresentação final do projeto com resumo de:
- motivação
- dataset
- metodologia
- resultados quantitativos
- exemplos qualitativos
- conclusões e trabalhos futuros
