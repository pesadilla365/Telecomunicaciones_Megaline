# Telecomunicaciones_Megaline
Análisis de datos para un operador de telecomunicaciones: comparación del comportamiento de uso e ingresos entre dos planes de prepago, con pruebas de hipótesis estadísticas.

## Descripción del proyecto

Megaline, un operador de telecomunicaciones, ofrece a sus clientes dos tarifas de prepago: Surf y Ultimate. El departamento comercial necesita saber cuál de las dos tarifas genera más ingresos para poder ajustar el presupuesto de publicidad de forma más eficiente.

A partir de una muestra de 500 clientes con datos de llamadas, mensajes de texto y uso de internet durante 2018, se realizó un análisis completo para determinar qué plan es más rentable para la empresa y describir el comportamiento de los usuarios de cada uno.

El proceso incluyó:


- Preprocesamiento de datos: revisión y limpieza de cinco tablas (usuarios, llamadas, mensajes, uso de internet y planes), conversión de tipos de datos (fechas a datetime), y verificación de duplicados y valores ausentes.
- Reglas de facturación: aplicación de las reglas específicas de Megaline, como el redondeo hacia arriba de la duración de cada llamada al minuto completo, y el redondeo del consumo mensual de datos a gigabytes completos antes de calcular cargos por excedente.
- Agregación de datos por usuario y mes: cálculo de número de llamadas, minutos totales, número de mensajes y MB de internet usados por cada cliente en cada mes.
- Cálculo de ingresos: función que calcula el ingreso mensual de cada usuario combinando la tarifa base del plan y los cargos por excedente en minutos, mensajes y datos.
- Análisis del comportamiento de usuario: comparación de minutos, mensajes e internet usados entre los dos planes, con gráficos de barras, histogramas y diagramas de caja, además de medidas de tendencia central y dispersión (media y varianza).
- Pruebas de hipótesis estadísticas: contraste de si existe una diferencia significativa en los ingresos entre los planes Surf y Ultimate, y entre los usuarios de la región NY-NJ frente a los de otras regiones.


## Objetivo

Determinar qué tarifa de prepago (Surf o Ultimate) genera más ingresos para Megaline, y entender el comportamiento de uso de cada segmento de clientes para apoyar decisiones de marketing y presupuesto publicitario.

## Tecnologías utilizadas

- Python
- Pandas / NumPy — manipulación, limpieza y agregación de datos
- Matplotlib / Seaborn — visualización de datos
- SciPy — pruebas de hipótesis estadísticas (t-test)


## Principales hallazgos


- En cuanto a minutos de llamada, no se observan diferencias importantes en el comportamiento entre usuarios de ambos planes: distribuciones, medias y varianzas son similares.
- En número de mensajes enviados, sí se observa una diferencia: los usuarios de Ultimate envían en promedio más mensajes, aunque el plan Surf tiene una proporción mayor de usuarios que no envían mensajes en absoluto.
- En consumo de datos de internet, el comportamiento entre planes tampoco muestra diferencias relevantes.
- Los ingresos del plan Ultimate se mantienen estables a lo largo del año y muy cercanos al costo fijo de la tarifa, ya que sus límites incluidos son suficientes para la mayoría de los usuarios. Los ingresos del plan Surf muestran mayor variabilidad y una tendencia creciente a lo largo del año, producto de cargos por excedente.
- La prueba de hipótesis confirma una diferencia estadísticamente significativa entre los ingresos generados por ambos planes.
- Se probó adicionalmente si los usuarios de la región NY-NJ generan ingresos distintos a los del resto de regiones.


## Estructura del notebook


1. Inicialización y carga de datos
2. Preparación de datos (tarifas, usuarios, llamadas, mensajes, internet)
3. Revisión de condiciones de las tarifas
4. Agregación de datos por usuario y mes
5. Cálculo de ingreso mensual por usuario
6. Análisis del comportamiento de usuario (llamadas, mensajes, internet)
7. Análisis de ingresos por plan
8. Pruebas de hipótesis estadísticas
9. Conclusión general


## Cómo ejecutar el proyecto

bashgit clone <url-del-repo>
cd <nombre-del-repo>
pip install -r requirements.txt
jupyter notebook notebook_proyecto.ipynb

Los datos utilizados (megaline_users.csv, megaline_calls.csv, megaline_messages.csv, megaline_internet.csv, megaline_plans.csv) deben colocarse en el directorio del proyecto para que el notebook los lea correctamente.


## Notas
Proyecto desarrollado como parte del programa de Ciencia de Datos de TripleTen (aprobado).
