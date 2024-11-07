## Retos_clase
# 1. Filtrar y manipular marcos de datos
> library(dplyr)
> especies <- data.frame(
+     especie = c("Ajolote", "Rana", "Serpiente", "Tortuga"),
+     habitat = c("Lago", "Río", "Bosque", "Lago"),
+     tamano = c(30, 10, 150, 50),
+     peso = c(150, 25, 1000, 500)
+ )
> 
> especies 
    especie habitat tamano peso
1   Ajolote    Lago     30  150
2      Rana     Río     10   25
3 Serpiente  Bosque    150 1000
4   Tortuga    Lago     50  500
# - Filtrar todas las especies que viven en un lago.
> Animalitos_Lago <- filter(especies, habitat == "Lago")
> Animalitos_Lago
  especie habitat tamano peso
1 Ajolote    Lago     30  150
2 Tortuga    Lago     50  500
# - Ordenar los resultados por tamaño (de mayor a menor).
> Animalitos_Ordenados <- arrange(especies, desc(tamano))
> Animalitos_Ordenados
    especie habitat tamano peso
1 Serpiente  Bosque    150 1000
2   Tortuga    Lago     50  500
3   Ajolote    Lago     30  150
4      Rana     Río     10   25

# 2. Generación de gráficos
# - Crear un gráfico de dispersión entre Sepal.Length y Sepal.Width, y colorear los puntos según la especie.
> install.packages("ggplot2")
> library(ggplot2)
> install.packages("gcookbook")
> library(gcookbook)
> iris[, c("Sepal.Length", "Sepal.Width")]
> ggplot(iris, aes(x=Sepal.Length, y=Sepal.Width)) + geom_point()

![Captura de Pantalla 2024-11-04 a la(s) 20 34 40](https://github.com/user-attachments/assets/6306db3b-c14b-429e-b4fb-be0366d964d0)

> iris[, c("Sepal.Length", "Sepal.Width", "Species")]
> ggplot(iris, aes(x=Sepal.Length, y=Sepal.Width, colour=Species)) + geom_point()
![Captura de Pantalla 2024-11-04 a la(s) 20 35 23](https://github.com/user-attachments/assets/19599123-bce3-46d5-bf22-95a0b1e31778)

