# ggplot
### TABELA

    ano customer_state n_ativos receita receita_media    churn
    2017              1       12   3025.          252. 0.00120 
    2017              2       29   6816.          235. 0.00300 
    2017              3        9   2764.          307. 0.000900
    2017              4        2   1031.          515. 0.000200
    2017              5      134  30991.          231. 0.0137  
    2017              6       62  14188.          229. 0.00620 
    2017              7       75  13209.          176. 0.00770 

### cria diversas colunas contendo no eixo x os estados, no y a receita distribuidos por ano
    gplot(ativos, aes(x=customer_state, y=receita_media, 
    # fill=ano) --> fica um tom de azul
    # fill= as. factor(ano)) --> estabele a quantidade de cores do ano
    ) + 
    ###### fill = ano 
    geom_bar( stat = "identity") + 
      labs(x = "Estado", y = "Numero de Consum", title = "Receita Media de Consum por Estado") +
      scale_fill_continuous(name = "Ano", labels = c(2017, 2018), breaks = c(2017, 2018)) + 
    ###### fill = as.factor(ano) 
    geom_bar( stat = "identity") + 
      labs(x = "Estado", y = "Numero de Consum", title = "Receita Media de Consum por Estado") +
      labs(fill="ano")+
       
     
### cria os labes para cada coluna baseado na receita media
    geom_text(
      aes(label = round(receita_media)),
      position =  position_stack(vjust = 0.8), vjust = 1, color="#ffffff", size=3
    ) 
    
### colocar valores na barra
- https://dataunirio.github.io/GALERIA_DE_GRAFICOS/Barras.html
- https://italocegatta.github.io/os-graficos-que-explicam-nossos-dados-barras/

### pie
 - https://plot.ly/r/pie-charts/
