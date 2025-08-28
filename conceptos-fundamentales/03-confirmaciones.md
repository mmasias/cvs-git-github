# Confirmaciones

## ¿Por qué?

### El problema de los puntos de control significativos

Una vez comprendido que los repositorios almacenan la información en espacios diferentes, surge la pregunta: ¿cómo se crean esos "puntos de control" en el historial? Sin entender qué son las confirmaciones, es imposible crear un historial útil y navegable.

Problemas típicos por falta de comprensión:

- **"¿Cuándo debo guardar mi progreso?"**: No saber cuándo crear puntos de control efectivos
- **"No entiendo mi propio historial"**: Mensajes crípticos que no explican los cambios realizados  
- **"No puedo encontrar cuándo cambió algo específico"**: Falta de granularidad adecuada en el historial

## ¿Qué?

Una **confirmación** (commit) es una instantánea completa del estado de los archivos en un momento específico, junto con metadatos que documentan quién realizó los cambios, cuándo y por qué.

Cada confirmación registra:
- **Qué cambió**: Los archivos modificados
- **Quién lo cambió**: Autor de las modificaciones
- **Cuándo se cambió**: Fecha y hora exacta
- **Por qué se cambió**: Mensaje explicativo

## ¿Para qué?

### Beneficios de las confirmaciones bien estructuradas

|Navegación temporal|Documentación automática|Colaboración efectiva|
|-|-|-|
|Permite volver a cualquier estado anterior específico|Cada confirmación documenta el razonamiento detrás de los cambios|Los mensajes claros facilitan que otros entiendan la evolución del proyecto|
|Facilita identificar cuándo se introdujo un cambio o error específico|Crea un registro histórico de decisiones técnicas|Permite revisar contribuciones individuales con contexto completo|
|Posibilita comparar diferentes versiones para analizar la evolución|Automatiza la creación de logs de cambios para usuarios finales|Reduce tiempo de onboarding al explicar automáticamente la historia del proyecto|

## ¿Cuándo?

### Momentos apropiados para crear confirmaciones

|Confirmación necesaria|Confirmación recomendada|Evitar confirmación|
|-|-|-|
|Se completó una unidad lógica de trabajo|Se realizaron cambios experimentales que se quieren preservar|Trabajo está a medio completar sin funcionalidad estable|
|Se corrigió un error específico|Se alcanzó un punto de trabajo estable antes de pausa prolongada|Solo se cambió formato o espaciado sin funcionalidad|
|Se añadió una funcionalidad completa|Se quiere documentar un enfoque específico para referencia futura|Cambios son temporales o de prueba|
|Se actualizó documentación relacionada con cambios funcionales|Se modificaron configuraciones que afectan el comportamiento del proyecto|Archivos generados automáticamente que cambian constantemente|

## ¿Cómo?

## Anatomía de una confirmación

### Componentes principales:

**Hash único (SHA-1)**
- Identificador único de 40 caracteres
- Ejemplo: `e7ec78da64a683eff4520f001428a865115b852d`
- Se puede abreviar: `e7ec78d`

**Metadatos del autor**
```
Author: mmasias@sdf1 <manuel@masiasweb.com>
Date: Wed Aug 27 23:50:07 2025 +0200
```

**Mensaje de confirmación**
```
feat: artículo repositorios, diagramas y corrección a algunos puntos de la introducción.

Crear diagramas PlantUML para flujo de información y operaciones,
corregir estructura pedagógica y mantener coherencia conceptual.
```

**Puntero al estado anterior**
- Cada confirmación "apunta" a su confirmación padre
- Crea una cadena cronológica del historial

## Escribiendo buenos mensajes de confirmación

### Estructura recomendada:

```
Título conciso (50 caracteres máximo)

Descripción opcional más detallada explicando:
- Por qué se realizó el cambio
- Qué problema resuelve
- Cualquier contexto importante
```

### Ejemplos efectivos:

**Bien:**
```
feat: añadir diagrama de flujo de trabajo fundamental

Crear diagrama PlantUML que muestra los cinco estados básicos
del control de versiones y las transiciones entre ellos.
```

**Mal:**
```
cambios
```

**Mal:**
```
actualizar varios archivos y arreglar cosas del README
```

### Convenciones útiles

|Convención|Ejemplo correcto|Ejemplo incorrecto|
|-|-|-|
|**Verbo en infinitivo**|"Añadir sección de herramientas gráficas"|"Añadida sección de herramientas gráficas"|
|**Ser específico**|"Cambiar nombres de archivos a camelCase según convención"|"Cambiar nombres de archivos"|
|**Explicar el 'por qué'**|"Simplificar diagrama eliminando ruido para mantener claridad conceptual"|"Cambiar diagrama"|
|**Longitud del título**|"Corregir error en validación de email" (47 caracteres)|"Corregir un error que se producía en el sistema de validación de direcciones de correo electrónico"|
|**Usar prefijos descriptivos**|"feat: añadir diagrama de flujo", "fix: corregir ortografía"|"cambios", "actualizar"|

## El historial como cadena

Las confirmaciones forman una cadena cronológica donde cada confirmación apunta a su predecesora, creando un historial navegable:

<div align=center>

|![](/images/modelosUML/cadenaConfirmaciones.svg)
|:-:
|[Código fuente](/modelosUML/cadenaConfirmaciones.puml)

</div>

Este diagrama muestra la cadena real de confirmaciones de este proyecto, donde cada objeto representa una confirmación con sus metadatos completos y las relaciones de parentesco que forman el historial.

### Navegando en el historial

Puedes moverte a cualquier punto:
```bash
git checkout a3b2c1d  # Ir a confirmación específica
git checkout HEAD~3   # Ir 3 confirmaciones atrás
```

## Tipos de confirmaciones

|Tipo|Características|Propósito|Ejemplo|
|-|-|-|-|
|**Normal**|Un padre, cambios incrementales|Desarrollo diario regular|"feat: añadir validación de formularios"|
|**Fusión (merge)**|Múltiples padres|Combinar ramas de desarrollo|"Merge branch 'feature-login' into main"|
|**Inicial**|Sin padre|Primera confirmación del repositorio|"Initial commit"|
|**Revert**|Deshace cambios específicos|Anular confirmación problemática|"Revert 'feat: añadir validación compleja'"|

## Buenas prácticas

|Práctica|Hacer|Evitar|Beneficio|
|-|-|-|-|
|**Frecuencia**|Confirmaciones pequeñas y cohesivas|Confirmaciones grandes con múltiples cambios|Historial más navegable y rollbacks precisos|
|**Atomicidad**|Una idea por confirmación|Usar "y" en el mensaje (indica múltiples ideas)|Facilita identificar y revertir cambios específicos|
|**Revisión previa**|`git status` y `git diff` antes de confirmar|Confirmar sin revisar cambios|Previene errores y mejora calidad de mensajes|
|**Mensajes descriptivos**|Explicar qué y por qué|Mensajes genéricos como "fix", "changes"|Facilita mantenimiento y colaboración|
|**Historial limpio**|Confirmaciones que compilan y funcionan|Confirmaciones con código roto|Permite bisección y debugging efectivos|

## Ejercicio mental

Imagina tu historial de confirmaciones como un diario:

- Cada entrada (confirmación) registra qué hiciste ese día
- Puedes volver atrás y leer cualquier entrada anterior
- Las entradas están conectadas cronológicamente
- Cada entrada explica no solo qué hiciste, sino por qué lo hiciste

## Siguiente paso

Con estos conceptos fundamentales claros, el siguiente paso es aprender los **comandos básicos** para poner en práctica estos conocimientos.