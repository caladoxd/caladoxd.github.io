---
title: "Kaggle Titanic Project"
date: 2018-01-28
tags: [kaggle, titanic, data science]
header:
  image: "/images/zakim.jpg"
excerpt: "Data Science, Kaggle, Titanic Challenge"
mathjax: "true"
---

# H1 Desafio inicial do Kaggle para machine learning

## H2 Titanic: Machine Learning from Disaster

### H3 Resultado: top 5% melhores

Fonte: dados retirados do desastre do titanic, com informações coletadas sobre os passageiros e quais sobreviveram.
Após a análise dos dados para determinar as correlações, foi elaborado um modelo usando python para prever se um passageiro sobrevive ou não, baseado nos dados do banco de testes.


[Código fonte](https://github.com/caladoxd/Kaggle-Titanic)


Python code block:
```python
    import numpy as np

    def test_function(x, y):
      z = np.sum(x,y)
      return z
```

R code block:
```r
library(tidyverse)
df <- read_csv("some_file.csv")
head(df)
```

Here's some inline code `x+y`.

Here's an image:
<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/linsep.jpg" alt="linearly separable data">

