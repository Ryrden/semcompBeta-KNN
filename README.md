# Minicurso Semcomp Beta 2023

# Objetivo 

aplicar um algoritmo KNN para reconhecimento de dígitos, esta técnica e chamada de m-list


# Conceitos

## Dados

- Dados estruturados (são geralmente tabelas)

- Dados não estruturados (Imagens, textos, áudios, ...)
    - Imagens: São matrizes de cores que variam de 0 a 255 

- Dados semi-estruturados (Tabela + imagens + etc...)

## Modelos de Machine Learning

O que muda é a presença de um rotulo

- Supervisionado: Exemplo, uma lista de imagens com um rotulo do que são (Cavalo)
    - Classificação: Rotulo é binario
    - Regressão: Rotulo é um numero real entre um intervalo
- Não supervisionado: Exemplo, uma lista de imagens com descrição (possui 4 patas, carnivoro, etc)
    - Clustering: Agrupamento de dados, não há rotulos, o ojetivo é identificar grupos
    - Dimesionality Reduction: Dado uma tabela com N colunas, reduzir a sua dimensão para duas é encontrar as 2 colunas que são relevantes o suficiente para diferenciar cada linha


## Classificação de Dígitos


Reconhecer um dígito escrito a mão com um modelo

### Desafios

- Onde na imagem esta escrito?
- Se o papel é uma cor diferente, ele vai conseguir reconhecer os digitos
- O modelo consegue reconhecer variações

## Dataset MNIST

- É um ponto de partida para muitos dos estudantes que buscam se aventurar em áreas de ciências de dados e aprendizado de máuina
- Corresponde a uma base de imagens de 28x28 em escala de cinza de dígitos de 0 à 9, escritos à mão

![imagem](https://datasets.activeloop.ai/wp-content/uploads/2019/12/MNIST-handwritten-digits-dataset-visualized-by-Activeloop.webp)


## Modelo K-Nearest Neighbors

- K-Vizinhos mais Próximos
- Simples e prático algoritmo de classificação
    - Com bas nos atributos de dados, iremos predizer a classe de uma amostra
- Os dados devem ser TODOS numéricos
    - Dados caregóricos devem ser transformados
- Hipótese: exemplos de uma mesma classe estão localizados próximos no espaço


### Localização Espacial

- Uma amostra se localiza no espaço por meio de um ponto, indicado por meio de suas coordenadas

Se faz necessário definir uma distancia entre os pontos

### Proximidade entre instâncias

- Distância Euclidiana
- Distância de Manhatam

A distancia é adaptada conforme a necessidade

## Algoritmo

### 1NN

1. Calcular a distância do exemplo de teste para cada instância do conjunto de treino
2. Descobrir qual o elemento do treino está mais próximo da instância de teste
3. Retornar a classe que o exemplo de treino mais próximo

### KNN

1. Calcular a distância do exemplo de teste para cada instância do conjunto de treino
2. Descobrir quais k elementos do treino estão mais próximos da instância de teste
3. Dentre os k exemplos mais próximos descobrir a classe mais frequente
4. Retornar a classe mais frequente enre os vizinhos mais próximos

