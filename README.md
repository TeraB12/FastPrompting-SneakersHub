# Sneakers Hub con Fast Prompting

## Introducción
Este proyecto es una POC para implementar un asistente virtual de ventas en un ecommerce de zapatillas importadas.  

El problema identificado es que los usuarios pierden tiempo buscando un modelo específico dentro del catálogo, ya que deben navegar múltiples páginas o usar buscadores poco eficientes.  
Un asistente que entienda lenguaje natural mejora la experiencia, acelera la búsqueda y aumenta la conversión.

---

## Propuesta de solución
La solución utiliza Fast Prompting para:  
- Interpretar consultas en lenguaje natural (ej: “quiero unas Jordan negras talla 42”).  
- Responder con productos relevantes.  
- Devolver la información en formato estructurado (JSON) para integrarse fácilmente con la web.  

---

## Justificación de viabilidad
- Técnica: se implementa en Python con Jupyter Notebook y la API de OpenAI.  
- Costos: optimización de prompts para reducir llamadas innecesarias.  
- Tiempo: se puede implementar rápidamente como POC y escalar a producción.  

---

## Objetivos
1. Mejorar la búsqueda de productos dentro de la web de zapatillas.  
2. Demostrar cómo Fast Prompting reduce el costo y mejora las respuestas.  
3. Construir una prueba de concepto lista para integrar en un chatbot.  

---

## Metodología
- Iteración de prompts: partir de una versión básica e ir optimizándola.  
- Comparación: medir la calidad y formato de las respuestas en cada versión.  
- Documentación: guardar los experimentos en una notebook.  

---

## Herramientas y tecnologías
- Lenguaje: Python (Jupyter Notebook).  
- API: OpenAI.  
- Técnicas de prompting:  
  - Zero-shot.  
  - Few-shot (con ejemplos).  
  - Respuestas estructuradas en JSON.  

---

## Implementación
La notebook incluye pruebas con dos versiones de prompts:

1. **Prompt simple**  
   ```
   Encuentra zapatillas Adidas Campus grises en talle 41.
   ```

2. **Prompt mejorado (Fast Prompting)**  
   ```
   Actúa como un asistente de ventas de una tienda de zapatillas.
   Responde de forma breve y clara.
   Si el producto está disponible, indica modelo, color, talle y precio.
   Si no está disponible, ofrece una alternativa similar.
   Devuelve la respuesta en JSON con los campos: modelo, color, talle, precio.

   Usuario: Quiero unas Adidas Campus en gris, talle 41
   ```

---

## Ejemplo de resultado
Versión 1 (respuesta libre):  
"Las Adidas Campus en gris talle 41 están disponibles por USD 120."

Versión 2 (respuesta optimizada):
```json
{
  "modelo": "Adidas Campus",
  "color": "Gris",
  "talle": 41,
  "precio": 120
}
```
