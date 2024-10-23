# Retos_clase
Resoliuciòn de los ejercicios de clase
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
> 
> Animalitos_Lago <- filter(especies, habitat == "Lago")
> Animalitos_Lago
  especie habitat tamano peso
1 Ajolote    Lago     30  150
2 Tortuga    Lago     50  500
> Animalitos_Ordenados <- arrange(especies, desc(tamano))
> Animalitos_Ordenados
    especie habitat tamano peso
1 Serpiente  Bosque    150 1000
2   Tortuga    Lago     50  500
3   Ajolote    Lago     30  150
4      Rana     Río     10   25
> 
