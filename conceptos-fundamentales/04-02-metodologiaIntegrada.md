# Metodología integrada: ejemplo práctico

## ¿Por qué?

### El problema de la coexistencia descoordinada

Los equipos que conocen metodologías de gestión (como RUP) y Git como herramienta enfrentan un problema de integración práctica que genera ineficiencias operativas significativas. Cuando se aplican estas aproximaciones de forma separada, surgen conflictos de autoridad y duplicación de esfuerzos que afectan la productividad del proyecto.

Sin una estructura clara de gobernanza, se presentan situaciones problemáticas recurrentes:

- **Desalineación temporal**: El gestor de proyecto define hitos según la metodología mientras los desarrolladores gestionan versiones según Git, creando descoordinación temporal
- **Criterios contradictorios**: Los criterios de calidad se evalúan desde la perspectiva de fases metodológicas sin considerar el estado real del repositorio
- **Responsabilidades solapadas**: Las responsabilidades se solapan entre roles de gestión y permisos Git, causando confusión operativa sobre quién puede autorizar qué acciones específicas

## ¿Qué?

Un esquema de gobernanza integrado es un marco que establece relaciones jerárquicas claras entre la metodología de gestión y la herramienta Git, definiendo responsabilidades complementarias donde cada sistema gobierna su dominio específico sin conflicto con el otro.

Este esquema determina que la metodología funciona como la capa de planificación y control de gestión, mientras Git opera como la capa de ejecución técnica y trazabilidad. Se establecen puntos de sincronización donde ambos sistemas se coordinan, y se definen mecanismos de resolución para situaciones donde sus criterios aparentemente divergen.

## ¿Para qué?

### Resolución de problemas de coordinación

La integración gobernada resuelve directamente cada problema de coordinación identificado mediante la asignación clara de dominios de autoridad:

|Problema|Solución metodológica|Solución técnica|Coordinación|
|-|-|-|-|
|**Desalineación temporal**|La metodología define marcos temporales estratégicos (fases, iteraciones, hitos)|Git ejecuta la secuencia táctica de integración|Las entregas técnicas respetan los compromisos de gestión sin sacrificar calidad técnica|
|**Criterios contradictorios**|Metodología mantiene autoridad sobre criterios de completitud de fase y objetivos de negocio|Git conserva control sobre estabilidad técnica e integridad de código|Ambos criterios deben cumplirse para avanzar|
|**Solapamiento de responsabilidades**|Se mapean roles metodológicos a responsabilidades específicas en Git|Se implementan permisos técnicos coherentes con la estructura organizacional|Eliminación de ambigüedad sobre autorización de operaciones críticas|

### Beneficios de la integración

|Coordinación natural|Resolución eficiente|Trazabilidad completa|
|-|-|-|
|Facilitación de coordinación entre equipos distribuidos|Reducción de tiempo de resolución de conflictos operativos|Establecimiento de trazabilidad desde decisiones de negocio hasta implementación técnica|
|Sincronización automática entre planificación y ejecución|Procesos claros para escalar y resolver discrepancias|Auditoría bidireccional entre metodología y repositorio|
|Alineación de objetivos entre gestión y desarrollo|Definición clara de autoridades y responsabilidades|Documentación automática de decisiones y su implementación|

## ¿Cuándo?

### Señales de necesidad de integración

|Integración inmediata|Integración muy recomendada|Integración recomendada|
|-|-|-|
|Existen conflictos frecuentes entre gestión de proyecto y gestión técnica|Se requiere coordinación entre múltiples interesados con perspectivas diferentes|Se planifica crecimiento significativo del equipo o la complejidad del proyecto|
|Los hitos de gestión no se correlacionan con el estado real del desarrollo|Se trabaja con plazos críticos donde la coordinación es fundamental|Se valora la profesionalización y documentación de procesos|
|Hay confusión regular sobre autoridades y responsabilidades en decisiones técnicas|Se necesita trazabilidad completa para auditorías o análisis retrospectivo|Se desea establecer procesos escalables y repetibles|

### Contextos organizacionales apropiados

|Equipos distribuidos|Proyectos corporativos complejos|Entornos regulados|
|-|-|-|
|Coordinación asíncrona entre múltiples zonas horarias|Múltiples interesados con diferentes perspectivas técnicas y de negocio|Auditorías externas y trazabilidad obligatoria|
|Necesidad de estándares que funcionen sin supervisión directa|Integración crítica entre objetivos de negocio e implementación técnica|Separación clara de responsabilidades y autoridades|
|Diferentes niveles de experiencia que requieren procesos claros|Gestión de riesgos que requiere visibilidad completa del estado del proyecto|Cumplimiento con normativas específicas de la industria|

## ¿Cómo?

### Principio rector fundamental

**La metodología gobierna la estrategia, Git gobierna la táctica**

- **Metodología responde**: Qué se entrega, cuándo se entrega, qué criterios debe cumplir
- **Git responde**: Cómo se integra, quién contribuyó específicamente, cómo se rastrea la evolución

### Mapeo de autoridades por dominio

|Dominio|Autoridad metodológica|Autoridad Git|Mecanismo de coordinación|
|-|-|-|-|
|**Temporal**|Define fases, iteraciones y plazos|Ejecuta secuencia de integración respetando plazos|Hitos metodológicos = Tags Git|
|**Calidad**|Establece criterios de completitud funcional|Garantiza estabilidad técnica y ausencia de regresiones|Ambos criterios deben cumplirse para versiones|
|**Responsabilidad**|Define roles y responsabilidades de gestión|Implementa permisos técnicos y flujos de trabajo|Roles metodológicos mapean a responsabilidades Git específicas|
|**Trazabilidad**|Requiere auditoría de decisiones y cumplimiento|Proporciona historial técnico granular automáticamente|Commits referencian artefactos metodológicos, artefactos referencian commits|

### Estructura operativa integrada

**Fases metodológicas como estrategia Git:**

|Fase metodológica|Estrategia Git correspondiente|Propósito|
|-|-|-|
|**Inicio**|Repositorio central con ramas experimentales|Exploración de viabilidad técnica|
|**Elaboración**|Ramas por componente arquitectural|Desarrollo paralelo de fundamentos|
|**Construcción**|Flujo feature-branch con integración continua|Alineación con iteraciones metodológicas|
|**Transición**|Tags de versión coordinados con criterios de finalización|Sincronización entre entrega metodológica y técnica|

**Roles metodológicos como responsabilidades Git:**

|Rol metodológico|Responsabilidad Git|Autoridad específica|
|-|-|-|
|**Gestor de proyecto**|Autorización de tags de hito|Decisiones de alcance para versiones|
|**Arquitecto**|Control de merges a ramas principales|Aprobación de cambios estructurales|
|**Líder técnico**|Gestión de ramas de equipo|Coordinación de integración de funcionalidades|
|**Desarrollador**|Commits de calidad en ramas asignadas|Responsabilidad de implementación específica|
|**Validador**|Bloqueo de merges sin criterios cumplidos|Control de calidad técnica|

### Flujo de decisiones operativas

**Para cambios de desarrollo:**
1. **Validación metodológica**: ¿El cambio corresponde a disciplinas activas en la iteración actual?
2. **Ejecución Git**: Creación de rama, desarrollo, commit, push, solicitud de integración
3. **Evaluación metodológica**: ¿El resultado cumple criterios de aceptación de la fase?
4. **Integración Git**: Merge a rama correspondiente si ambas validaciones son positivas

**Para versiones:**
1. **Evaluación metodológica**: ¿Se alcanzaron objetivos y criterios de la fase correspondiente?
2. **Verificación Git**: ¿El código en rama principal es estable y desplegable?
3. **Autorización metodológica**: Decisión go/no-go basada en criterios de negocio y técnicos
4. **Ejecución Git**: Creación de tag, ramificación para mantenimiento si corresponde

### Resolución de conflictos

**Cuando metodología y Git presentan criterios aparentemente contradictorios:**

|Tipo de conflicto|Precedencia|Adaptación requerida|
|-|-|-|
|**Conflicto temporal**|La metodología tiene precedencia sobre cuándo debe completarse una entrega|Git debe adaptar flujo técnico para cumplir compromiso sin sacrificar estabilidad mínima|
|**Conflicto de calidad técnica**|Git mantiene veto sobre integraciones que comprometan estabilidad|La metodología debe ajustar expectativas temporales hasta resolución técnica|
|**Conflicto de alcance**|Gestor de proyecto arbitra qué funcionalidades se incluyen en versión específica|Git implementa decisión mediante gestión de ramas y merges|

**Escalación:**
- **Conflictos técnicos**: Líder técnico → Arquitecto → Director técnico
- **Conflictos de alcance/tiempo**: Gestor de proyecto → Interesado correspondiente
- **Conflictos de proceso**: Gestor de proyecto + Arquitecto → Decisión conjunta

### Implementación práctica

**Sincronización de artefactos:**
- Issues/Historias de usuario (metodología) se referencian en commits (Git)
- Commits (Git) se documentan en informes de iteración (metodología)
- Tags Git corresponden exactamente a hitos metodológicos
- Ramas Git reflejan estructura de trabajo definida por disciplinas metodológicas

**Métricas integradas:**
- Velocidad metodológica se calcula basándose en commits y merges Git efectivos
- Gates de calidad metodológicos incluyen métricas de Git (cobertura de pruebas, estado de revisión de código)
- Reportes metodológicos incorporan automáticamente trazabilidad técnica de Git

## Siguiente paso

Esta metodología integrada proporciona un ejemplo concreto de cómo coordinar gestión y herramientas técnicas. El siguiente paso es explorar los [comandos básicos de Git](../comandos-basicos/configuracion.md) aplicando estos principios metodológicos desde el inicio, en lugar de aprender comandos aislados sin contexto organizacional.

> **💡 Nota práctica**: Esta integración requiere adaptación específica a cada contexto organizacional. Los principios son universales, pero la implementación debe ajustarse a las metodologías y herramientas específicas de cada equipo.