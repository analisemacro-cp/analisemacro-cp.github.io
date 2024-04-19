---
title: "A gramática dos gráficos"
excerpt: "Este é um tutorial sobre a biblioteca plotnine <br/><img src='/images/graficos.png'>"
collection: portfolio
---

# Introdução

A etapa de visualização de dados refere-se a uma parte fundamental da análise de dados, pois permite não somente compreender os dados que estamos analisando, mas como também é uma ferramenta útil para explanar os resultados encontrados. Mas qual a forma mais fácil de construir um gráfico, como podemos melhorar a produtividade nesta tarefa? É onde podemos aplicar a gramática dos gráficos e construir com a biblioteca plotnine no Python.

# Gramática dos Gráficos

A ideia da "gramática dos gráficos" foi popularizada por Leland Wilkinson em seu livro "The Grammar of Graphics", publicado em 1999. Neste livro, Wilkinson apresenta uma abordagem teórica para a criação de gráficos estatísticos, propondo uma estrutura unificada para representar uma ampla variedade de gráficos estatísticos e de visualização de dados.

O termo se refere aos elementos e princípios fundamentais que constituem um gráfico. Assim como a gramática de uma língua ajuda a organizar e comunicar informações de maneira clara e coerente, a gramática dos gráficos faz o mesmo para representações visuais de dados.

Para construir um gráfico, conforme Wilkinson, deve-se basear nos seguintes componentes: 

  - Dados: Todo gráfico começa com dados. A escolha dos dados certos é fundamental para a criação de uma visualização significativa.

  - Atributos visuais (aesthetics): A gramática dos gráficos identifica esses atributos e como eles podem ser mapeados para os dados.
  
  - Geometrias: As geometrias são as formas visuais usadas para representar os dados, como pontos, linhas, barras e áreas.
    
  - Sinais estatísticos: Sinais estatísticos, como médias, medianas e desvios padrão, podem ser adicionados aos gráficos para fornecer informações adicionais sobre os dados.       
    
  - Facetas: As facetas são usadas para dividir os dados em subconjuntos e representá-los em painéis separados. Isso pode ser útil para explorar padrões em dados multidimensionais.

  - Coordenadas: As coordenadas definem como os dados são mapeados nos elementos visuais. Deve ser cartersiano ou polar?
  
  - Temas: Descreve toda a parte não relacionada aos dados do gráficos.

## ggplot2 vs. plotnine

A gramática dos gráficos ganhou grande destaque em aplicações de análise de dados, e é impossível não mencionar que foi popularizada por Hadley Wickham com a criação do pacote ggplot2 na linguagem de programação R.

O ggplot2 revolucionou a visualização de dados na linguagem, seguindo a abordagem da gramática dos gráficos, onde os gráficos são construídos a partir de camadas (layers), geometrias (geoms) e mapeamentos estéticos (aesthetics).

Na comunidade do Python, houve a criação de bibliotecas bastante conhecidas, como matplotlib e seaborn. Entretanto, elas não foram tão difundidas no contexto da aplicação da gramática dos gráficos. Esse papel foi desempenhado pelo plotnine, uma biblioteca inspirada (ou mesmo uma cópia perfeita para o Python) do ggplot2.

O plotnine permite a construção de gráficos adicionando camadas, geometrias e mapeamentos estéticos. Isso facilita a criação de visualizações complexas e personalizadas.

## Passo 01: Instalar bibliotecas

Vamos agora realizar o procedimento de construir gráficos usando o plotnine no Python. Para tanto, é necessário instalar e importar os módulos da biblioteca.

```python
# !pip install plotnine
import plotnine as p9
```

## Passo 02: dados de exemplo

Vamos importar os dados `mtcars` que contém várias características de carros, como cilindros, cavalos de potência, consumo de combustível e muito mais.

```python
# Importa os dados do módulo data
from plotnine.data import mtcars

# Exibe o dataframe
mtcars.head()
```

## Passo 03: criando o gráfico com o plotnine

Com os dados em mãos, devemos definir cada etapa do processo de criação do gráfico conforme a gramática dos gráficos usando o plotnine. Primeiro, devemos abrir o parêntese `()` e definir toda a construção do gráfico em seu interior. Definimos os dados, inserindo com a função principal `p9.ggplot()` o dataframe `mtcars` e mapeamos os eixos x e y com a função `p9.aes()`. Lembramos que aqui as camadas são "somadas", ou seja, juntadas pelo símbolo +.

```python
(p9.ggplot(mtcars) + 
  p9.aes(x = "wt", y = "mpg")
  )
```

![graficos](/images/graficos.png)

....
