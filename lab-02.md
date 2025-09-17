Lab 02 - Plastic waste
================
Laeticia Tremblay
17 septembre 2025

## Chargement des packages et des données

``` r
library(tidyverse) 
```

``` r
plastic_waste <- read_csv("data/plastic-waste.csv")
```

Commençons par filtrer les données pour retirer le point représenté par
Trinité et Tobago (TTO) qui est un outlier.

``` r
plastic_waste <- plastic_waste %>%
  filter(plastic_waste_per_cap < 3.5)
```

## Exercices

### Exercise 1

``` r
ggplot(data = plastic_waste, 
       aes (x = plastic_waste_per_cap)) +
  geom_histogram(binwidth = 0.2) +
    facet_wrap(~ continent)
```

![](lab-02_files/figure-gfm/plastic-waste-continent-1.png)<!-- -->

Certains continents ont une quantité de déchets produits par jour par
habitant plus élevée que d’autre. En effet, l’Afrique est un très petit
producteur de déchets plastiques. La production de déchets plastiques
par habitant se ressemble en Amérique du Sud, en Europe et en Océanie,
où la majorité des habitants en produisent environ 0,25 kg par jour et
où très peu en produisent plus que ça. Finalement, l’Asie et l’Amérique
du Nord sont les plus gros producteurs de déchets plastiques. Une
majorité en produit 0,25 kg par jour et plusieurs en prodsuisent plus.

### Exercise 2

``` r
ggplot(data = plastic_waste, 
       aes (x = plastic_waste_per_cap)) +
  geom_density(adjust = 1) 
```

![](lab-02_files/figure-gfm/plastic-waste-density-1.png)<!-- -->

``` r
ggplot(data = plastic_waste, 
       aes (x = plastic_waste_per_cap, color = continent)) +
  geom_density(adjust = 1) 
```

![](lab-02_files/figure-gfm/plastic-waste-density-2.png)<!-- -->

``` r
ggplot(data = plastic_waste, 
       aes (x = plastic_waste_per_cap, color = continent, fill = continent)) +
  geom_density(adjust = 1) 
```

![](lab-02_files/figure-gfm/plastic-waste-density-3.png)<!-- -->

``` r
ggplot(data = plastic_waste, 
       aes (x = plastic_waste_per_cap, color = continent, fill = continent)) +
  geom_density(adjust = 1, alpha = 0.4) 
```

![](lab-02_files/figure-gfm/plastic-waste-density-4.png)<!-- -->

C’est parce que lorsqu’on écrit dans la section aes, le réglage dépend
de la donnée et donc change avec elle. Par exemble, la couleur change
pour chaque continent. Quand on écrit dans la section geom_density, le
paramètre reste le même pour chaque donnée. Ainsi, la transparence est
identique pour chaque continent.

### Exercise 3

Boxplot:

``` r
# insert code here
```

Violin plot:

``` r
# insert code here
```

Réponse à la question…

### Exercise 4

``` r
# insert code here
```

Réponse à la question…

### Exercise 5

``` r
# insert code here
```

``` r
# insert code here
```

Réponse à la question…

## Conclusion

Recréez la visualisation:

``` r
# insert code here
```
