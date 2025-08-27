# Introducción al control de versiones

## ¿Por qué?

### El problema universal de gestión de cambios

Consideremos estas situaciones comunes:

- **Escritor**: Modifica el capítulo final de una novela eliminando una escena importante. Dos días después se da cuenta de que la necesita, pero la ha sobrescrito irreversiblemente.

- **Diseñador**: El cliente solicita "volver a la versión anterior" del logo, pero existen 15 archivos llamados `logo_final_definitivo.psd` y resulta imposible recordar cuál era la que le gustaba.

- **Investigador**: Colabora con tres colegas en un paper importante. Cada uno edita el documento por separado y cuando se intenta combinar los cambios, se descubre que dos personas eliminaron párrafos diferentes que el tercero necesitaba.

- **Profesional empresarial**: El supervisor solicita explicar por qué se cambió una política corporativa el mes pasado, quién la cambió y cuál era la justificación, pero no existe registro de las modificaciones.

### Los costos reales de la desorganización

Esta falta de control genera:

|Pérdida de ... |Tiempo|Calidad|Dinero|Confianza|Estrés (innecesario)|
|-|-|-|-|-|-|
|**Por ...**|reconstruir trabajo perdido o buscar entre versiones confusas|introducir inconsistencias al combinar cambios mal coordinados|rehacer trabajo, extender fechas de entrega, o perder oportunidades|clientes, colaboradores o supervisores que pierden fe en la capacidad de gestión|incertidumbre por posibles pérdidas de trabajo importante |

## ¿Qué?

Un **sistema de control de versiones** es una herramienta que registra automáticamente los cambios realizados en archivos a lo largo del tiempo, creando un historial navegable y seguro del trabajo.

### Características esenciales

|Registro temporal completo|Información de autoría|Gestión de ramas paralelas|Colaboración coordinada|
|-|-|-|-|
|Cada modificación queda registrada con timestamp exacto|Identificación clara de quién realizó cada cambio|Múltiples líneas de desarrollo simultáneo|Mecanismos para que múltiples personas trabajen simultáneamente|
|Posibilidad de volver a cualquier punto en el tiempo|Contexto sobre las razones del cambio|Experimentación segura sin afectar versión principal|Detección y resolución de conflictos de edición|
|Comparación entre versiones diferentes del mismo archivo|Trazabilidad completa para auditorías o análisis|Fusión inteligente de cambios paralelos|Sincronización controlada entre participantes|

### Tipos de sistemas

|Centralizados|Distribuidos|
|-|-|
|Un servidor central contiene la "verdad única"|Cada participante tiene una copia completa del historial|
|Los colaboradores obtienen copias de trabajo locales|Trabajo completamente offline|
|Requiere conexión al servidor para la mayoría de operaciones|Mayor flexibilidad para modelos de colaboración complejos|
|***Subversion***|***Git***|

## ¿Para qué?

### Beneficios inmediatos

|Seguridad del trabajo|Confianza en la experimentación|Colaboración sin fricción|
|-|-|-|
|Backup automático e incremental de cada cambio|Permite probar cambios drásticos sin riesgo|Coordina trabajo con cualquier número de colaboradores|
|Imposibilidad de perder trabajo accidentalmente|Posibilita crear versiones alternativas sin duplicar archivos|Integra cambios automáticamente cuando es posible|
|Recuperación granular: desde líneas específicas hasta proyectos completos|Facilita abandonar experimentos fallidos sin consecuencias|Resuelve conflictos de manera controlada cuando es necesario|

### Casos de uso por profesión

|Escritores y editores|Diseñadores y creativos|Investigadores y académicos|Profesionales empresariales|Desarrolladores de software|
|-|-|-|-|-|
|Gestión de múltiples borradores y revisiones|Exploración de conceptos alternativos sin perder versiones anteriores|Coautoría en papers con seguimiento detallado de contribuciones|Control de versiones en documentos críticos (contratos, políticas)|Coordinación de equipos trabajando en funcionalidades paralelas|
|Colaboración con editores manteniendo historial de sugerencias|Colaboración en campañas complejas con múltiples recursos|Gestión de conjuntos de datos y análisis con reproducibilidad garantizada|Auditoría completa de cambios para cumplimiento normativo|Gestión de versiones y despliegue de aplicaciones|
|Mantenimiento de versiones en diferentes idiomas o formatos|Gestión de bibliotecas de recursos reutilizables|Documentación de metodologías y decisiones de investigación|Gestión de propuestas y licitaciones complejas|Depuración mediante análisis histórico de cambios|

### Beneficios a largo plazo

|Conocimiento institucional|Calidad mejorada|
|-|-|
|El historial de cambios documenta decisiones y razonamientos|Los procesos de revisión se vuelven naturales y documentados|
|Nuevos colaboradores pueden entender la evolución del proyecto|Posibilidad de análisis retrospectivo para mejorar procesos|
|Preservación del contexto aunque cambien los participantes|Identificación de patrones problemáticos antes de que escalen|

## ¿Cuándo?

### Señales de que se necesita

|Implementación inmediata recomendada|Implementación muy recomendada|Implementación recomendada|
|-|-|-|
|Se ha perdido trabajo importante al menos una vez|El trabajo es crítico para la organización|Se desea mejorar la organización personal|
|Existe colaboración con otras personas en archivos compartidos|Los archivos evolucionan significativamente a lo largo del tiempo|Existe interés en aprender herramientas que usan profesionales avanzados|
|El trabajo pasa por procesos de revisión o aprobación|Se necesita documentar decisiones y cambios para auditorías|Se trabaja en proyectos de larga duración|
|Se requiere mantener múltiples versiones activas del mismo proyecto|Se trabaja con archivos de texto plano (código, configuraciones, documentación)|Se valora la tranquilidad de tener backup automático inteligente|


### Tipos de archivo que se benefician más

|Ideales|Funciona bien|Limitaciones|
|-|-|-|
|Documentos de texto plano (Markdown, LaTeX, HTML, CSS, TXT)|Documentos de oficina (Word, Excel, PowerPoint, Keynote)|Archivos binarios muy grandes (videos, audio)|
|Código fuente en cualquier lenguaje|Archivos de diseño vectorial|Formatos propietarios complejos donde los cambios no son visibles|
|Archivos de configuración|Documentos estructurados con cambios frecuentes|Archivos que cambian automáticamente (logs, caches)|
|Scripts y automatizaciones|||

## ¿Cómo?

### El modelo mental básico

En lugar de gestionar archivos como:

```text
documento.docx
documento_v2.docx
documento_v2_revisado.docx
documento_FINAL.docx
documento_FINAL_REAL.docx
```

El control de versiones mantiene **un solo archivo** con **múltiples versiones registradas internamente**:

```text
documento.docx (con historial completo navegable)
├── Versión inicial (15 Feb 2025)
├── Añadir sección metodología (18 Feb 2025)  
├── Revisar conclusiones (22 Feb 2025)
├── Correcciones de estilo (25 Feb 2025)
└── Versión actual (28 Feb 2025)
```

### Flujo de trabajo fundamental

<div align=center>

![](/images/modelosUML/flujoTrabajoFundamental.svg)

</div>

### Git como implementación práctica

**Git** es el sistema de control de versiones más popular del mundo, usado por millones de profesionales. Características destacadas:

- **Distribuido**: Cada persona tiene copia completa del historial
- **Eficiente**: Maneja proyectos desde individuales hasta masivos
- **Flexible**: Soporta cualquier flujo de trabajo colaborativo
- **Maduro**: Más de 15 años de desarrollo y refinamiento
- **Universal**: Integrado en prácticamente todas las herramientas profesionales

**GitHub** es la plataforma de alojamiento más popular para repositorios Git, proporcionando interfaz web y funcionalidades adicionales de colaboración.

## Siguiente paso

Una vez comprendido **por qué** se necesita control de versiones y **qué** ofrece, el siguiente paso es entender **cómo** Git organiza la información: el concepto de [repositorio](02-repositorios.md).