# Control de Versiones con Git y GitHub

> ***Nota importante**: Git se diseñó originalmente para gestionar código de software, pero resulta igualmente útil para cualquier profesional que trabaje con documentos, proyectos colaborativos o necesite mantener un historial de cambios. Escritores, diseñadores, investigadores, abogados, educadores, arquitectos y profesionales de cualquier disciplina pueden aprovechar las capacidades del control de versiones para mejorar su gestión documental y colaboración profesional.*

## ¿Por qué?

La gestión moderna de proyectos y documentos enfrenta un problema fundamental de control de cambios que genera costos significativos y riesgos operativos elevados. Cuando se trabajan proyectos sin un sistema de control de versiones, surgen problemas críticos que afectan tanto la productividad individual como la colaboración en equipo.

||Pérdida de versiones anteriores|Conflictos de colaboración|Ausencia de trazabilidad|
|:-:|:-:|:-:|:-:|
|**Impacto**|Un escritor modifica el capítulo final de su novela y necesita recuperar la versión previa que tenía mejor estructura narrativa, pero la ha sobrescrito irreversiblemente.|Múltiples profesionales trabajan simultáneamente sobre los mismos documentos sin coordinación, generando sobrescritura accidental del trabajo de otros miembros del equipo.|No existe registro histórico de qué cambios se realizaron, cuándo se ejecutaron, quién los implementó y por qué se tomaron esas decisiones.|
|**Consecuencia**|Pérdida de tiempo reconstruyendo contenido, incremento del riesgo de introducir inconsistencias y retraso en las entregas del proyecto.|Pérdida de trabajo realizado, duplicación de esfuerzos, tensiones en el equipo y dificultad para identificar qué cambios son válidos.|Imposibilidad de auditar el proyecto, dificultad para identificar el origen de errores y incapacidad para revertir cambios problemáticos de manera precisa.|

## ¿Qué?

Un sistema de control de versiones es una herramienta que registra los cambios realizados en archivos a lo largo del tiempo, de modo que se puede recuperar una versión específica más adelante. Permite mantener un historial completo de las modificaciones, identificar quién realizó cada cambio, cuándo se efectuó y por qué se implementó.

Los sistemas de control de versiones pueden ser centralizados, donde existe un único servidor que contiene todos los archivos versionados, o distribuidos, donde cada usuario mantiene una copia completa del historial del proyecto.

## ¿Para qué?

Los sistemas de control de versiones resuelven directamente cada uno de los problemas de gestión de cambios identificados:

|Frente a...|Pérdida de versiones anteriores|Conflictos de colaboración|Ausencia de trazabilidad|
|-|-|-|-|
|Los sistemas de control de versiones...|Garantizan que cada cambio quede registrado permanentemente en el historial, permitiendo recuperar cualquier versión previa del proyecto. Las confirmaciones funcionan como puntos de control que preservan el estado completo de los documentos en momentos específicos.|Proporcionan mecanismos de fusión automática y manual que permiten integrar cambios de múltiples colaboradores de forma controlada. Las ramas de trabajo aíslan las contribuciones individuales hasta que estén listas para integrarse.|Registran información completa de cada cambio: autor, fecha, descripción y archivos modificados. Esta información permite auditorías completas y facilita la identificación del origen de cualquier modificación.|

Estos sistemas permiten gestionar proyectos de cualquier escala, desde documentos individuales hasta colecciones complejas de archivos. Pueden manejar tanto archivos de texto como documentos binarios, imágenes, presentaciones y recursos digitales diversos, funcionando como un sistema de respaldo distribuido que protege contra pérdida de información.

Su aplicación práctica incluye

- Coordinación de equipos distribuidos geográficamente.
- Gestión de múltiples versiones de un proyecto en paralelo.
- Colaboración en tiempo real en documentos compartidos.

El control de versiones funciona como la infraestructura que facilita estos procesos, estableciendo las bases para flujos de trabajo colaborativos eficientes.

Git, como implementación específica de estos principios, se destaca por su eficiencia en la gestión distribuida y su capacidad para manejar proyectos de gran escala, convirtiéndose en la herramienta de referencia para materializar estos beneficios en la práctica profesional.

> **💡 Información detallada** Para una explicación exhaustiva sobre la necesidad del control de versiones, los problemas específicos que resuelve y cómo beneficia a diferentes profesionales, consultar: [Introducción al control de versiones](conceptos-fundamentales/01-introduccion.md)

## ¿Cómo?

### Modelo mental básico

La mayoría de profesionales han experimentado la situación de gestionar múltiples versiones de un documento importante. Un patrón típico produce archivos como "Propuesta_Cliente.docx", "Propuesta_Cliente_v2.docx", "Propuesta_Cliente_final.docx", "Propuesta_Cliente_final_revisado.docx". Este enfoque manual genera confusión sobre cuál es la versión actual, dificulta la recuperación de cambios anteriores y complica la colaboración.

**Git** es un sistema de control de versiones distribuido que se ha convertido en el estándar de la industria para la gestión de cambios en proyectos. Su enfoque distribuido permite que cada participante mantenga una copia completa del historial del proyecto, facilitando el trabajo offline y la colaboración descentralizada.

Git automatiza y perfecciona este proceso manual. En lugar de crear copias físicas de archivos, Git registra únicamente los cambios realizados, manteniendo un historial completo que permite recuperar cualquier versión anterior. Cada vez que se registra un conjunto de cambios, Git crea lo que se denomina una "confirmación" que funciona como una instantánea etiquetada del proyecto en ese momento específico.

**GitHub** es una plataforma de alojamiento en la nube que utiliza Git como motor de control de versiones, proporcionando una interfaz web y funcionalidades adicionales para la colaboración, gestión de proyectos y publicación de contenido. Esta plataforma fue adquirida por Microsoft en 2018 y se ha establecido como el servicio de referencia para alojar repositorios y coordinar trabajo colaborativo en proyectos de diversas disciplinas.

### Conceptos fundamentales

El sistema opera mediante cuatro espacios conceptuales que reflejan el flujo natural de trabajo:

**Directorio de trabajo**: La carpeta normal donde se realizan las modificaciones diarias. Aquí se editan documentos, se crean archivos nuevos y se organizan los materiales del proyecto, exactamente como se haría sin control de versiones.

**Área de preparación**: Un espacio intermedio donde se seleccionan los cambios que se desean registrar permanentemente. No todos los cambios realizados en una sesión de trabajo necesitan registrarse al mismo tiempo, permitiendo agrupar modificaciones relacionadas.

**Repositorio local**: El archivo histórico completo del proyecto que reside en la máquina de trabajo. Contiene todas las versiones anteriores, permitiendo acceder al historial completo sin conexión a internet.

**Repositorio remoto**: Una copia del proyecto alojada en un servidor que facilita la colaboración. Todos los miembros del equipo pueden sincronizar sus cambios a través de este repositorio central.

### Flujo de trabajo cotidiano

El proceso de trabajo sigue un patrón repetible que se integra naturalmente con las rutinas profesionales habituales:

**Modificación**: Se realizan cambios en los archivos del proyecto utilizando las herramientas habituales de cada disciplina. Un escritor edita su texto en Word, un diseñador modifica gráficos en Photoshop, un investigador actualiza datos en Excel.

**Selección**: Se identifican qué cambios están listos para ser registrados permanentemente. Esto permite separar experimentos o trabajo parcial de modificaciones definitivas que se desean preservar en el historial.

**Registro**: Se crea una confirmación que captura el estado actual de los archivos seleccionados junto con una descripción del trabajo realizado. Esta descripción debe explicar qué se cambió y por qué se realizó la modificación.

**Sincronización**: Se envían los cambios registrados al repositorio remoto para que estén disponibles para otros colaboradores, y se obtienen las modificaciones realizadas por otros miembros del equipo.

### Implementación técnica

Git utiliza una interfaz de línea de comandos para ejecutar estas operaciones. Aunque inicialmente puede resultar desconocida para usuarios no técnicos, los comandos básicos siguen una lógica intuitiva:

**Configuración inicial del entorno de trabajo:**

```bash
git config --global user.name "Ibuprofeno Fernandez"
git config --global user.email "ibuprofeno.fernandez@gmail.com"
```

Estos comandos establecen la identidad del usuario para que todas las confirmaciones queden registradas con la información correcta del autor.

**Inicialización de un proyecto nuevo:**

```bash
git init
```

Convierte una carpeta normal en un repositorio Git, habilitando el seguimiento de cambios en todos los archivos contenidos.

**Obtención de un proyecto existente:**

```bash
git clone https://github.com/usuario/proyecto.git
```

Descarga una copia completa de un proyecto remoto, incluyendo todo su historial de versiones.

**Gestión diaria de cambios:**

```bash
git status
```

Muestra qué archivos han sido modificados desde la última confirmación, proporcionando una visión clara del estado actual del trabajo.

```bash
git add documento.txt
```

Selecciona un archivo específico para incluir en la próxima confirmación. Este paso permite elegir exactamente qué cambios registrar.

```bash
git add .
```

Selecciona todos los archivos modificados en el directorio actual, útil cuando se desea registrar todos los cambios realizados.

```bash
git commit -m "Actualizar conclusiones del capítulo 3"
```

Crea una confirmación con los archivos seleccionados y una descripción clara de las modificaciones realizadas.

**Colaboración con el equipo:**

```bash
git push
```

Envía las confirmaciones locales al repositorio remoto, haciéndolas disponibles para otros colaboradores.

```bash
git pull
```

Obtiene las confirmaciones realizadas por otros miembros del equipo e integra sus cambios en la copia local del proyecto.

### Gestión de versiones y ramas

Para proyectos complejos, Git permite crear ramas de trabajo independientes. Una rama representa una línea de desarrollo paralela donde se pueden realizar experimentos o desarrollar características específicas sin afectar la versión principal del proyecto.

```bash
git branch nueva-caracteristica
git checkout nueva-caracteristica
```

Estos comandos crean una nueva rama y cambian el contexto de trabajo a ella, permitiendo realizar modificaciones experimentales sin riesgo.

```bash
git checkout main
git merge nueva-caracteristica
```

Una vez completado el trabajo en la rama experimental, estos comandos regresan a la rama principal e integran los cambios desarrollados.

### Casos de uso específicos

**Para escritores y editores:** Git permite experimentar con diferentes estructuras narrativas, mantener versiones en múltiples idiomas, y colaborar con editores manteniendo un registro completo de todas las sugerencias y modificaciones.

**Para diseñadores:** Facilita la gestión de variaciones de diseño, el mantenimiento de bibliotecas de recursos visuales actualizadas, y la colaboración en proyectos creativos complejos donde múltiples personas contribuyen elementos visuales.

**Para investigadores:** Proporciona trazabilidad completa en el análisis de datos, permite mantener versiones de papers académicos con todas las revisiones de pares, y facilita la replicación de resultados manteniendo registro de las metodologías utilizadas.

**Para profesionales empresariales:** Garantiza que documentos críticos como contratos, propuestas comerciales y políticas corporativas mantengan un historial completo de modificaciones con información de autoría y justificación de cambios.

## Casos de uso por disciplina

### Escritura y edición

- Gestión de manuscritos con múltiples revisiones.
- Colaboración en libros y publicaciones académicas.
- Control de versiones en guiones y contenido creativo.

### Diseño y creatividad

- Seguimiento de evolución en proyectos de diseño gráfico.
- Gestión de recursos visuales y activos creativos.
- Colaboración en campañas publicitarias.

### Investigación y academia

- Control de versiones en papers de investigación.
- Gestión de datos experimentales y análisis.
- Colaboración en proyectos de investigación multidisciplinarios.

### Ámbito legal y empresarial

- Seguimiento de cambios en contratos y documentos legales.
- Gestión de propuestas comerciales y licitaciones.
- Control de versiones en políticas y procedimientos.

## Estructura del repositorio

```
├── README.md                 # Este archivo
├── conceptos-fundamentales/
│   ├── 01-introduccion.md
│   ├── 02-repositorios.md
│   └── 03-confirmaciones.md
├── comandos-basicos/
│   ├── configuracion.md
│   ├── gestion-cambios.md
│   └── colaboracion.md
├── flujos-trabajo/
│   ├── flujo-personal.md
│   ├── flujo-colaborativo.md
│   └── flujo-empresarial.md
├── ejercicios-practicos/
│   ├── nivel-basico/
│   ├── nivel-intermedio/
│   └── nivel-avanzado/
└── recursos/
    ├── comandos-referencia.md
    ├── solucion-problemas.md
    ├── herramientas-graficas.md
    └── bibliografia.md
```

## ¿Cuándo?

El control de versiones debe implementarse desde el inicio de cualquier proyecto que involucre múltiples archivos, colaboración entre personas o necesidad de mantener un historial de cambios. Se aplica especialmente en situaciones donde se requiere coordinar trabajo en equipo, preservar versiones importantes del trabajo o mantener trazabilidad de decisiones tomadas.

## ¿Alternativas?

Comparación con otros sistemas de gestión de versiones:

**Subversion (SVN)**: Sistema centralizado con menor complejidad inicial pero limitaciones para trabajo desconectado y gestión de ramas.

**Mercurial**: Sistema distribuido similar a Git con sintaxis más simple pero menor adopción en la industria.

**Sistemas propietarios**: Soluciones como SharePoint o Google Drive con capacidades básicas de versionado pero funcionalidades limitadas para colaboración avanzada.

## ¿Y ahora qué?

Una vez dominados los conceptos fundamentales, se recomienda explorar flujos de trabajo específicos según el contexto profesional, integración con herramientas de productividad existentes, y estrategias avanzadas de colaboración. El dominio de interfaces gráficas como GitHub Desktop, integración con editores de texto, y automatización de tareas repetitivas amplía significativamente las capacidades de gestión documental y colaboración profesional.
