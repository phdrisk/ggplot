# ggplot
### TABELA

    ano customer_state n_ativos receita receita_media    churn
    2017              1       12   3025.          252. 0.00120 <br>
    2017              2       29   6816.          235. 0.00300 <br>
    2017              3        9   2764.          307. 0.000900<br>
    2017              4        2   1031.          515. 0.000200<br>
    2017              5      134  30991.          231. 0.0137  <br>
    2017              6       62  14188.          229. 0.00620 <br>
    2017              7       75  13209.          176. 0.00770 <br>

### cria diversas colunas contendo no eixo x os estados, no y a receita distribuidos por ano
    gplot(ativos, aes(x=customer_state, y=receita_media, fill=ano)) +
    geom_bar( stat = "identity") + <
     labs(x = "Estado", y = "Numero de Consum", title = "Receita Media de Consum por Estado") +
     scale_fill_continuous(name = "Ano", labels = c(2017, 2018), breaks = c(2017, 2018)) + 
### cria os labes para cada coluna baseado na receita media
    geom_text(
      aes(label = round(receita_media)),
      position =  position_stack(vjust = 0.8), vjust = 1, color="#ffffff", size=3
    ) 
