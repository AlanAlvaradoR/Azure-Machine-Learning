# Azure-Machine-Learning
Resolución de algortimo por medio de Machine Learning de un negocio de renta de bicicletas

![Logo de Machine Learning](https://github.com/AlanAlvaradoR/Azure-Machine-Learning/blob/main/imagenes/ML.png)

## Requisitos

- Cuenta de [Azure](https://portal.azure.com/) con suscripción activa
- Computadora con Windows, Linux o MacOs

---------------------------------------------------------

## Pasos

1. Se inicia sesión en la página de [Machine Learning de Azure](https://ml.azure.com/home)

2. Se crea una nueva área de trabajo.

3. Se llenan los parámetros requeridos (Nombre, suscripción, grupo de recursos y región) y se da click en "crear"

*Nota: se puede crear un área de trabajo de ML desde el portal de Azure también, pero en este caso como no se requiere configurar la red ni ningún parámetro importante se crea más fácilmente y con menos requerimientos desde el machine learning studio*

4. Una vez creada el área de trabajo, se entra en la misma, se debe ver una pestaña como la siguiente

![Creació área de trabajo ML](https://github.com/AlanAlvaradoR/Azure-Machine-Learning/blob/main/imagenes/ML1.PNG)

5. En el menú lateral izquierdo se selecciona "proceso"

6. Se selecciona "Nuevo" en instancia de proceso (Para más fácil de entender es una nueva máquina virtual)

7. Se rellenan los campos requeridos: Nombre del proceso, región (bloqueada por el grupo de recursos), tipo de máquina virtual(GPU es más potente pero más cara) y tamaño. Al finalizar se da click en "crear".

8. EN el menú lateral izquierdo se da click en "datos".

9. Se selecciona "crear" y luego "de archivo web"

10. En el nuevo menú se pega el siguiente link en el apartado de "URL web"

```Bash
https://aka.ms/bike-rentals
```
11. Se le coloca un nombre, tipo de datos tabular ya que es un archivo de excel, se da una descripción y se da click en "siguiente".

12. En la siguiente pestaña se indica el delimitador (en este caso por ser un archivo CSV está delimitado por comas y se puede corroborar abriendolo con VSCode), el encabezado de columna (en este caso solo el primer archivo tiene encabezados) y lo demás se deja igual. Se da click en "siguiente".

13. En la siguiente pestaña solo corroboramos que "path" este deseleccionado y damos en "siguiente".

14. En la siguiente venta se da click en "crear". Esperamos a que se cree.

15. En el menú lateral izquierdo se selcciona "proceso"

16. Se selecciona "clústeres de proceso" y se da click en "nuevo"

17. Se le coloca una ubicación (misma que el grupo de recursos), se selecciona dedicado, se selecciona CPU y se elige una opción de tamaño de máquina virtual. Se da click en "siguiente"

18. Se le coloca un nombre, se establece el número mínimo de nodos en cero y el número máximo en el máximo que deje seleccionar. Se da click en "crear".

19. Esperamos a que se complete la creación.

20. En el menú lateral izquierdo se selecciona "ML Automatizado"

21. Se da click en "Nuevo trabajo de ML Automatizado"

22. Se selecciona el archivo de bicis que creamos anteriormente y se da click en "siguiente"

23. En "nombre del experimento" se selecciona "crear"

24. Se le coloca un nombre, en columna destino se selecciona la etiqueta (lo que se quiere predecir, en este caso el número de rentas o "rentals"), se establece tipo de proceso en "clúster de proceso" y en "seleccionar el clúster de proceso" colocamos el clúster que creamos anteriormente. Se da click en "siguiente".

25. Se selecciona en "regresión".

*NOTA: Dependiendo el tipo de predicción se pueden usar alguno de los otros modelos, para saber cual usar consultar [este link](https://docs.microsoft.com/en-us/azure/machine-learning/algorithm-cheat-sheet)*

26. Se da click en "siguiente"

27. Se da click en "finalizar"

28. Esperar a que termine (puede durar bastante tiempo)
