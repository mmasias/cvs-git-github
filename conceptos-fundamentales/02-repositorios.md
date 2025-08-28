# El repositorio

## ¿Por qué?

### La necesidad de comprender dónde se almacena la información

Al comenzar con Git, aparecen conceptos como "repositorio local", "repositorio remoto", "directorio de trabajo" que generan confusión. Sin entender estos conceptos fundamentales, las operaciones cotidianas se vuelven mecánicas y los errores resultan incomprensibles.

Problemas típicos por falta de comprensión:

- **"No sé dónde están mis cambios"**: Confusión entre lo que está en el directorio de trabajo, el área de preparación, y lo que está realmente guardado en el historial.

- **"Mi colaborador no ve mis cambios"**: No entender la diferencia entre repositorio local y remoto, y cuándo la información se sincroniza.

- **"Perdí mi trabajo"**: No comprender que Git tiene múltiples espacios de almacenamiento y cómo recuperar información de cada uno.

## ¿Qué?

Un **repositorio** es la estructura organizacional que contiene de manera sistemática y completa toda la información de un proyecto: archivos, historial de cambios, metadatos de autoría y configuración. Funciona como un archivo histórico inteligente que preserva no solo el estado actual, sino la evolución completa del trabajo.

### Arquitectura fundamental

Los sistemas de control de versiones organizan esta información mediante una arquitectura de espacios conceptuales que refleja el flujo natural de trabajo:

|Espacio|Ubicación|Propósito|Contenido|
|-|-|-|-|
|**Directorio de trabajo**|Máquina local|Edición diaria|Archivos en su estado actual, modificables con herramientas habituales|
|**Área de preparación**|Máquina local|Selección de cambios|Cambios específicos marcados para registro permanente|
|**Repositorio local**|Máquina local|Historial completo|Todas las versiones confirmadas del proyecto con metadatos completos|
|**Repositorio remoto**|Servidor externo|Coordinación colaborativa|Copia autorizada del proyecto accesible para sincronización|

### Tipos de repositorios según distribución

|Repositorios locales|Repositorios remotos|
|-|-|
|Residen en la máquina de trabajo del usuario|Alojados en servidores especializados (GitHub, GitLab, Bitbucket)|
|Contienen historial completo, permitiendo trabajo desconectado|Facilitan colaboración mediante acceso compartido|
|Proporcionan rendimiento óptimo para operaciones frecuentes|Actúan como respaldo distribuido y punto de sincronización|
|Funcionan como copia personal del proyecto|Establecen la versión de referencia para el equipo|

## ¿Para qué?

### Resolución de problemas de gestión de información

La arquitectura de repositorios resuelve los problemas de confusión informacional mencionados:

|Problema|Solución mediante repositorios|Beneficio|
|-|-|-|
|"No sé dónde están mis cambios"|Espacios conceptuales claramente definidos con propósitos específicos|Claridad sobre el estado y ubicación de toda modificación|
|"Mi colaborador no ve mis cambios"|Distinción explícita entre repositorio local y remoto con operaciones de sincronización|Control preciso sobre cuándo y qué información se comparte|
|"Perdí mi trabajo"|Múltiples niveles de almacenamiento con recuperación granular|Protección integral contra pérdida de información|

> **💡 Para beneficios conceptuales:** Los beneficios sobre aprendizaje, innovación y documentación del proceso creativo se desarrollan en [El proceso de creación](04-04-procesoDeCreacion.md).

## ¿Cómo?

### Modelo conceptual básico

En lugar de gestionar información como:

```text
ProyectoX/
├── version_inicial/
├── version_con_cambios_cliente/
├── version_definitiva/
├── version_definitiva_real/
└── version_para_entrega/
    ├── copia_seguridad_2024/
    └── ultima_version_buena/
```

El repositorio mantiene **una ubicación unificada** con **múltiples estados históricos navegables**:

```text
ProyectoX/ (repositorio con historial completo)
├── Estado actual (visible para edición)
├── Historial navegable
│   ├── [abc123] Estructura inicial (15 Feb 2025)
│   ├── [def456] Incorporar feedback cliente (18 Feb 2025)
│   ├── [ghi789] Revisar propuesta técnica (22 Feb 2025)
│   ├── [jkl012] Ajustes finales presentación (25 Feb 2025)
│   └── [mno345] Versión para entrega (28 Feb 2025)
└── Configuración de sincronización remota
```

### Operaciones que conectan los espacios

La información se mueve entre los cuatro espacios mediante operaciones específicas:

- **`add`**: Mueve cambios del directorio de trabajo al área de preparación
- **`commit`**: Registra los cambios preparados como una nueva versión en el repositorio local
- **`push`**: Envía las confirmaciones locales al repositorio remoto
- **`pull`**: Trae cambios del repositorio remoto e integra en local y directorio de trabajo
- **`fetch`**: Obtiene cambios del remoto sin integrarlos automáticamente
- **`checkout`**: Cambia el directorio de trabajo a una versión específica del historial
- **`reset`**: Mueve cambios desde el área de preparación de vuelta al directorio de trabajo

### Visualización del flujo de información

<div align=center>

|![](/images/modelosUML/flujoInformacionRepositorio.svg)
|:-:
|[Código fuente](/modelosUML/flujoInformacionRepositorio.puml)

</div>


### Operaciones de consulta y gestión

Además del flujo básico, existen operaciones para consultar el estado y gestionar los contenidos:

<div align=center>

|![](/images/modelosUML/operacionesConsultaGestion.svg)
|:-:
|[Código fuente](/modelosUML/operacionesConsultaGestion.puml)

</div>

### Implementación práctica con Git

**Configuración inicial del entorno:**

```bash
git config --global user.name "Profesional Apellidos"
git config --global user.email "profesional@organizacion.com"
```

**Creación de nuevo repositorio:**

```bash
mkdir proyecto-importante
cd proyecto-importante  
git init
```

**Obtención de repositorio existente:**

```bash
git clone https://github.com/organizacion/proyecto-importante.git
```

**Ciclo básico de trabajo:**

```bash
# Verificar estado actual
git status

# Seleccionar cambios para registro
git add documento-principal.md
git add recursos/

# Crear confirmación con descripción clara
git commit -m "Actualizar metodología de análisis según revisión experta"

# Sincronizar con repositorio remoto
git push origin main
```

**Coordinación colaborativa:**

```bash
# Obtener cambios de colaboradores
git pull origin main

# Verificar historial del proyecto
git log --oneline --graph

# Comparar versiones específicas
git diff HEAD~2 HEAD
```

### Decisiones sobre estructura de repositorios

|Repositorio único|Múltiples repositorios|Repositorios anidados|
|-|-|-|
|**Usar cuando**: Proyecto cohesivo con componentes interdependientes|**Usar cuando**: Componentes independientes con ciclos de vida diferentes|**Usar cuando**: Jerarquías complejas con dependencias externas|
|**Ejemplo**: Libro con capítulos, anexos y recursos|**Ejemplo**: Empresa con website, marketing y documentación|**Ejemplo**: Proyecto con bibliotecas de terceros específicas|
|**Ventaja**: Historial unificado, sincronización automática|**Ventaja**: Permisos granulares, equipos especializados|**Ventaja**: Gestión precisa de dependencias externas|

### Configuración local vs remota

|Solo repositorio local|Repositorio con remoto|Múltiples remotos|
|-|-|-|
|**Usar cuando**: Trabajo completamente individual sin necesidad de respaldo externo|**Usar cuando**: Colaboración o respaldo necesarios|**Usar cuando**: Colaboración con múltiples organizaciones o proveedores|
|**Limitación**: Sin respaldo, sin colaboración posible|**Estándar**: La mayoría de casos profesionales|**Avanzado**: Proyectos complejos con stakeholders diversos|

### Estrategias por escala de proyecto

|Proyectos individuales|Equipos pequeños (2-10 personas)|Organizaciones grandes|
|-|-|-|
|Repositorio local con respaldo remoto ocasional|Flujo centralizado con rama principal estable|Modelo distribuido con múltiples niveles de integración|
|Confirmaciones descriptivas para referencia personal|Revisión por pares antes de integración|Workflows automatizados con gates de calidad|
|Ramificación mínima, enfoque en linealidad|Ramas por característica o experimento|Ramas por equipo, producto y release|
|Sincronización manual según necesidades|Integración continua con testing automatizado|Pipelines de despliegue con múltiples entornos|

## Siguiente paso

Una vez comprendida la estructura organizacional que proporciona el repositorio, el siguiente elemento fundamental son las **confirmaciones**: las unidades atómicas que componen el historial y permiten navegar entre diferentes estados del proyecto: [Confirmaciones](03-confirmaciones.md).
