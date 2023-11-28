---
layout: default
---

Mi primer portafolio
en este se presentará los proyectos que estoy elaborando

[LinkeInd](https://www.linkedin.com/in/anshel-chuquiviguel-za%C3%B1a-7ab93827a/)
(https://github.githubassets.com/

# 1. Análisis Estructural de un portico

El diseño y construcción de edificios actualmente cuenta con una gran demanda en la cartera de proyectos, especialmente del tipo residencial, esto en respuesta a la gran demanda. Estructuras que, a su vez, llegan a alcanzar grandes alturas debido a su diseño, para el cual se determinan ciertos criterios asociados a las deflexiones máximas que puede tener para ser considerada estable. Es por ello, que se infiere que estas estructuras demandan un alto grado de análisis referidas a los desplazamientos máximos que se pudieran dar, así como las principales propiedades con las que deben contar sus elementos. 

De lo anteriormente mencionado, se propone el análisis de un edificio de dos pisos bajo dos combinaciones de carga determinando que la segunda, la cual, considera el efecto del sismo tiene mayor injerencia sobre la estructura en los desplazamientos y que a medida que se adicionan más pisos la inercia tiende a aumentar.

En tal sentido, la investigación se limita a estudiar una estructura aporticada simplificada axialmente rígida. Además, el alcance del análisis es estudiar la estructura bajo cuatro cargas, cargas muertas, vivas, de viento y de sismo, y empleando únicamente dos combinaciones de carga. Además, las cargas muertas y vivas se consideran cargas gravitatorias, mientras que la carga de viento, una carga horizontal que actúa perpendicular a las columnas extremas izquierdas. En cuanto a la carga del sismo, esta únicamente actúa en los nodos del lado izquierdo de la estructura y su valor es proporcional a la cantidad de pisos de la estructura así como a la carga muerta que se presenta.



## Objetivos

Determinar las propiedades idóneas E y I para el edificio de dos pisos mediante el método de desplazamiento considerando diversas condiciones de carga.
### Objetivos específicos:
* Determinar los desplazamientos debido a las combinaciones de carga bajo el método pendiente-deflexión verificando que no superen la flecha máxima (0.03ft).
* Identificar el tipo de combinación de carga crítica.
* Evaluar la variación de la inercia (I) al añadir dos pisos y tres tramos adicionales.

## Fundamento teórico

El método de pendiente-deflexión, propuesto inicialmente por Heinrich Manderla y Otto Mohr, y luego ampliado por George A. Maney en 1914 (Zambrano, 2020), se centra en el análisis de estructuras indeterminadas. Este método correlaciona diversas variables de interés en el análisis estructural, como las cargas y los desplazamientos. Utiliza conocimientos de estática para evaluar los equilibrios tanto en los nodos (puntos de unión entre dos elementos estructurales) como en un equilibrio global en el caso de desplazamientos laterales. Para estos últimos, se asume que la estructura es axialmente rígida. Al correlacionar estos desplazamientos y giros, el método genera un sistema de ecuaciones equivalente al número de grados de libertad presentes en la estructura.
``` 
Mij=2EIL2i+j-3ij+FEMij
```

Para el desarrollo de las ecuaciones de pendiente-deflexión, estas requieren de una componente asociada al tipo de carga actuante sobre la estructura, la cual puede ser determinada utilizando las tablas propuestas por diversos autores. Hibbeler (2012) propone establecer el sentido horario como positivo para facilitar el análisis; sin embargo, esto no implica que no se pueda considerar el sentido antihorario como positivo.

## Procedimiento

Para realizar el análisis, primero se encontró la inercia mínima que requiere una estructura aporticada de acero para cumplir con el desplazamiento máximo. Este procedimiento se realizó mediante el método pendiente deflexión, pues permite encontrar fácilmente los giros y el  desplazamiento lateral de la estructura de manera más corta. Las combinaciones de cargas son las siguientes:

![dfd](./imagenes/1comb.png)

**Figura 1.** Diagrama de la primera combinación
![](./imagenes/dib1.png)

**Figura 2.** Diagrama de la segunda combinación
![](./imagenes/dib2.png)


## Análisis Estructural

### Cálculo del desplazamiento por el método pendiente deflexión  

Se decidió emplear el método pendiente-deflexión dado a su facilidad de encontrar el desplazamiento lateral de la estructura con el menor número de pasos posibles. El análisis se realizó primero considerando la distribución de fuerzas empleando la primera combinación de cargas. Después de encontrar los desplazamientos relativos, se propone un valor de inercia que cumpla con la deflexión máxima. El mismo paso se realizó con la segunda combinación, que incluye una fuerza sísmica, obteniendo otro valor de inercia que cumpla con los requerimientos de desplazamiento. Finalmente, se proponen propiedades de EI que cumplan en ambas combinaciones con la deflexión máxima.

#### Primera combinación
En la primera combinación, primero se encontró los momentos internos de empotradura en los extremos de cada tramo y, dado a su similitud, se pueden resumir en:

**Figura 3.** Momentos internos de empotradura en cada tramo, primera combinación
![](./imagenes/f3.png)

Posteriormente, se definieron las variables de desplazamiento lateral en la estructura y el ángulo de giro generado por este mismo.

**Figura 4.** Desplazamiento lateral y giro en la estructura
![](./imagenes/f4.png)

Considerando la ecuación de pendiente deflexión, los momentos internos en los extremos de cada tramo serían:
![](./imagenes/e1.png)

Por lo tanto, realizando equilibrio de momentos en los nodos 

***Equilibrio de momentos en los nodos C e I***
![](./imagenes/e2.png)

**Equilibrio de momentos en los nodos B, H, F**
![](./imagenes/e3.png)

**Equilibrio de momentos en el nodo E**
![](./imagenes/e4.png)

Para solucionar el sistema de ecuaciones se necesitan 2 ecuaciones más. El cual se obtiene haciendo equilibro de fuerzas con las cortantes generados en la estructura de la siguiente manera:

**Figura 5.** Equilibrio de fuerzas en la estructura, primera combinación
![](./imagenes/f5.png)

Por lo tanto, las cortantes internas serían:
![](./imagenes/e7.png)

Equilibrio de fuerzas:
![](./imagenes/e5.png)
![](./imagenes/e6.png)

Reemplazando con los datos ya conocidos, asumiendo la inercia y el módulo de elasticidad como una unidad, y teniendo en cuenta que no existe giros en los apoyos empotrados de los nodos A, D, y G, obtenemos el sistema de ecuaciones de la siguiente manera:
![](./imagenes/e8.png)

La matriz de las ecuaciones se resumen en:
![](./imagenes/e9.png)

Considerado que el material del pórtico es acero, obtenemos que la I mínima para cumplir con el desplazamiento máximo es:
E=2900 kip/in2=4176000 kip/ft2
Imin=1+2H/400/E=32141+218383/400/4176000=0.431 ft4
Sin embargo, por cuestiones de seguridad se propone utilizar una inercia un poco mayor,
I=0.5 ft4

Ver procedimiento detallado en el [*Anexo 1*](./ANEXO_1_Primera_combinación.pdf)

#### Segunda combinación

A comparación de la primera combinación, la segunda combinación no considera la carga distribuida del viento, sino cargas puntuales proporcionales a la carga muerta y a los pisos de la estructura que actúan horizontalmente en los nodos B y C. Por lo cual, todas las columnas no tendrían momentos de empotradura y los diagramas se reducen de la siguiente manera:

**Figura 6.** Momentos internos de empotradura en cada tramo, segunda combinación 
![](./imagenes/f6.png)

Por lo cual, los momentos internos en los extremos de cada tramo serían:
![](./imagenes/e10.png)


Realizando el equilibrio de momentos en los nodos, obtenemos:

***Equilibrio de momentos en los nodos C e I***
![](./imagenes/e11.png)

***Equilibrio de momentos en los nodos B, H, F***
![](./imagenes/e12.png)

***Equilibrio de momentos en el nodo E***
![](./imagenes/e13.png)

Además, el equilibrio de fuerzas cambiaria respecto a la combinación 1 pues solo se comparan la fuerza del sismo respecto a las cortantes de la estructura:

**Figura 7.** Equilibrio de fuerzas en la estructura, segunda combinación
![](./imagenes/f7.png)

Por lo tanto, las cortantes internas serían:
![](./imagenes/e15.png)

Por equilibrio de fuerzas:
![](./imagenes/e14.png)
![](./imagenes/e16.png)


Como en la primera combinación, reemplazando con los datos ya conocidos y asumiendo la inercia y el módulo de elasticidad como una unidad, obtenemos la siguiente matriz del sistema de ecuaciones:

De igual manera, considerando que el material del pórtico es acero, obtenemos que la Inercia mínima que cumple con el desplazamiento máximo es:
```
E=2900 kip/in2=4176000 kip/ft2
Imin=1+2H/400/
E=177154+1855843/400/4176000=2.895 ft4
```

Sin embargo, por cuestiones de seguridad se decidió utilizar una inercia un poco mayor de
`I=3 ft4`

Ver procedimiento detallado en el [Anexo 2](./ANEXO_2_Segunda_combinación.pdf).


# 2. Deforestación de la Amazonía en Madre de Dios: Corredor minero

Proyecto desarrollado como parte del curso de Geodesia Satelital y Fotogrametría

*Objetivo:* Utilizar imágenes satelitales del Landsat 8, 7 y 5 para determinar el nivel de deforestación en el corredor minero del departamento de Madre de Dios, entre los años 1990 al 2022.

*Logro:* La deforestación encontrada para el 2022 asciende a 478.36 km2, con una tasa de 23.76 km2/año, lo que ha generado aproximadamente 154.68 millones de soles de pérdidas económicas. Se estimó que la deforestación para el 2040 oscilará entre 669 y 745 km2 el cual generaría unas perdidas económicas de 216.24 a 241.04 millones de soles.

**Deforestación del corredor minero de 1991 a 2022**
Resumen de las áreas deforestadas en el corredor minero del distrito de Madre de Dios, provincia de Manu, y en el distrito de Inambari, provincia de Tambopata, desde 1991 a 2022
![](./imagenes/mapa.png)

[Acceder a los mapas de 1990 a 2000](./imagenes/m1.pdf)

[Acceder a los mapas de 2001 a 2009](./imagenes/m2.pdf)

[Acceder a los mapas de 2014 a 2022](./imagenes/m3.pdf)



# Estudio hidrológico de la cuenca del Río Seco de Pachacamac

Proyecto desarrollado como parte del curso de Hidrología 

**Objetivo:** Conocer y evaluar las características físicas y geomorfológicas de la cuenca de la quebrada de Pachacamac, encontrar su funcionamiento hidrológico, y estimar y modelar eventos extremos.

**Logro:** Se ha procesado y analizado la información hidrometeorológica de la cuenca mediante registros históricos de 1990 al 2010 encontrando un balance hídrico y climático negativo, no hay presencia de escorrentía, y estimando precipitaciones de 73.5 y 82.7 mm en 50 y 100 años de periodo de retorno que a su vez generarían caudales de 31.1 y 46.2 m3/s respectivamente.

![](./imagenes/INFO.png)















