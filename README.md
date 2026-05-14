# QCA_problemas_sociales
En este trabajo se muestra una tabla de la verdad, donde se analiza que provoca los problemas sociales 

### Formulas

install.packages(readxl)
library(readxl)
datos<-read_excel("qcar .xlsx")
list.files()
View(datos)

### Tabla de Verdad

 incl.cut. Un puntaje de 1 indica que la configuración de condiciones es suficiente para el resultado
install.packages("QCA")
install.packages("SetMethods")
library(SetMethods)
library(QCA)
summary(datos)
tv <- truthTable(data = datos, outcome = "Resultados", conditions = c("A,B,C,D"), incl.cut= 1, complete=TRUE)
tv

##### Condiciones Necesarias 
QCAfit(x = datos[, c("A", "B", "C","D")], y = datos$Resultados, necessity = TRUE)
##### Minimización Booleana
minimize(input = tv, include = "all", details = TRUE)

### Excel
[qcar.xlsx](https://github.com/user-attachments/files/27744153/qcar.xlsx)

### Resultados

<img width="861" height="532" alt="image" src="https://github.com/user-attachments/assets/b25607bb-1c32-41fd-b1a0-ee964f07915b" />
<img width="665" height="392" alt="image" src="https://github.com/user-attachments/assets/817eee35-241a-4844-82ed-6697b4155364" />

### Conclusiones
La minimización booleana identificó cuatro configuraciones causales suficientes para explicar el resultado analizado. Esto sugiere la existencia de equifinalidad, es decir, múltiples combinaciones de condiciones pueden conducir al mismo resultado. Todas las configuraciones presentaron altos niveles de consistencia (1.000), indicando una fuerte relación entre las combinaciones causales y el resultado observado.


