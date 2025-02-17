# Projeto de Transfer Learning em Python

Este projeto utiliza Transfer Learning com a rede pré-treinada **MobileNetV2** para classificar imagens de gatos e cachorros usando o dataset **Cats vs Dogs** do [TensorFlow Datasets](https://www.tensorflow.org/datasets/catalog/cats_vs_dogs). O código foi desenvolvido no ambiente Google Colab com suporte para GPU.

---

## **Objetivo**

Demonstrar como aplicar Transfer Learning em um problema de classificação binária, utilizando o dataset Cats vs Dogs e a arquitetura MobileNetV2.

---

## **Recursos Utilizados**

- **Linguagem:** Python
- **Bibliotecas:**
  - TensorFlow 2.x
  - TensorFlow Datasets (TFDS)
  - Keras para construção do modelo
- **Modelo Base:** MobileNetV2 (pré-treinada com ImageNet)
- **Ambiente:** Google Colab com suporte a GPU
- **Dataset:** Cats vs Dogs (disponível via TensorFlow Datasets)

---

## **Configuração**

1. **Pré-requisitos**
   - Conta no [Google Colab](https://colab.research.google.com/).
   - Conhecimento básico de Python e Machine Learning.
   - GPU habilitada no Google Colab:
     - Vá em **Ambiente de execução** > **Alterar tipo de ambiente de execução** > **Acelerador de hardware** > **GPU**.

2. **Dependências**
   O código importa automaticamente as bibliotecas necessárias, como TensorFlow e TensorFlow Datasets. Certifique-se de ter TensorFlow >= 2.0 instalado.

---

## **Estrutura do Projeto**

1. **Carregamento do Dataset:**
   - O dataset Cats vs Dogs é carregado diretamente do TensorFlow Datasets.
   - É dividido em 80% para treino e 20% para validação.

2. **Pré-processamento:**
   - As imagens são redimensionadas para 224x224 pixels.
   - Os valores dos pixels são normalizados (0 a 1).

3. **Modelo:**
   - Utiliza a arquitetura MobileNetV2 como base.
   - Camadas superiores foram adicionadas para customização:
     - **GlobalAveragePooling2D** para reduzir dimensões espaciais.
     - **Dropout** para evitar overfitting.
     - Camadas densas para classificação.

4. **Treinamento:**
   - O modelo é treinado por 10 épocas.
   - Métricas utilizadas: `loss` e `accuracy`.

5. **Inferência:**
   - Possibilidade de carregar uma imagem nova e prever se é um gato ou cachorro.

---

## **Como Executar**

1. Abra o arquivo **PROJETO_DE_TRANSFER_LEARNING_EM_PYTHON.ipynb** no Google Colab.
2. Execute todas as células do notebook, seguindo a ordem.
3. Para testar com suas imagens:
   - Faça upload de uma imagem clicando em **Choose File** na interface Colab.
   - A última célula do código realiza a previsão.

---

## **Exemplo de Uso**

### **Treinamento**
Após executar o notebook, o modelo será treinado por 10 épocas e exibirá as métricas de treino e validação:

```bash
Epoch 1/10
125/125 [==============================] - 12s 82ms/step - loss: 0.4212 - accuracy: 0.8050 - val_loss: 0.2891 - val_accuracy: 0.8746
...
