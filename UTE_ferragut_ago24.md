---
title: "Optimización en redes de energía"
author: "Andres Ferragut"
marp: true
theme: my-theme
footer: Andres Ferragut, Universidad ORT Uruguay. Julio 2024
math: katex
transition: fade
---
<!-- _footer: ![sponsors](images/sponsors.png) -->
<!-- _paginate: false -->
<!-- _class: titleSlide -->

![bg left:20%](images/fondo.png)

# Optimización en redes de energía

## Andrés Ferragut - Universidad ORT Uruguay

### Fondo Sectorial de Energía, ANII, Julio 2024

---
<!-- paginate: true -->
<!-- class: normalSlide -->


# Algunos números


<div class="grid grid-cols-2 gap-10">
<div>

* En Uruguay se vendieron **860.000 $m^3$** de gasolina en 2021.
* Corresponden a **10300 millones de kms.** (a 12 km/l)



* Se requieren **1300 GWh** anuales para sustituir la gasolina (a 0.125 kwh/km)
* Uruguay consumió **11200 GWh** en 2021, y exportó **2800 GWh**, mayormente de fuentes renovables.


</div>

<div style="display: flex;
  justify-content: center;
  align-items: center;">

<img width=100% src="images/nissan.jpg" />

</div>
</div>

---
# La energía está:

 <h2 style="color: rgb(20,50,100); text-align: center;"> Uruguay dispone de la energía eléctrica para electrificar todo su parque automotor inmediatamente. </h2>

<br />
<br />

<!-- 
---
# Lo que los promedios esconden...

* Esos **1300 GWh** serían demanda mayormente residencial.
* La demanda residencial es 45% del total de energía actual.
* **Resultado:** La demanda *residencial* de energía se incrementaría en un **25%**.
<p />
<p />
<p />


Si además, consideramos que los vehículos se cargan de noche:

* El consumo nocturno es un 70% del consumo medio residencial.
* La energía a entregar en horas de la noche se **duplicaría**.
  
-->

---
# Desafío: 

## Se requiere **gestionar** la demanda para evitar la **congestión** de la red eléctrica.

<br />
<br />

## **¿Cómo lo hacemos?:** Optimización, optimización, optimización...
---

# Nuestro equipo:


<div style="text-align: center; color: rgb(20,50,100); font-weight: bold">
Grupo de Matemática Aplicada a Telecomunicaciones y Energía

Universidad ORT Uruguay

</div>

<br />

**Investigadores:**

 * Fernando Paganini (SNI Nivel III)
 * Andrés Ferragut (SNI Nivel II)

**Colaborador:**

 * Enrique Briglia

---

# Proyectos FSE


* **Mercados, subastas y nuevas tecnologías en el sector eléctrico uruguayo**. 2012-2014. En conjunto con IIE/Fing/UdelaR.

* **Redes eléctricas inteligentes y sus mercados en presencia de energías renovables**. 2014-2016. En conjunto con IIE/Fing/UdelaR.

* **Operación óptima de cargas inteligentes, generación renovable y recursos de almacenamiento en redes eléctricas**. 2017-2019.

* **Optimización del almacenamiento de energía en redes eléctricas**, 2018-2020. En conjunto con IIE/Fing/UdelaR.

---

# Proyectos FSE

* **Gestión de recarga de vehículos eléctricos y su integración inteligente con la red eléctrica**, 2019-2021.

* **Integración y control de almacenamiento distribuido en sistemas eléctricos**, 
2020-2022. En conjunto con IIE/Fing/UdelaR..

* **Red de recarga adaptativa para vehículos eléctricos**. 2021-2022.

---

# Otros proyectos de energía

 
 * **Flujo de carga óptimo y almacenamiento de energía para redes eléctricas dinámicas**, 2016-2017 - Conjunto con UdelaR y UTE.

 * **Flujo de carga óptimo para incorporación de energías renovables**. Proyecto BID-MIEM-Vinculación con la Diáspora Calificada, 2016-2017.

 * **Optimización del almacenamiento de energía en mercados eléctricos con alta penetración de renovables**. ANII - PPI, 2016-2018. Con CSI Ingenieros.

 * **Optimización y Modelos Estocásticos para Planificación y Despacho en la Red Eléctrica**, 2019-2020 - Conjunto con UdelaR y UTE.

---

# Estudiantes y colaboradores

* Federico Bliman (master, actualmente doctorando en UdelaR).
* Martín Zeballos (actualmente en CSI-CIEMSA).
* Rodrigo Porteiro (master, actualmente en UTE).
* Camila Martínez (actualmente doctorando en Ecole de Mines - Paris).
* Lucas Narbondo (actualmente doctorando en TU/Delft).
* Agustín Castellano (master, actualmente doctorando en Johns Hopkins).
* Sebastián Alaggia (Ing. en UTE).
* Diego Acuña (Ing. en UTE).
* Emiliano Espíndola (posgrado en ingeniería, CTO de RedeLocker)

Mantenemos además colaboración activa con UdelaR y universidades del extranjero (Caltech, Johns Hopkins, Georgia Tech).

---

# Aportes realizados

Mencionamos ahora algunos ejemplos de aportes que hemos construido en este tiempo.

<br />
<br />

**Foco común:** Incorporar estrategias de *optimización* y *probabilidad* para generar algoritmos con impacto práctico. 

---


# Ejemplo: agenda de vehículos

<div class="flex">

<div>

Consideremos un parking que ofrece servicio de carga de vehículos.

>**Pregunta:** 
>Si tengo congestión, **¿en qué orden se deben cargar los vehículos?**

¿En orden de llegada? *Muy mala idea*

<br />

>**Solución 1:**
> Priorizar por *urgencia* de la carga (tiempo de partida).

Mejor...pero tengo que confiar en los usuarios...

</div>
<div>
<img class="card" width=400px,  src=images/parking.png />
</div>
</div>

---

# Ejemplo: agenda de vehículos

>**Solución 2:**
> Cargarlos en orden **inverso al de llegada.**

Contraintuitivo, pero aproxima perfectamente el algoritmo anterior *sin necesidad de saber el tiempo de permanencia* [Ferragut et al., INFORMS APS 2019]

<br />

<div class="grid grid-cols-2 gap-10">
<div style="text-align:center">
<br />
<img class="card" src=images/lifo.png />
</div>
<div style="text-align:center">
<img class="card" width=75% src=images/edf_vs_lifo.png />
</div>
</div>

---

# Ejemplo: gestión de demanda de EVs

**Idea:** Si tengo control sobre la carga puedo aprovechar la **flexibilidad** de los usuarios.


<div class="grid grid-cols-2 gap-10">
<div>

* Ejemplo: en Canadá, 95% del tiempo los vehículos están *parados*.

* Podemos *optimizar* la gestión de carga para minimizar el impacto en la red:
  * Disminuir picos [Nakahira et al. Operations Research 2022]
  * Desbalance trifásico, [D. Acuña et al. e-Energy 2022], [Ferragut et al. Performance 2023].
</div>

<div style="text-align:right">
<br />
<img class="card" width=90% src=images/mpc.png />
</div>

---

# Ejemplo: ubicación de puestos de carga


**Idea:** a partir del consumo actual georreferenciado, diseñar una infraestructura de carga óptima para una región:


<div class="grid grid-cols-4 gap-10">
<div>
<img class="card" src=images/demandas.png />
</div>
<div>
<img class="card" src=images/ajuste.png />
</div>
<div>
<img class="card" src=images/cargadores.png />
</div>
<div>
<img class="card" src=images/voronoi.png />
</div>
</div>

<br />

**Solución:** diseñamos un algoritmo de Machine Learning para estimar la demanda [Espindola, F., INFORMS APS 2023] y luego resolver el problema de optimización resultante [Paganini et al., Allerton 2023, TCNS submitted].

---

# Otros aportes:

 * Creamos un algoritmo de **programación estocástica dual multi-escala** para resolver el problema de la optimización conjunta de recurso hídrico y baterías en presencia de renovables [R. Porteiro, Tesis Maestría].
 
 * Creamos algoritmos basados en **relajaciones convexas** para calcular el flujo de carga óptimo en una red de distribución. [Software COMODIN, en testing actualmente en UTE].
 
 * Hicimos aportes a la **regulación de frecuencia**, al control de **demand-response**, así como a modelos de despacho conjunto térmico-hídrico-baterías.

---

# Conclusiones


<div class="grid grid-cols-2 gap-10">
<div>

* Debemos adecuar la *gestión* de la red para evitar la *congestión*.

* Debemos incorporar algoritmos y matemática para llevarlo a cabo.
  
* El FSE ha sido un gran instrumento para apoyar esta investigación y formar RRHH en estos temas.
</div>
<div style="text-align:right">
<br />
<br />
<img width=90% class="card"  src=images/movilidad_electrica.jpg />
</div>
</div>
</div>


---

<!-- _footer: ![sponsors](images/sponsors.png) -->
<!-- _paginate: false -->
<!-- _class: titleSlide -->


![bg left:20%](images/fondo.png)

# Muchas gracias

## Contacto: ferragut@ort.edu.uy

## Website: https://aferragu.github.io

