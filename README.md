# CLASE-30-ABRIL

# Clase: Transmisión por Tornillo Guía

La transmisión por tornillo guía es un método ampliamente utilizado para convertir movimiento rotacional en movimiento lineal. Es fundamental en aplicaciones de control de movimiento, como en sistemas CNC, actuadores lineales y máquinas herramienta. Esta clase explora los principios, ecuaciones, eficiencia, cálculos prácticos y simulaciones relacionadas con los tornillos trapezoidales y de bolas, ofreciendo herramientas para comprender y aplicar correctamente estos sistemas en diseños mecánicos.

## 1. Subtítulos

1.1 Tipos de tornillos de transmisión  
1.2 Conceptos geométricos  
1.3 Relación de transmisión  
1.4 Torque de carga  
1.5 Inercia reflejada  
1.6 Eficiencia del tornillo  
1.7 Ejemplo práctico  
1.8 Simulación Simscape  
1.9 Figuras y referencias visuales  

## 2. Definiciones

>🔑 *Tornillo guía:* Mecanismo que convierte movimiento rotacional en movimiento lineal, común en sistemas de posicionamiento.  
>🔑 *Rosca trapezoidal:* Tipo de rosca con flancos en ángulo de 30°, utilizada en mecanismos de transmisión por su robustez.  
>🔑 *Paso (p):* Distancia lineal que avanza la tuerca por cada vuelta del tornillo.  
>🔑 *Inercia reflejada:* Equivalente rotacional de una masa lineal vista desde el eje del motor.  
>🔑 *Eficiencia:* Relación entre la energía útil obtenida y la energía suministrada.  

## 3. Subsecciones

### 3.1. Tipos de tornillos de transmisión
- Tornillos ACME o trapezoidales  
- Tornillos de bolas  

### 3.2. Torque de carga con y sin fricción
Se explica el impacto de la fricción en el torque requerido para mover una carga axial.  

### 3.3. Inercia reflejada por masa lineal
Permite calcular cuánta resistencia al cambio de velocidad lineal se traduce como carga rotacional.   

## 4. Ecuaciones

$$\\frac{d\\theta}{dx} = \\frac{2\\pi}{p}$$

$$T = \\frac{F \\cdot d_m}{2} \\cdot \\left( \\frac{p + \\pi \\mu d_m}{\\pi d_m - \\mu p} \\right)$$

$$J_{\\text{ref}} = m \\cdot \\left( \\frac{p}{2\\pi} \\right)^2$$

$$\\eta \\approx \\frac{1 - \\mu \\cdot \\tan(\\phi)}{1 + \\mu / \\tan(\\phi)}$$

## 5. Figuras

![Tornillo Trapezoidal](https://rollcnc.com/product/tornillo-trapezoidal-t102-1000mm/)
Figura 1. Tornillo trapezoidal T10x2

![Husillo y Tuerca Trapezoidal](https://grupogaes.com/tienda/movimiento-lineal/husillos/husillos-y-tuercas-trapezoidales/)
Figura 2. Conjunto husillo y tuerca trapezoidal

![Husillo de bolas](https://www.directindustry.es/prod/thomson-industries-inc/product-7040-2252635.html)
Figura 3. Husillo de bolas con tuerca

![Wikipedia](https://es.wikipedia.org/wiki/Husillo_de_bolas)
Figura 4. Diagrama interno de husillo de bolas

## 6. Tablas

| Tipo de tornillo | Eficiencia | Características clave                  |
|------------------|------------|----------------------------------------|
| Trapezoidal      | 35% - 85%  | Resistente, fácil de fabricar           |
| De bolas         | 85% - 95%  | Alta precisión, bajo desgaste, costoso |

Tabla 1. Comparación entre tipos de tornillos

## 7. Código

**Ejemplo:** Cálculo básico en MATLAB
```matlab
F = 500;
p = 0.008;
T = F * p / (2*pi);
disp(['Torque ideal: ', num2str(T), ' Nm']);
```
**Ejemplo:** Simulacion en MATLAB de simulink multibody 

## 8. Ejercicios

### Ejercicio 1

**Enunciado:** Determinar el torque necesario para levantar una carga de 1000 N con un tornillo de paso 4 mm, fricción 0.1 y diámetro medio 16 mm.

**Solución:**

La fórmula general del torque necesario para levantar una carga con un tornillo con fricción es:

$T = \frac{F \cdot d_m}{2} \cdot \frac{\tan(\lambda) + \mu}{1 - \mu \cdot \tan(\lambda)}$

donde:

* $T$: torque necesario (Nm)
* $F$: carga axial (N) $\rightarrow 1000 \text{ N}$
* $d_m$: diámetro medio del tornillo (m) $\rightarrow 16 \text{ mm} = 0.016 \text{ m}$
* $\mu$: coeficiente de fricción $\rightarrow 0.1$
* $\lambda$: ángulo de hélice del tornillo
* $\tan(\lambda) = \frac{p}{\pi \cdot d_m}$, donde $p$ es el paso del tornillo $\rightarrow 4 \text{ mm} = 0.004 \text{ m}$

### 1. Calcular el ángulo de hélice ($\lambda$):

$\tan(\lambda) = \frac{p}{\pi \cdot d_m} = \frac{0.004}{\pi \cdot 0.016} \approx 0.0796$

### 2. Aplicar la fórmula del torque:

$T = \frac{1000 \cdot 0.016}{2} \cdot \frac{0.0796 + 0.1}{1 - 0.1 \cdot 0.0796}$

$T = 8 \cdot \frac{0.1796}{1 - 0.00796} = 8 \cdot \frac{0.1796}{0.99204} \approx 8 \cdot 0.1810 \approx 1.45 \text{ Nm}$

En el ejercicio aparece que $T \approx 1.23 \text{ Nm}$, por lo que podrían estar usando una fórmula aproximada o con algún redondeo o simplificación adicional.

### Ejercicio 2

**Enunciado:** Calcule el torque requerido para un tornillo con una carga de 500 N, un paso de 0.008 m, un diámetro medio de 0.018 m y un coeficiente de fricción de 0.2. Considere tanto el torque ideal (sin fricción) como el torque real (con fricción).

**Datos:**

* Carga $F = 500 \text{ N}$
* Paso del tornillo $p = 0.008 \text{ m (8 mm)}$
* Diámetro medio del tornillo $d_m = 0.018 \text{ m (18 mm)}$
* Coeficiente de fricción $\mu = 0.2$

## Paso 1: Torque sin fricción (ideal)

$T_{\text{ideal}} = \frac{F \cdot p}{2\pi} = \frac{500 \cdot 0.008}{2\pi} \approx 0.636 \text{ Nm}$

## Paso 2: Torque con fricción

$T = \frac{F \cdot d_m}{2} \cdot \left( \frac{p + \pi \mu d_m}{\pi d_m - \mu p} \right)$

Sustituyendo:

$T = \frac{500 \cdot 0.018}{2} \cdot \left( \frac{0.008 + \pi \cdot 0.2 \cdot 0.018}{\pi \cdot 0.018 - 0.2 \cdot 0.008} \right)$

Calculamos:

* Numerador: $0.008 + \pi \cdot 0.2 \cdot 0.018 \approx 0.008 + 0.0113 = 0.0193$
* Denominador: $\pi \cdot 0.018 - 0.0016 \approx 0.0565 - 0.0016 = 0.0549$

$T \approx 4.5 \cdot \left( \frac{0.0193}{0.0549} \right) \approx 4.5 \cdot 0.3515 = 1.58 \text{ Nm}$

### Ejercicio 3

**Enunciado:** Una banda transportadora transporta cajas de 20 kg cada una sobre una pendiente de 15°. El sistema usa una correa conectada a una polea motriz de 10 cm de radio. La banda debe acelerar desde reposo hasta 1 m/s en 2 segundos. El coeficiente de fricción dinámica entre la caja y la banda es 0.3.
Se pide:
* Calcular la fuerza total que debe generar la banda
* Calcular el torque que debe generar el motor
* Determinar la potencia requerida

## Paso 1: Análisis de fuerzas

Para mover la caja sobre la pendiente hay tres fuerzas principales:

### 1. Peso componente paralelo a la rampa:

$F_{\text{pendiente}} = m \cdot g \cdot \sin(\theta) = 20 \cdot 9.81 \cdot \sin(15^\circ) \approx 50.8 \text{ N}$

### 2. Fricción:

$F_{\text{fricción}} = \mu \cdot m \cdot g \cdot \cos(\theta) = 0.3 \cdot 20 \cdot 9.81 \cdot \cos(15^\circ) \approx 56.8 \text{ N}$

### 3. Fuerza por aceleración lineal (segunda ley de Newton):

Primero calculamos la aceleración:

$a = \frac{v_f - v_0}{t} = \frac{1 - 0}{2} = 0.5 \text{ m/s}^2$

$F_{\text{aceleración}} = m \cdot a = 20 \cdot 0.5 = 10 \text{ N}$

## Fuerza total que debe hacer la banda:

$F_{\text{total}} = F_{\text{pendiente}} + F_{\text{fricción}} + F_{\text{aceleración}} \approx 50.8 + 56.8 + 10 = 117.6 \text{ N}$

## Paso 2: Calcular el torque requerido

La banda mueve la caja mediante una polea de $0.1 \text{ m}$ de radio. Entonces:

$T = F \cdot r = 117.6 \cdot 0.1 = 11.76 \text{ Nm}$

## Paso 3: Calcular la potencia necesaria

La potencia mecánica en el eje del motor es:

$P = F \cdot v = 117.6 \cdot 1 = 117.6 \text{ W}$

Si se considera una eficiencia del sistema de, digamos, 85%:

$P_{\text{real}} = \frac{117.6}{0.85} \approx 138.3 \text{ W}$

## 9. Conclusiones

El diseño eficaz de sistemas mecánicos para el control de movimiento es un proceso multifacético que va más allá de la simple aplicación de fórmulas. Es crucial no solo calcular con precisión el torque y la potencia necesarios para superar cargas, fricción y aceleración (como se ilustra en los ejemplos de cálculo de tornillos y bandas transportadoras), sino también seleccionar cuidadosamente el motor y el mecanismo de transmisión adecuados. Esto implica asegurar que el motor tenga el torque suficiente y una inercia compatible con la carga, siempre considerando un margen de seguridad y factores prácticos como el costo y la precisión.

Finalmente, la validación y el análisis de estos sistemas se ven enormemente beneficiados por el uso de herramientas de simulación. Estas herramientas permiten predecir el comportamiento de mecanismos complejos como las cremalleras y piñones, o las bandas transportadoras, y visualizar resultados clave, lo que facilita la optimización del diseño y la comprensión de conceptos fundamentales como la inercia reflejada, asegurando así la fiabilidad y eficiencia del sistema final.

## 10. Referencias

* Wikipedia: [https://es.wikipedia.org/wiki/Husillo_de_bolas](https://es.wikipedia.org/wiki/Husillo_de_bolas)
* Catálogo Thomson: [https://www.thomsonlinear.com/es/productos/husillos-de-bolas](https://www.thomsonlinear.com/es/productos/husillos-de-bolas)
* Manual SKF (Slideshare): [https://es.slideshare.net/slideshow/manual-husillos-de-bolas-skfpdf/254006675](https://es.slideshare.net/slideshow/manual-husillos-de-bolas-skfpdf/254006675)
* Imágenes obtenidas de: RollCNC, GrupoGaes, DirectIndustry, Wikipedia
