# quantregRanger

Provides the quantile regression for the [**ranger**](https://github.com/imbs-hl/ranger) package. 
There is now also a possibility for quantile regression directly in the [**ranger**](https://github.com/imbs-hl/ranger) package which I can recommend to use. 

## Installation

    install.packages("quantregRanger")
    devtools::install_github("PhilippPro/quantregRanger")   

## Usage
Quickstart:

    library(quantregRanger)
    y = rnorm(150)
    x = cbind(y + rnorm(150), rnorm(150))
    data = data.frame(x,y)
    mod = quantregRanger(y ~ ., data = data, params.ranger = list(mtry = 2))
    predict(mod, data = data[1:5, ], quantiles = c(0.1, 0.5, 0.9))
