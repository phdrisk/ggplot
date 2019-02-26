# ggplot

 ano customer_state n_ativos receita receita_media    churn <br>
   
 1  2017              1       12   3025.          252. 0.00120 <br>
 2  2017              2       29   6816.          235. 0.00300 <br>
 3  2017              3        9   2764.          307. 0.000900
 4  2017              4        2   1031.          515. 0.000200
 5  2017              5      134  30991.          231. 0.0137  
 6  2017              6       62  14188.          229. 0.00620 
 7  2017              7       75  13209.          176. 0.00770 

### cria diversas colunas contendo no eixo x os estados, no y a receita separados por ano
gplot(ativos, aes(x=customer_state, y=receita_media, fill=ano))+
    geom_bar( stat = "identity") +
    labs(x = "Estado", y = "Numero de Consumidores", title = "Receita Media de Consumidores por Estado") +
    scale_fill_continuous(name = "Ano", labels = c(2017, 2018), breaks = c(2017, 2018)) + 
### cria os labes para cada coluna baseado na receita media
    geom_text(
      aes(label = round(receita_media)),
      position =  position_stack(vjust = 0.8), vjust = 1, color="#ffffff", size=3
    ) 
