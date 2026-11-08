<p align="center">
  <img align="center" width="auto" src="https://github.com/soliasq/soliasq/assets/5314272/9f87757f-836e-4b79-bfa5-b12b3d1fb72c"/>
  <!--![me](https://github.com/soliasq/soliasq/assets/5314272/9f87757f-836e-4b79-bfa5-b12b3d1fb72c)-->
  <h3 align="center">¡Hey 👋!  I'm soliasq 👨🏻‍💻</h3>
  
```js
const soliasq = {
  pronoums: "he" |"him",
  code: [Javascript,Typescript, HTML, CSS, Java, Haskell, Rust, C#, PHP],
  tools: [Laravel, Flutter, Node, Storybook, Style-Components, Jest, Dock],
  desing: [Photoshop, Illustrator, Figma, Xd, Corel-Draw, Premier, After-Effects, Indesign],
  other: [Skechup, R, Python, Vba, Tableu ]
}    
```

 <p align="center"> <strong> You can find me :</strong>  👇!</p>
 
<p align="center">
  <a href="http://www.soliasq.260mb.net/?i=1" alt="WEB" target="_blank">
     <img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/googlechrome.svg" alt="Web" height="28px" width="28px"/>
  </a>&nbsp;&nbsp;&nbsp;
   <a href="https://www.youtube.com/channel/UCOBSI6n-Uktm6iN4lqG-fSg" target="_blank" style="margin-right:4px">
    <img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/youtube.svg" alt="solaisq" height="28px" width="28px" />
  </a>&nbsp;&nbsp;&nbsp;
  <a href="https://t.me/soliasq" target="_blank">
    <img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/telegram.svg" alt="soliasq" height="28px" width="28px" />
  </a>&nbsp;&nbsp;&nbsp;
    <a href="https://www.facebook.com/profile.php?id=100065418402533" target="_blank">
    <img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/facebook.svg" alt="soliasq" height="28px" width="28px" />
  </a>&nbsp;&nbsp;&nbsp;
  
  <a href="https://www.instagram.com/t43cr0w" target="blank">
    <img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/instagram.svg" alt="soliasq" height="28px" width="28px" />
  </a>
</p> 
<hr> 
# 📊 EPSAS La Paz - Dashboard MCO Dinámico

[![Estado](https://img.shields.io/badge/Estado-En%20Vivo-success)](https://soliasq.github.io/mco/)
[![Versión](https://img.shields.io/badge/Versión-1.0-blue)](https://soliasq.github.io/mco/)

**Sistema web interactivo de análisis multivariado para el pronóstico de consumo de agua (m³)** utilizando el Método de Mínimos Cuadrados Ordinarios (MCO). Diseñado para la Empresa Pública Social de Agua y Saneamiento (EPSAS) de La Paz, Bolivia.

## 🌐 Acceso al Sistema

Puedes acceder a la aplicación en vivo haciendo clic en el siguiente enlace:

👉 **[https://soliasq.github.io/mco/](https://soliasq.github.io/mco/)**

> *Nota: Actualmente el sistema se encuentra en su estado inicial ("0 Registros"). Para comenzar a usarlo, presiona el botón **"Generar Demo (15k)"** o sube tu propio archivo CSV.*

---

## 🚀 Características Principales

- **Carga Dinámica de Datos:** Permite generar un set de datos de prueba (15,000 registros) o subir un archivo `.csv` real.
- **Cálculo MCO Automático:** Estimación de coeficientes mediante álgebra matricial (con estandarización previa para evitar errores de precisión con números grandes).
- **Visualización Interactiva:** 6 gráficos estadísticos generados con `Chart.js` (Real vs Predicho, Importancia |t|, Residuos, Histograma, Q-Q, Distribución Normal).
- **Mapa Geoespacial:** Integración con `Leaflet.js` y `MarkerCluster` para visualizar los puntos de consumo en La Paz, con opción de filtro por consumo mínimo y Heatmap.
- **Diagnósticos Estadísticos:** Pruebas de Jarque-Bera, Durbin-Watson, Homocedasticidad y Multicolinealidad.
- **Informe Ejecutivo PDF:** Generación automática de un PDF profesional con resumen ejecutivo, tablas formateadas, rankings de impacto y conclusiones.

## 🛠️ Tecnologías Utilizadas

Este proyecto es 100% frontend (Vanilla JavaScript), lo que significa que no requiere servidor ni base de datos para funcionar.

- **HTML5 / CSS3** (Diseño responsivo, Glassmorphism, animaciones).
- **JavaScript (ES6)** (Lógica matemática y manipulación del DOM).
- **[Chart.js](https://www.chartjs.org/)** (Gráficos estadísticos interactivos).
- **[Leaflet.js](https://leafletjs.com/)** + **Leaflet.markercluster** + **Leaflet.heat** (Mapas).
- **[jsPDF](https://github.com/parallax/jsPDF)** (Generación del informe ejecutivo).
- **[FontAwesome](https://fontawesome.com/)** (Iconografía).
- **Google Fonts** (Inter / JetBrains Mono).

## 📂 Estructura del Código

El archivo principal es `index03.html`, que contiene todo el sistema. Está dividido lógicamente en las siguientes secciones:

### 1. Interfaz Gráfica (UI)
- **Header:** Logos, botones de carga de CSV, generación de PDF e indicadores (R², registros).
- **Panel Izquierdo:** Selector de variables (Y dependiente, X independientes), botón de cálculo y caja de diagnósticos.
- **Panel Derecho:** Grilla de 6 gráficos, mapa geoespacial, formulación matemática, matrices y tablas de coeficientes/estadísticas.

### 2. Motor Matemático (JavaScript)
Todo el cálculo se realiza internamente sin librerías estadísticas externas (excepto para gráficos).

- **`matMul` / `matTranspose`:** Operaciones básicas de matrices.
- **`matInversePivot`:** Inversión de matriz con pivoteo parcial (crucial para estabilidad numérica).
- **`estandarizarMatriz`:** Normaliza las variables X (media 0, varianza 1) antes de calcular `XᵀX`. Esto evita que valores grandes (ej. 100,000 habitantes) colapsen el cálculo a cero.
- **`desestandarizarBeta`:** Convierte los coeficientes calculados en escala normalizada de vuelta a la escala original del negocio para su interpretación.
- **`pValorT`:** Implementación de la distribución t-Student para obtener el p-valor de cada coeficiente.

### 3. Lógica del MCO (`ejecutarMCO`)
1. Extrae Y y X de los datos seleccionados.
2. Estandariza las X para evitar errores de redondeo.
3. Calcula \(\hat{\beta} = (X^T X)^{-1} X^T Y\).
4. Desestandariza los \(\beta\) para mostrarlos en escala real.
5. Calcula residuos, R², errores estándar y p-valores.
6. Ejecuta pruebas de diagnóstico (DW, JB).
7. Dispara la renderización de gráficos, mapas y matrices.

## 🧮 Fundamento Matemático

El modelo implementado es:
\[
 Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \beta_k X_k + \varepsilon 
\]

Donde los parámetros se estiman minimizando la suma de errores al cuadrado (SSR):
\[
 \hat{\beta} = (X^T X)^{-1} X^T Y 
\]

Las pruebas implementadas son:
- **R²:** Proporción de varianza explicada.
- **Durbin-Watson (DW):** Detecta autocorrelación (valores cercanos a 2 indican independencia).
- **Jarque-Bera (JB):** Contrasta si los residuos tienen una distribución normal.
- **t-Student:** Evalúa si cada coeficiente es significativamente distinto de cero.

## 📖 Guía de Uso Rápido

1. Abre [https://soliasq.github.io/mco/](https://soliasq.github.io/mco/) en tu navegador web (Chrome, Edge o Firefox).
2. Presiona el botón **"Generar Demo (15k)"** para cargar datos de prueba, o sube un CSV con el botón **"Subir CSV"**.
   - *Nota: El CSV debe tener una fila de encabezados y la primera columna debe ser la variable Y (Consumo_m3) para que funcione el mapa.*
3. Selecciona las variables X que deseas incluir en el modelo.
4. Presiona **"Calcular MCO Dinámico"**.
5. Explora los gráficos (haz clic en ellos para ver explicaciones detalladas) y usa el mapa para ubicar los consumos.
6. Presiona **"Informe PDF"** para descargar el reporte ejecutivo con los resultados.

## 📊 Interpretación de los Gráficos y Ventanas Modales

- **Real vs Predicho:** Si los puntos forman una línea recta de 45°, el modelo es perfecto.
- **Importancia |t|:** Barras más largas = variables más relevantes. La regla general es que si `|t| > 2`, la variable es significativa.
- **Residuos vs Predicho:** Debe verse como una nube aleatoria sin patrones (ni embudos, ni curvas).
- **Histograma de Residuos:** Debe tener forma de campana centrada en cero.
- **Gráfico Q-Q:** Los puntos deben seguir la línea diagonal azul para confirmar normalidad.
- **Distribución Normal:** Muestra la campana de Gauss calculada con la media y desviación real de *tus* residuos, con líneas rojas en ±2 desviaciones estándar.

## 👨‍💻 Autor

Desarrollado para la **EPSAS La Paz**.
*Módulo de Análisis Multivariado para Pronósticos.*
¡Gracias por visitar! Siéntete libre de contactarme o tienes alguna pregunta.<br>
Thank you for visiting my profile! Feel free to contact me or if you have any questions.
<!--
**soliasq/soliasq** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

