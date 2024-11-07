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

# 3. Agrupar las calificaciones por estudiante y calcular el promedio de calificación por cada uno.
> calificaciones <- data.frame( estudiante = c("Ana", "Carlos", "Lucía", "Jorge", "Ana", "Carlos", "Lucía", "Jorge"), asignatura = c("Matemáticas", "Matemáticas", "Matemáticas", "Matemáticas", "Historia", "Historia", "Historia", "Historia"), calificacion = c(95, 85, 92, 88, 78, 82, 85, 90) )
> > promedio <- calificaciones %>% group_by(estudiante) %>% summarise(promedio = mean(calificacion))
> print(promedio)

# 4.  Crear una nueva columna con las alturas en metros y mostrar el nuevo data frame
> alturas <- data.frame(
+     nombre = c("Laura", "Pedro", "Sara", "Miguel"),
+     altura_cm = c(160, 175, 150, 180)
+ )
> alturas$altura_m <- alturas$altura_cm / 100
> print(alturas)

# 5. Crear un gráfico de barras para visualizar las ventas mensuales.
> ventas <- data.frame(
  mes = c("Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio"),
  ventas = c(12000, 15000, 13000, 16000, 17500, 14000)
)
> library(ggplot2)
> ggplot(ventas, aes(x = mes, y = ventas)) + geom_bar(stat = "identity", fill = "skyblue") + labs(title = "Ventas mensuales", x = "Mes", y = "Ventas")
> ![Captura de Pantalla 2024-11-06 a la(s) 22 02 13](https://github.com/user-attachments/assets/03be8767-63b0-4bd5-afae-68885dd1e045)


# 6. Calcular el total de ingresos por producto (precio * cantidad vendida) y agregarlo como una nueva columna.
> productos <- data.frame(
+     producto = c("A", "B", "C", "D"),
+     precio = c(20, 35, 50, 10),
+     cantidad_vendida = c(100, 200, 150, 250)
+ )
> 
> productos <- productos %>%
+     mutate(ingresos = precio * cantidad_vendida)
> print(productos)
# 7. Crear un gráfico de caja (boxplot) que muestre la distribución de millas por galón (mpg) en función del número de cilindros (cyl).
> data(mtcars)
> mtcars
> ggplot(mtcars, aes(x = as.factor(cyl), y = mpg)) + geom_boxplot(fill = "lightblue") + labs(title = "Distribución de millas por galón según el número de cilindros", x = "Número de cilindros", y = "Millas por galón (mpg)")
> ![Captura de Pantalla 2024-11-06 a la(s) 22 05 44](https://github.com/user-attachments/assets/7171e6a5-f000-4d84-acbb-68f4f3cf09bc)
