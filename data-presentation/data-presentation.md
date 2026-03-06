# Data Presentation Skill

## Propósito

Este skill permite estructurar proyectos de análisis de datos siguiendo una adaptación del método científico, generando presentaciones HTML profesionales que comunican efectivamente los hallazgos técnicos y de negocio.

---

## 📊 Método Científico: Tradicional vs Análisis de Datos

### Comparativa de Secciones

| Método Científico Tradicional | Proyectos de Análisis de Datos | Decisión | Razón |
|-------------------------------|--------------------------------|----------|--------|
| **1. Observación** | **Observación/Contexto** | ✅ **INCLUIR** | Establece el problema de negocio y el contexto del proyecto. Esencial para que la audiencia entienda por qué existe el análisis. |
| **2. Pregunta de investigación** | **Planteamiento del problema + Objetivos + Justificación** | ✅ **INCLUIR** | Define qué se quiere lograr. En análisis de datos, se combina con objetivos específicos y la justificación del negocio. Engancha a la audiencia desde el inicio. |
| **3. Revisión de literatura / Marco teórico** | *(No aplica)* | ❌ **OMITIR** | Los proyectos de análisis de datos no son investigación académica. No se está investigando fenómenos nuevos, sino resolviendo problemas de negocio con datos. |
| **4. Hipótesis** | *(No aplica)* | ❌ **OMITIR** | En análisis exploratorio muchas veces no se sabe qué se va a encontrar. Se responden preguntas de negocio específicas, no se prueban hipótesis científicas formales. |
| **5. Diseño metodológico** | *(Cubierto en Análisis de Datos)* | ❌ **OMITIR como sección separada** | Se cubre implícitamente en la sección de "Análisis de datos" donde se explican transformaciones, queries y pipelines. |
| **6. Recolección de datos** | **Fuentes de Datos** | ✅ **INCLUIR** | Fundamental en análisis de datos. Muestra de dónde vienen los datos, su calidad, granularidad y período. Demuestra rigor técnico. |
| *(No existe en ciencia tradicional)* | **Stack Tecnológico / Herramientas** | ✅ **INCLUIR** | Específico de proyectos técnicos. Muestra competencias técnicas y herramientas utilizadas (BigQuery, SQL, Python, etc.). Clave para reclutadores y audiencias técnicas. |
| **7. Experimentación / Análisis** | **Análisis de Datos** | ✅ **INCLUIR** | El core del trabajo. Incluye desarrollo de queries, pipelines, transformaciones de datos, y explicación técnica del proceso. Demuestra cómo se resolvió el problema. |
| **8. Resultados** | **Resultados** | ✅ **INCLUIR** | Los hallazgos concretos del análisis. Dashboards, visualizaciones, métricas obtenidas. La "respuesta" a las preguntas de negocio planteadas. |
| **9. Discusión** | **Recomendaciones** | ✅ **INCLUIR** (pero transformado) | En lugar de "discusión académica", se presentan **insights accionables** y recomendaciones estratégicas para el negocio. Muestra pensamiento estratégico. |
| **10. Conclusiones / Limitaciones** | *(No aplica como sección separada)* | ❌ **OMITIR** | Para portfolios puede sonar a "excusas". Las conclusiones se integran en Recomendaciones. Las limitaciones solo se mencionan si son críticas. |
| **11. Referencias bibliográficas** | *(No aplica)* | ❌ **OMITIR** | No es trabajo académico. Si se usan fuentes externas, se mencionan inline o en documentación técnica del README. |
| *(No existe en ciencia tradicional)* | **Próximos Pasos** | ✅ **INCLUIR** | Específico de proyectos técnicos. Demuestra visión de producto, escalabilidad y pensamiento iterativo. Da pie a conversaciones en entrevistas. |

---

## 🎯 Estructura Final para Proyectos de Análisis de Datos

### Secciones Obligatorias

1. **Portada**
   - Título del proyecto
   - Autor y credenciales
   - Stack tecnológico (badges)
   - Breve descripción (1-2 líneas)

2. **Observación / Contexto Actual**
   - Situación del negocio/problema observado
   - Contexto que motiva el análisis
   - Datos disponibles

3. **Planteamiento del Problema + Objetivos + Justificación**
   - Pregunta(s) de investigación específica(s)
   - Objetivos del proyecto (bullet points)
   - Por qué es importante resolver esto (justificación de negocio)

4. **Fuentes de Datos**
   - De dónde vienen los datos (plataforma, API, CSV, base de datos)
   - Granularidad (evento, orden, producto, usuario)
   - Período de tiempo analizado
   - Volumen de datos
   - Calidad/limitaciones de los datos (si es relevante)

5. **Stack Tecnológico / Herramientas Utilizadas**
   - Herramientas y tecnologías (BigQuery, SQL, Python, Looker Studio, etc.)
   - Pipeline de datos (diagrama de flujo visual)
   - Separar pipelines si hay múltiples módulos independientes

6. **Análisis de Datos**
   - Transformaciones aplicadas
   - Queries SQL principales (fragmentos clave)
   - Explicación de pipelines y procesos
   - Diagramas de flujo de transformación
   - Propósito de cada query/proceso

7. **Resultados**
   - Hallazgos clave (insights numerados)
   - Visualizaciones y dashboards
   - Métricas obtenidas
   - Patrones identificados

8. **Recomendaciones**
   - Acciones accionables basadas en los resultados
   - Implementaciones sugeridas
   - Impacto esperado de cada recomendación

9. **Próximos Pasos**
   - Mejoras técnicas planeadas (automatización, tiempo real, etc.)
   - Nuevas capacidades de análisis
   - Evolución del proyecto

10. **Cierre**
    - Resumen de conclusiones por módulo (si aplica)
    - Impacto esperado general
    - Información de contacto del autor

---

## 📋 Flujo de Trabajo del Skill

### Paso 1: Análisis Automático del README

El skill debe:

1. **Leer el README principal del proyecto**
2. **Identificar secciones existentes** que mapeen a la estructura del método científico:
   - Buscar títulos como: "Objetivo", "Descripción", "Fuente de datos", "Herramientas", "Análisis", "Resultados", "Conclusiones", etc.
3. **Extraer contenido relevante** de cada sección identificada
4. **Identificar gaps** (secciones faltantes que deberían existir)

### Paso 2: Mapeo de Secciones

Crear un mapeo claro entre lo encontrado y lo esperado:

```
Encontrado en README → Sección del Método Científico

"Objetivo del proyecto" → Planteamiento del problema + Objetivos
"Descripción" → Observación/Contexto
"Fuente de datos" → Fuentes de Datos
"Herramientas y tecnologías" → Stack Tecnológico
"Análisis detallado" → Análisis de Datos
...
```

### Paso 3: Confirmación con el Usuario

Presentar al usuario:

```
He analizado tu README y encontré las siguientes secciones mapeables:

✅ Encontradas:
- Objetivo del proyecto → Planteamiento del problema + Objetivos
- Descripción → Observación/Contexto
- Herramientas → Stack Tecnológico

⚠️ Secciones faltantes que recomiendo crear:
- Fuentes de Datos (información sobre origen de datos)
- Resultados (hallazgos clave del análisis)
- Recomendaciones (insights accionables)
- Próximos pasos (evolución del proyecto)

¿Estás de acuerdo con esta estructura? ¿Quieres modificar algo?
```

### Paso 4: Generación de la Presentación

Una vez confirmado, generar el HTML con:

1. **Estructura de slides** (una por sección principal)
2. **Contenido extraído del README** + contenido sugerido para secciones faltantes
3. **Formato visual estándar** (sin colores, pero estructura clara)

---

## 🎨 Especificaciones de HTML Estándar

### Principios de Diseño

El HTML generado por defecto (sin skill de diseño) debe ser:

- **Minimalista:** Sin colores llamativos, fondo blanco o gris muy claro
- **Legible:** Tipografía clara, buen espaciado, jerarquía visual mediante tamaños
- **Estructurado:** Secciones claramente diferenciadas
- **Responsive:** Funcional en desktop y mobile

### Estructura Base

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Nombre del Proyecto]</title>
  <style>
    /* Sistema de slides minimalista */
    /* Desktop: modo presentación */
    /* Mobile: scroll vertical con líneas divisoras */
  </style>
</head>
<body>
  <div class="slides-container">
    <!-- Slide 1: Portada -->
    <!-- Slide 2: Observación/Contexto -->
    <!-- Slide 3: Problema + Objetivos -->
    <!-- ... -->
  </div>

  <!-- Navegación (solo desktop) -->
  <script>
    // Sistema de navegación entre slides
  </script>
</body>
</html>
```

### CSS Estándar a Aplicar

```css
/* Base */
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  margin: 0;
  padding: 0;
  background: #fafafa;
  color: #333;
}

/* Slides en Desktop */
.slides-container {
  width: 100%;
  height: 100vh;
  overflow: hidden;
  position: relative;
}

.slide {
  position: absolute;
  top: 0; left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 60px 40px;
  opacity: 0;
  transition: opacity 0.4s ease;
}

.slide.active {
  opacity: 1;
}

.slide-content {
  max-width: 900px;
  width: 100%;
}

/* Tipografía */
h1 { font-size: 48px; font-weight: 700; margin-bottom: 16px; }
h2 { font-size: 36px; font-weight: 600; margin-bottom: 12px; }
h3 { font-size: 24px; font-weight: 600; margin-bottom: 10px; }
p { font-size: 16px; line-height: 1.6; color: #666; }

/* Listas */
ul, ol {
  font-size: 16px;
  line-height: 1.8;
  color: #666;
  padding-left: 24px;
}

/* Código */
code {
  font-family: 'Courier New', monospace;
  background: #f0f0f0;
  padding: 2px 6px;
  border-radius: 4px;
  font-size: 14px;
}

pre {
  background: #f5f5f5;
  padding: 16px;
  border-radius: 8px;
  overflow-x: auto;
  border: 1px solid #e0e0e0;
}

/* Mobile: Scroll vertical */
@media (max-width: 768px) {
  body {
    overflow-y: auto;
    overflow-x: hidden;
  }

  .slides-container {
    height: auto;
    overflow: visible;
  }

  .slide {
    position: relative;
    opacity: 1 !important;
    height: auto;
    min-height: 100vh;
    padding: 60px 20px;
    border-bottom: 1px solid rgba(0, 0, 0, 0.08);
  }

  .slide:last-child {
    border-bottom: none;
  }
}
```

---

## 📱 Consideraciones Responsive

### Desktop (ancho > 768px)

- **Modo presentación:** Una slide visible a la vez
- **Navegación:** Flechas izquierda/derecha, teclas de navegación
- **Dots de navegación:** Indicadores de progreso en la parte inferior
- **Transiciones:** Suaves entre slides

### Mobile (ancho ≤ 768px)

- **Modo scroll:** Todas las slides apiladas verticalmente
- **Scroll natural:** El usuario hace scroll hacia abajo
- **Líneas divisoras:** Bordes sutiles entre slides (`border-bottom: 1px solid rgba(0,0,0,0.08)`)
- **Sin línea final:** La última slide no tiene borde inferior
- **Navegación oculta:** No mostrar flechas ni dots
- **Altura automática:** Cada slide ocupa su altura natural (no forzar 100vh)
- **Padding:** Espaciado cómodo (60px 20px)

### Validación de Contenido

**El skill debe advertir si:**

1. **Una slide tiene demasiado contenido** (más de 800 palabras o más de 10 elementos)
   - Sugerencia: Dividir en múltiples slides

2. **Hay código SQL muy largo** (más de 50 líneas)
   - Sugerencia: Mostrar solo fragmento clave con enlace a archivo completo

3. **Muchas imágenes en una sola slide** (más de 3)
   - Sugerencia: Crear una slide de resultados por cada 2-3 insights principales

4. **Tablas muy anchas**
   - Sugerencia: Simplificar columnas o crear versión mobile-friendly

---

## 🔧 Instrucciones de Uso

### Caso 1: Solo con data-presentation (sin skill de diseño)

```
Usuario: "Crea un resumen HTML de mi proyecto usando data-presentation"

Respuesta esperada:
1. Analizar README
2. Mapear secciones
3. Confirmar con usuario
4. Generar HTML estándar minimalista
```

### Caso 2: Con data-presentation + datablog-design-v1

```
Usuario: "Crea un resumen HTML usando data-presentation para estructura y datablog-design-v1 para diseño"

Respuesta esperada:
1. data-presentation: Analiza y estructura contenido
2. datablog-design-v1: Aplica sistema de diseño avanzado (colores, gradientes, componentes)
3. Resultado: HTML con estructura del método científico + diseño profesional
```

---

## 🎓 Argumentación de Decisiones

### Por qué incluir "Stack Tecnológico"

- **Diferenciación:** Muestra competencias técnicas específicas
- **Keywords para reclutadores:** Facilita búsqueda de tecnologías (BigQuery, SQL, Python)
- **Comprensión del pipeline:** Ayuda a entender cómo fluyen los datos
- **Replicabilidad:** Otros pueden entender las herramientas necesarias

### Por qué omitir "Marco Teórico"

- **No es investigación académica:** No se están probando teorías científicas
- **Enfoque práctico:** El objetivo es resolver problemas de negocio, no contribuir al conocimiento científico
- **Audiencia diferente:** Stakeholders de negocio no esperan revisión literaria

### Por qué transformar "Discusión" en "Recomendaciones"

- **Orientado a acción:** Las empresas quieren saber QUÉ hacer con los hallazgos
- **Demuestra valor:** Muestra que puedes traducir datos en decisiones de negocio
- **Pensamiento estratégico:** Va más allá del análisis técnico

### Por qué incluir "Próximos Pasos"

- **Visión de producto:** Demuestra que piensas en la evolución del proyecto
- **Escalabilidad:** Muestra que entiendes que los proyectos son iterativos
- **Conversaciones en entrevistas:** Da pie a preguntas como "¿qué harías después?"
- **Diferenciación:** La mayoría de portfolios no tienen esta sección

---

## ✅ Checklist de Validación

Antes de generar el HTML final, verificar:

- [ ] Todas las secciones obligatorias están presentes
- [ ] El contenido de cada slide es apropiado para su longitud
- [ ] Hay variedad visual (no solo texto, incluye listas, código, imágenes)
- [ ] Las slides de "Análisis de Datos" incluyen código/queries con explicación
- [ ] Las slides de "Resultados" incluyen visualizaciones o descripciones claras
- [ ] Las "Recomendaciones" son accionables (tienen verbos de acción)
- [ ] Los "Próximos pasos" son realistas y alcanzables
- [ ] El responsive está considerado (líneas divisoras en mobile, padding adecuado)
- [ ] No hay slides vacías o con contenido placeholder
- [ ] La navegación funciona correctamente en desktop
- [ ] El scroll es natural en mobile

---

## 📝 Notas Adicionales

### Módulos Múltiples

Si el proyecto tiene múltiples módulos independientes (como el ejemplo de ecommerce-performance-insights con Módulo 1 GA4 y Módulo 2 Shopify):

1. **Secciones compartidas al inicio:**
   - Portada (única)
   - Contexto general
   - Problema y objetivos (mencionar ambos módulos)
   - Stack tecnológico (mostrar pipelines separados)

2. **Secciones por módulo:**
   - Slide separadora "Módulo 1 de 2"
   - Análisis de datos (específico del módulo)
   - Resultados (específico del módulo)
   - Recomendaciones (específico del módulo)

3. **Secciones compartidas al final:**
   - Próximos pasos (evolución general)
   - Cierre (resumen de ambos módulos)

### Datos Independientes vs Integrados

Si los módulos analizan **negocios diferentes** (como GA4 público vs Shopify simulado):
- Aclarar que son independientes y no se integran
- Explicar que en práctica profesional se aplicarían al mismo negocio

Si los módulos analizan el **mismo negocio**:
- Mostrar cómo se complementan
- Incluir slide de "Integración" si hay cruce de datos

---

## 🚀 Ejemplo de Prompt para el Usuario

```
Para usar este skill, ejecuta:

"Crea un resumen HTML de mi proyecto siguiendo data-presentation"

O con diseño avanzado:

"Crea un resumen HTML usando data-presentation para estructura y datablog-design-v1 para diseño"

El skill analizará tu README, mapeará las secciones al método científico adaptado,
y generará una presentación profesional lista para compartir con reclutadores o stakeholders.
```
