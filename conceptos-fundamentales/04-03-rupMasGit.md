# Integración RUP + Git: esquema de gobernanza

## ¿Por qué?

Los equipos que conocen RUP como metodología y Git como herramienta enfrentan un problema de integración práctica que genera ineficiencias operativas significativas. Cuando se aplican estas aproximaciones de forma separada, surgen conflictos de autoridad y duplicación de esfuerzos que afectan la productividad del proyecto.

Sin una estructura clara de gobernanza, se presentan situaciones problemáticas recurrentes: el gestor de proyecto define hitos según RUP mientras los desarrolladores gestionan versiones según Git, creando desalineación temporal. Los criterios de calidad se evalúan desde la perspectiva de fases RUP sin considerar el estado real del repositorio, generando decisiones basadas en información incompleta. Las responsabilidades se solapan entre roles RUP y permisos Git, causando confusión operativa sobre quién puede autorizar qué acciones específicas.

## ¿Qué?

Un esquema de gobernanza integrado es un framework que establece relaciones jerárquicas claras entre la metodología RUP y la herramienta Git, definiendo responsabilidades complementarias donde cada sistema gobierna su dominio específico sin conflicto con el otro.

Este esquema determina que RUP funciona como la capa de planificación y control de gestión, mientras Git opera como la capa de ejecución técnica y trazabilidad. Se establecen puntos de sincronización donde ambos sistemas se coordinan, y se definen mecanismos de resolución para situaciones donde sus criterios aparentemente divergen.

## ¿Para qué?

La integración gobernada resuelve directamente cada problema de coordinación identificado mediante la asignación clara de dominios de autoridad.

**Frente a desalineación temporal**: Se establece que RUP define los marcos temporales estratégicos (fases, iteraciones, hitos) mientras Git ejecuta la secuencia táctica de integración, garantizando que las entregas técnicas respeten los compromisos de gestión sin sacrificar calidad técnica.

**Frente a criterios de calidad conflictivos**: RUP mantiene la autoridad sobre criterios de completitud de fase y cumplimiento de objetivos de negocio, mientras Git conserva control sobre estabilidad técnica e integridad de código, estableciendo que ambos criterios deben cumplirse para avanzar.

**Frente a solapamiento de responsabilidades**: Se mapean roles RUP a responsabilidades específicas en Git, eliminando ambigüedad sobre quién autoriza operaciones críticas como merges a main, creación de versiones o gestión de hotfixes.

El esquema facilita coordinación natural entre equipos distribuidos, reduce tiempo de resolución de conflictos operativos y establece trazabilidad completa desde decisiones de negocio hasta implementación técnica.

## ¿Cómo?

### Principio rector fundamental

**RUP gobierna la estrategia, Git gobierna la táctica**

RUP responde las preguntas de gestión: qué se entrega, cuándo se entrega, qué criterios debe cumplir. Git responde las preguntas técnicas: cómo se integra, quién contribuyó específicamente, cómo se rastrea la evolución.

### Mapeo de autoridades por dominio

|Dominio|Autoridad RUP|Autoridad Git|Mecanismo de coordinación|
|-|-|-|-|
|**Temporal**|Define fases, iteraciones y plazos|Ejecuta secuencia de integración respetando plazos|Hitos RUP = Tags Git|
|**Calidad**|Establece criterios de completitud funcional|Garantiza estabilidad técnica y ausencia de regresiones|Ambos criterios deben cumplirse para release|
|**Responsabilidad**|Define roles y responsabilidades de gestión|Implementa permisos técnicos y flujos de trabajo|Roles RUP mapean a responsabilidades Git específicas|
|**Trazabilidad**|Requiere auditoría de decisiones y cumplimiento|Proporciona historial técnico granular automáticamente|Commits referencian artefactos RUP, artefactos RUP referencian commits|

### Estructura operativa integrada

**Fases RUP como estrategia Git:**

- **Inicio**: Repositorio central con ramas experimentales para exploración de viabilidad técnica
- **Elaboración**: Ramas por componente arquitectural permitiendo desarrollo paralelo de fundamentos
- **Construcción**: Flujo feature-branch con integración continua alineada a iteraciones RUP
- **Transición**: Tags de release coordinados con criterios de finalización de fase

**Roles RUP como responsabilidades Git:**

- **Gestor de proyecto**: Autoriza creación de tags de hito y toma decisiones de scope para releases
- **Arquitecto**: Controla merges a ramas principales (main/develop) y aprueba cambios estructurales
- **Líder de equipo**: Gestiona ramas de equipo y coordina integración de features completadas
- **Desarrollador**: Responsable de commits de calidad en ramas feature asignadas
- **Tester**: Bloquea merges que no cumplan criterios de validación establecidos

### Flujo de decisiones operativas

**Para cambios de desarrollo:**
1. RUP valida: ¿El cambio corresponde a disciplinas activas en la iteración actual?
2. Git ejecuta: Branch creation, development, commit, push, pull request
3. RUP evalúa: ¿El resultado cumple criterios de aceptación de la fase?
4. Git integra: Merge a rama correspondiente si ambas validaciones son positivas

**Para releases:**
1. RUP evalúa: ¿Se alcanzaron objetivos y criterios de la fase correspondiente?
2. Git verifica: ¿El código en rama principal es estable y desplegable?
3. RUP autoriza: Decisión go/no-go basada en criterios de negocio y técnicos
4. Git ejecuta: Creación de tag, branching para mantenimiento si corresponde

### Resolución de conflictos

**Cuando RUP y Git presentan criterios aparentemente contradictorios:**

- **Conflicto temporal**: RUP tiene precedencia sobre cuándo debe completarse una entrega, Git debe adaptar flujo técnico para cumplir compromiso sin sacrificar estabilidad mínima
- **Conflicto de calidad técnica**: Git mantiene veto sobre integraciones que comprometan estabilidad, RUP debe ajustar expectativas temporales hasta resolución técnica
- **Conflicto de scope**: Gestor de proyecto (RUP) arbitra qué funcionalidades se incluyen en release específico

**Escalación:**
- Conflictos técnicos: Líder de equipo → Arquitecto → Director técnico
- Conflictos de alcance/tiempo: Gestor de proyecto → Interesado correspondiente
- Conflictos de proceso: Gestor de proyecto + Arquitecto → Decisión conjunta

### Implementación práctica

**Sincronización de artefactos:**
- Issues/User Stories (RUP) se referencian en commits (Git)
- Commits (Git) se documentan en informes de iteración (RUP)
- Tags Git corresponden exactamente a hitos RUP
- Branches Git reflejan estructura de trabajo definida por disciplinas RUP

**Métricas integradas:**
- Velocity RUP se calcula basándose en commits y merges Git efectivos
- Quality Gates RUP incluyen métricas de Git (test coverage, code review status)
- Reportes RUP incorporan automáticamente trazabilidad técnica de Git

## ¿Cuándo?

Este esquema de gobernanza debe implementarse desde el inicio de proyectos que requieren coordinación entre gestión profesional y desarrollo técnico. Se aplica especialmente en contextos donde se necesita trazabilidad completa, múltiples interesados con diferentes perspectivas técnicas y de negocio, o equipos distribuidos que requieren coordinación asíncrona efectiva.

## ¿Alternativas?

**Metodologías ágiles puras**: Marcos como Scrum con integración Git nativa, pero con menor énfasis en documentación y trazabilidad formal requerida en contextos corporativos complejos.

**Herramientas de gestión propietarias**: Plataformas como Jira + Confluence integradas con Git, ofreciendo facilidad de uso pero menor flexibilidad y control sobre procesos específicos.

**Aproximaciones ad-hoc**: Coordinación informal entre RUP y Git según necesidades del momento, proporcionando máxima flexibilidad pero creando riesgo de inconsistencias y conflictos no resueltos.

## Siguiente paso

Una vez establecido el esquema de gobernanza, se recomienda desarrollar plantillas específicas de integración para los artefactos más comunes, definir métricas combinadas que reflejen tanto progreso de gestión como calidad técnica, y establecer procesos de revisión periódica que permitan ajustar la coordinación según lecciones aprendidas del equipo específico.

Los siguientes artículos desarrollarán la implementación técnica específica comenzando por [Comandos básicos con metodología](../comandos-basicos/configuracion.md).

> **💡 Nota técnica**: Esta integración es especialmente efectiva en organizaciones que ya tienen experiencia con RUP y necesitan incorporar Git de manera estructurada, manteniendo la disciplina metodológica existente.