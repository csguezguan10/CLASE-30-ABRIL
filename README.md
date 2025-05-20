# CLASE-30-ABRIL
CLASE 30 ABRIL

# Ruta de guardado y contenido del archivo .md
file_path = Path("/mnt/data/Clase_Tornillo_Guia.md")
md_content = """
# ⚖️ Clase: Transmisión por Tornillo Guía

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

## 4. Ejemplos

💡**Ejemplo 1:** Calcular el torque requerido para levantar 500 N usando un tornillo trapezoidal con paso de 8 mm, fricción 0.2 y diámetro medio de 18 mm. Resultado: 1.58 Nm  

💡**Ejemplo 2:** Calcular la inercia reflejada por una masa de 10 kg usando un tornillo de paso 10 mm. Resultado: \(2.53 \times 10^{-5} \, \text{kg}\cdot\text{m}^2\)  

## 5. Ecuaciones

$$\\frac{d\\theta}{dx} = \\frac{2\\pi}{p}$$

$$T = \\frac{F \\cdot d_m}{2} \\cdot \\left( \\frac{p + \\pi \\mu d_m}{\\pi d_m - \\mu p} \\right)$$

$$J_{\\text{ref}} = m \\cdot \\left( \\frac{p}{2\\pi} \\right)^2$$

$$\\eta \\approx \\frac{1 - \\mu \\cdot \\tan(\\phi)}{1 + \\mu / \\tan(\\phi)}$$

## 6. Figuras

![Tornillo Trapezoidal](https://rollcnc.com/product/tornillo-trapezoidal-t102-1000mm/)
Figura 1. Tornillo trapezoidal T10x2

![Husillo y Tuerca Trapezoidal](https://grupogaes.com/tienda/movimiento-lineal/husillos/husillos-y-tuercas-trapezoidales/)
Figura 2. Conjunto husillo y tuerca trapezoidal

![Husillo de bolas](https://www.directindustry.es/prod/thomson-industries-inc/product-7040-2252635.html)
Figura 3. Husillo de bolas con tuerca

![Wikipedia](https://es.wikipedia.org/wiki/Husillo_de_bolas)
Figura 4. Diagrama interno de husillo de bolas

## 7. Tablas

| Tipo de tornillo | Eficiencia | Características clave                  |
|------------------|------------|----------------------------------------|
| Trapezoidal      | 35% - 85%  | Resistente, fácil de fabricar           |
| De bolas         | 85% - 95%  | Alta precisión, bajo desgaste, costoso |

Tabla 1. Comparación entre tipos de tornillos

## 8. Código

💡**Ejemplo 4:** Cálculo básico en MATLAB
```matlab
F = 500;
p = 0.008;
T = F * p / (2*pi);
disp(['Torque ideal: ', num2str(T), ' Nm']);
```
## 9. Ejercicios

### 📝 Ejercicio 1

**Enunciado:** Calcule la inercia reflejada al motor por una masa de 20 kg usando un tornillo con paso de 5 mm.

**Solución:**

$$
J_{extref} = 20 \cdot \left( \frac{0.005}{2\pi} \right)^2 \approx 2.53 \times 10^{-6} \, \text{kg} \cdot \text{m}^2
$$

### 📝 Ejercicio 2

**Enunciado:** Determinar el torque necesario para levantar una carga de 1000 N con un tornillo de paso 4 mm, fricción 0.1 y diámetro medio 16 mm.

**Solución:**

Aplicamos la fórmula completa de torque con fricción:

$$
T \approx 1.23 \, \text{Nm}
$$

## 10. Conclusiones

* Los tornillos guía son elementos esenciales en sistemas de transmisión lineal.
* Comprender sus parámetros y ecuaciones es clave para diseños eficientes.
* La fricción y la inercia reflejada son factores críticos a considerar.
* Las simulaciones en Simscape ayudan a validar físicamente los modelos matemáticos.

## 11. Referencias

* Wikipedia: [https://es.wikipedia.org/wiki/Husillo_de_bolas](https://es.wikipedia.org/wiki/Husillo_de_bolas)
* Catálogo Thomson: [https://www.thomsonlinear.com/es/productos/husillos-de-bolas](https://www.thomsonlinear.com/es/productos/husillos-de-bolas)
* Manual SKF (Slideshare): [https://es.slideshare.net/slideshow/manual-husillos-de-bolas-skfpdf/254006675](https://es.slideshare.net/slideshow/manual-husillos-de-bolas-skfpdf/254006675)
* Imágenes obtenidas de: RollCNC, GrupoGaes, DirectIndustry, Wikipedia
