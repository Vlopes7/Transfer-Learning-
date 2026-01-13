# Transfer Learning com MobileNetV2 - Cats vs Dogs

Este repositório contém um exemplo prático de **Transfer Learning** utilizando a arquitetura **MobileNetV2** pré-treinada na ImageNet para resolver um problema de classificação binária (Gatos vs Cães).

## 📋 Descrição

O objetivo é demonstrar como utilizar um modelo de Deep Learning pré-existente para acelerar o treino e obter alta precisão num novo conjunto de dados, mesmo com poucas épocas de treino. 

O modelo base é configurado como não treinável para manter os pesos aprendidos na ImageNet, sendo adicionadas novas camadas densas no topo para a classificação específica de animais.

## 🚀 Tecnologias Utilizadas

* **Python**
* **TensorFlow / Keras**
* **TensorFlow Datasets (TFDS)**
* **Matplotlib e Numpy** (para visualização e processamento)

## 📊 Dataset

É utilizado o dataset `cats_vs_dogs` do TensorFlow Datasets:
* **Divisão:** 80% para treino e 20% para validação.
* **Pré-processamento:** As imagens são redimensionadas para **160x160** píxeis.

## 🧠 Arquitetura do Modelo

O modelo é construído de forma sequencial com as seguintes camadas:
1.  **Modelo Base:** MobileNetV2 (pesos da ImageNet, sem a camada de topo original).
2.  **GlobalAveragePooling2D:** Para redução da dimensionalidade espacial.
3.  **Dense (128 unidades):** Camada intermédia com ativação ReLU.
4.  **Dropout (0.5):** Camada de regularização para evitar overfitting.
5.  **Dense (1 unidade):** Camada de saída com ativação Sigmoid para a previsão final.

## ⚙️ Configuração de Treino

* **Otimizador:** Adam.
* **Função de Perda:** Binary Crossentropy.
* **Tamanho do Lote (Batch Size):** 32.
* **Épocas:** 3.

## 🖼️ Visualização de Resultados

O notebook inclui uma etapa de visualização que apresenta as previsões do modelo em imagens aleatórias do conjunto de validação, indicando a probabilidade calculada para "Cão" e "Gato", 0 ou 1.

---

**Como utilizar:**
1.  Abra o ficheiro `transfer_learning.ipynb` no **Google Colab**.
2.  Instale a biblioteca `tensorflow-datasets` se necessário.
3.  Execute todas as células para carregar os dados, configurar a arquitetura e treinar o modelo.
