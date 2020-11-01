---
authors: [Janosch Köferli & Philipp Manuel Stancke]
categories: []
date: "2019-02-05T00:00:00Z"
slides:
  highlight_style: dracula
  theme: black
summary: An introduction to using Academic's Slides feature.
tags: []
title: ¿Quién pierde? Efectos de erradicación de los cultivos en el
  desarrollo regional
---

Estructura

1.  Resumen de política de lucha contra los estupefacientes en
    Afganistán

2.  Problemas del desarrollo económico

3.  Investigación en los efecto de la erradicación de cultivos en el
    desarrollo socioeconómico

    -   Externalidades con respecto a agricultores, salud pública,
        consumo de drogas y a los talibanes.

---

#Pregunta de Investigación y Relevancia Académica

##Erradicación y Desarrollo - Ingresos Agrícolas
**Por qué hay una preferencia por el cultivo de opio?**

**Efectos de la erradicación por parte a través del ingreso:**

-   Empeoramiento de la calidad de la tierra

-   Disminución de la productividad de la tierra

-   Endeudamiento de los campesinos

-   Trata de seres humanos por los cultivadores

-   Criminalidad

---

**Hipótesis:**

-   **H1:** La erradicación causa el endeudamiento de los campesinos

-   **H2:** La erradicación causa un aumento en la tasa de criminalidad

-   **H3:** La erradicación causa una disminución en la productividad de
    la tierra
    
---

#Erradicación y DesarrolloUso de Drogas

**Hipótesis:**

-   **H4:** Los consumidores sustituyen opio por heroína u otras drogas.

-   **H5:** El riesgo de contagio de y la cantidad relativa de gente con
    VIH/SIDA y otras enfermedades transables por sangre aumenta.

-   **H6:** El apoyo a la salud y los programas de tratamiento no son
    suficientemente desarrollados en Afganistán.

---

#Erradicación y Desarrollo
##Apoyo a los Talibanes

**Hipótesis:**

-   **H7:** Hay un aumento en la tasa de pobreza.

-   **H8:** Regiones y campesinos que son adversarios al cultivo de opio
    están afectados por la erradicación.

-   **H9:** Los Talibán ofrecen servicios de protección y seguridad.

---

#Erradicación y Desarrollo
##Ingresos Talibanes

**Hipótesis:**

-   **H10:** Los precios suben proporcionalmente más que la oferta
    disminuye.

-   **H11:** La elasticidad de la demanda es baja y entonces la demanda
    no cambia mucho con un aumento en el precio en consecuencia de la
    escasez de opio.

---

#Erradicación y Desarrollo
##Efecto Global

**Hipótesis:**

-   **H12:** Esperamos que las externalidades negativas de la
    erradicación de cultivos superan sus beneficios para el desarrollo
    local.

---

##Datos - Intensidad de la Luz Nocturna

**¿Por qué se utiliza la intensidad de la Luz Nocturna?**

-   Falta de datos socioeconómicos fiables y desglosados

**Consecuencia:**

-   Es más difícil comprender la pobreza, el crecimiento económico y del
    desarrollo humano

**Solución:**

-   Utilizar la intensidad de la luz nocturna posibilita el acceso a
    datos fiables para estimaciones con respecto al desarrollo económico
    de un país.

**Fuente de datos de la luz nocturna:**

-   Administración Nacional Oceánica y Atmosférica (NOAA) para 1992
    hasta 2018

---

##Datos - Erradicación de la Adormidera

-   Problema principal es el acceso a datos de erradicación al nivel
    regional

-   UNODC ofrece solamente datos al nivel provincial

-   Esperamos obtener datos de Dr. Dave Mansfield (se dedica a la
    investigación con respecto a las drogas ilícita en Afganistán y
    sustentos alternativos)

---

##Marco Empírico

**Objetivo principal:**

-   Descubrimiento si hay efecto negativo de la erradicación al
    desarrollo local.

-   Relación entre cantidad de cultivos erradicados y desarrollo
    económico

---

**Modelo de Regresión:** $$\begin{aligned}
        Lum_{ict} = \alpha_{ic}+\beta_{ct}+\gamma * Erad_{ict-1} + X_{ct} + \varepsilon_{ict}
    \end{aligned}$$

-   Coeficiente de interés ($\gamma$) mide efecto de $Erad_{ict}$ sobre
    $Lum_{ict}$

-   Efectos fijos de la región ($\alpha_{ic}$)

-   Efectos fijos país-año ($\beta_{ct}$)

-   Conjunto de variables de control ($X_{ct}$)
