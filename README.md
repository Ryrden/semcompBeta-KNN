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

Como escolher o K?

#### Escolha de K

- O número de vizinhos é o que chamamos de Hiperparâmetro, isto é, parâmetro que é escolhido/definido antes do treinamento do modelo
- Para a maioria das tarefas, não existem hiperparâmetros mágicos que sempre funcionam, sendo necessário testar valores diferentes e descobrir qual funciona melhor para o problema
- Esse processo de teste de hiperparâmetro é realizado utilizando o conjunto de validação

Como esse K influencia ?

![Imagem](https://www.researchgate.net/publication/321554029/figure/fig2/AS:568611275317249@1512578900804/Illustration-of-the-k-nearest-neighbours-kNN-classifier-a-kNN-assigns-a-class-to.png)

Veja que k=3 faz o modelo dizer q é Cinza ao invés de Azul na segunda imagem, mas o dado desejado esta no azul, devemos aumentar o K?

### Observações sobre KNN

O KNN tem resultados rapidos mas treino lento, isso é o que nao queremos, o KNN é apenas didático

- O algoritmo não aprende, ele apenas "memoriza" os dados de treino
- Adia a parte pesada da computação para a fase de classificação
    - Para cada amostra de teste, temos que calcular a distância para todas as amostras de treino
- Classificador não linear, já que não define uma fronteira de decisão com speração linear (exemplo da ultima imagem)
- É importante utilizar pré-processamento de normalização ou padronização dos dados, uma ez que é computada a dist euclidiana entre as amostras

### Compelxidade de treino e teste

- Idealmente, queremos que o teste/inferência seja rápido


## Notas

Jay Alamar Blog - Bom conteúdo sobre dados não estruturados 

A escolha de um K ser impar torna a classificação mais interessante pq haverá uma majoritaria

Exemplo, se K = 2, pode ter 2 classes, mas com K=3 vai ter sempre uma dominante oq melhora a precisão