# 🧪 Proyecto 14. Prueba A/B — Sistema de Recomendaciones

## 📌 Contexto del proyecto
En este repositorio se analiza una Prueba A/B real ejecutada por una tienda en línea internacional para evaluar el impacto de un nuevo sistema de recomendaciones sobre el embudo de conversión de usuarios en la región UE.

La prueba compara:
- Grupo A (control): embudo actual
- Grupo B (test): nuevo embudo de pago con recomendaciones mejoradas

---

## 🎯 Objetivo del análisis
Evaluar si el nuevo sistema de recomendaciones mejora las tasas de conversión en las etapas del embudo:

**login → product_page → product_cart → purchase**

El resultado esperado era un incremento mínimo del 10% en cada etapa durante los primeros 14 días desde el registro del usuario.

---

## 🔍 Preparación y validación de los datos
Antes del análisis se realizaron validaciones clave para garantizar la confiabilidad del experimento:

- Conversión correcta de tipos de datos (fechas y timestamps)
- Verificación de valores nulos y duplicados
- Filtrado estricto por:
  - Región UE
  - Prueba recommender_system_test
  - Fechas oficiales del experimento
  - Eventos ocurridos dentro de los primeros 14 días
- Confirmación de no contaminación entre grupos (0 usuarios presentes en ambos grupos)

⚠️ Se detectó una desigualdad en el tamaño de los grupos, lo cual se consideró explícitamente al interpretar los resultados.

---

## 📊 Análisis del embudo de conversión
Se analizaron las tasas de conversión por etapa para ambos grupos:

- El grupo A mostró mejor conversión en la etapa inicial (login → product_page).
- El grupo B presentó mejores conversiones en las etapas posteriores del embudo.
- Se identificó un comportamiento atípico donde algunos usuarios realizan compras sin pasar por `product_cart`, lo cual fue interpretado y documentado como una particularidad del negocio.

---

## 📈 Análisis estadístico
Se aplicó una prueba Z para comparación de proporciones sobre la conversión a compra:
- Valor p = 0.0465
- α = 0.05

✅ El resultado indica una diferencia estadísticamente significativa entre los grupos.

---

## 🧠 Hallazgos claves
- El nuevo sistema de recomendaciones (grupo B) influye positivamente en la conversión final a compra.
- Existen diferencias de comportamiento de usuario que deben considerarse en el diseño del embudo.
- La desigualdad en el tamaño de los grupos puede afectar la potencia estadística, pero no invalida completamente la prueba.
- El análisis confirma la importancia de validar estructura, segmentación y calidad en pruebas A/B.

---

## 🛠️ Herramientas y habilidades aplicadas
- Python (Pandas, NumPy)
- Análisis exploratorio de datos (EDA)
- Pruebas estadísticas: Z-test para comparación de proporciones
- Visualización de datos: Matplotlib, Seaborn
- Data Wrangling: filtrado por región, fechas, eventos relevantes
- Análisis de embudos de conversión
- Validación de calidad de pruebas A/B

--- 

## 📌 Conclusión
A pesar de ciertas limitaciones en la ejecución del experimento, los resultados sugieren que el nuevo sistema de recomendaciones tiene un impacto positivo en la conversión final, por lo que se recomienda su implementación, acompañada de una futura prueba A/B con grupos balanceados.
