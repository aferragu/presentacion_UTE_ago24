---
title: "Optimización en redes de energía"
author: "Andres Ferragut"
marp: true
theme: my-theme
footer: Andres Ferragut, Universidad ORT Uruguay. Agosto 2024
math: katex
transition: fade
---
<!-- _footer: ![h:100](images/logoort.png) --> 
<!-- _paginate: false -->
<!-- _class: titleSlide -->

![bg left:20%](images/fondo.png)

# Optimización en redes de energía

## Andrés Ferragut - Universidad ORT Uruguay

### Foro de Descarbonización y Segunda Transición Energética. Agosto 2024.

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

# Proyectos y Estudiantes


* Múltiples proyectos financiados a través del Fondo Sectorial de Energía (DNE-ANCAP-UTE-ANII) desde 2012.

  * **Gestión de recarga de vehículos eléctricos y su integración inteligente con la red eléctrica**, 2019-2021.

  * **Red de recarga adaptativa para vehículos eléctricos**. 2021-2022.

* Una decena de estudiantes y graduados del grupo en estos años.
* Mantenemos además colaboración activa con UdelaR y universidades del extranjero (Caltech, Johns Hopkins, Georgia Tech).

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

**Solución:** diseñamos un algoritmo de Machine Learning para estimar la demanda [Espindola, F., INFORMS APS 2023] 

---

# Ejemplo: asignación dinámica de usuarios

**Idea:** estudiar cómo funciona la congestión en una red *urbana* de cargadores.

* Los usuarios eligen el cargador más cercano?
* O eligen uno que les proporcione más tiempo de carga/energía?
  

**Pregunta:** Si dejamos a los usuarios elegir de manera egoísta, ¿se llega a un equilibrio? ¿Es eficiente?


**Resultado:** Probamos que las decisiones egoístas alcanzan un equilibrio y caracterizamos su ineficiencia.

---

# Ejemplo: asignación dinámica de usuarios

<div style="text-align:center">
<video controls="controls" height="500px" width="1000px" src="images/stochastic.mp4" />
</div>


---

# Conclusiones


<div class="grid grid-cols-2 gap-10">
<div>

* Debemos adecuar la *gestión* de la red para evitar la *congestión*.

* Debemos incorporar algoritmos y matemática para llevarlo a cabo.
  
* El desafío ahora es incorporar la investigación en el desarrollo de nuevos proyectos.
  
</div>
<div style="text-align:right">
<br />
<br />
<img width=90% class="card"  src=images/movilidad_electrica.jpg />
</div>
</div>
</div>


---

<!-- _footer: ![h:100](images/logoort.png) --> 
<!-- _paginate: false -->
<!-- _class: titleSlide -->


![bg left:20%](images/fondo.png)

# Muchas gracias

## Contacto: ferragut@ort.edu.uy

## Website: https://aferragu.github.io

