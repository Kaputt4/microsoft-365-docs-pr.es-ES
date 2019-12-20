---
title: Trabajar con la puntuación de cumplimiento de Microsoft
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar las herramientas de flujo de trabajo en la puntuación de cumplimiento de Microsoft para administrar el cumplimiento de la organización.
ms.openlocfilehash: 9c3871db720666319eb8a0523ff8150efd753f91
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802143"
---
# <a name="working-with-microsoft-compliance-score-preview"></a>Trabajar con la puntuación de cumplimiento de Microsoft (versión preliminar)

## <a name="managing-your-workflow-with-improvement-actions"></a>Administración del flujo de trabajo con acciones de mejora

El uso de acciones de mejora en la puntuación de cumplimiento centraliza los flujos de trabajo de cumplimiento. Las acciones de mejora sugieren acciones recomendadas para alinearse con los estándares y las normas de protección de datos y proporcionar una guía de implementación detallada. Puede asignarlos a los usuarios para que realicen las tareas de implementación y pruebas necesarias. También puede almacenar documentación y notas, y registrar actualizaciones de estado directamente en la acción de mejora en sí.

## <a name="view-your-improvement-actions"></a>Ver las acciones de mejora

El panel de calificaciones de cumplimiento muestra las **acciones de mejora de clave**, es decir, las que tienen los puntos más disponibles que abordan los problemas más importantes.

Para ver todas las acciones de mejora, seleccione la pestaña **acciones de mejora** del panel o seleccione **ver todas las acciones de mejora** debajo de la lista de acciones de mejora de clave en el panel. Esto le lleva a la página **acciones de mejora** , donde puede ver todas las acciones de mejora de su organización.

Si tiene una larga lista de acciones, puede resultar útil filtrar la vista. Para ello, seleccione **filtro** en la esquina superior derecha de la lista acciones. Cuando aparezca el panel desplegable **filtros** , seleccione los criterios que desee en función de las regulaciones y los estándares, la solución y el grupo. También puede personalizar la vista seleccionando **Grupo** en la esquina superior derecha y, en el menú desplegable, seleccionar para ver por grupo, solución, categoría, tipo de acción o estado.

La vista predeterminada de esta página no muestra acciones de mejora con el estado de prueba **aprobado**. Para ver las acciones que han superado la prueba, active la casilla **aprobado** en el panel flotante de **filtros** . Solo acciones con un estado de prueba de recuento **aprobado** hacia su calificación.

La página acciones de mejora muestra los siguientes puntos de datos para cada acción de mejora:

- **Impacto del resultado**: los puntos por los que aumentará la puntuación general al completar la acción.
- **Regulaciones**: el Reglamento o el estándar que pertenece a la acción
- **Grupo**: el grupo al que asignó la acción
- **Soluciones**: la solución en la que puede realizar la acción.
- **Evaluaciones**: la evaluación (que organiza los controles para cumplir un determinado objetivo de cumplimiento) en el que reside la acción.
- **Categorías**: categoría de protección de datos relacionada (es decir, proteger la información, administrar dispositivos, etc.)
- **Estado**de la prueba:
    - **Ninguna** : no hay ninguna actualización de estado registrada
    - **No evaluado** : no se han iniciado las pruebas
    - **No en el ámbito** -se excluye del cálculo de puntuación de cumplimiento y no aumenta la puntuación
    - Las pruebas **probadas parcialmente** no se han completado todavía
    - Error en la prueba de **riesgo alto** de la implementación, y el riesgo de no cumplir con el estándar aplicable es alto
    - **Aprobada** : la implementación se ha probado correctamente
- Se ha **alcanzado**: muestra puntos obtenidos del máximo que puede obtenerse

### <a name="improvement-actions-details"></a>Detalles de acciones de mejora

Cada acción de mejora tiene una página de detalles. Esta página contiene instrucciones de implementación detalladas, que explican cómo realizar las acciones recomendadas para abordar los estándares relacionados y los requisitos normativos que aparecen en el encabezado **de un vistazo** .

La página Detalles es donde puede iniciar la acción recomendada o asignar el trabajo a otro usuario, actualizar el estado y adjuntar notas y documentación.

Para ver la página de detalles de una acción de mejora:

1. Vaya a la página acciones de mejora.
2. Haga clic o pulse en cualquier lugar de la fila de la acción de mejora que desea para abrir su página de detalles.

Puede ver fácilmente la acción de mejora siguiente o anterior en la lista seleccionando la flecha arriba o abajo en la esquina superior derecha de la pantalla. Si filtró la lista en la página acciones de mejora, al mover hacia arriba o hacia abajo irá al siguiente elemento de esa lista filtrada.

## <a name="assign-improvement-actions"></a>Asignar acciones de mejora

Para comenzar el trabajo de implementación en una acción de mejora, puede realizar el trabajo usted mismo o asignarlo a otro usuario. La persona asignada podría ser:

- Un propietario de la directiva de la empresa
- Un implementador de TI
- Otro empleado con responsabilidad de realizar la tarea 

Una vez identificada la persona adecuada, asegúrese de que desempeña un [papel](compliance-score-setup.md#set-user-permissions-and-assign-roles) suficiente en la puntuación de cumplimiento (Administrador de cumplimiento, administrador de datos de cumplimiento, administrador de seguridad o administrador global) para realizar el trabajo y, a continuación, siga estos pasos: 

1. En la página de detalles de acciones de mejora, seleccione **Editar estado** cerca de la sección superior izquierda de la pantalla. 

2. En el panel de control flotante Editar estado, haga clic o pulse en el cuadro **asignado a** , que rellena una lista de usuarios **sugerida de personas** . Puede seleccionar el usuario de la lista o escribir la dirección de correo electrónico de la persona a la que desea asignar la acción.

3. Seleccione **Guardar y cerrar** para completar la asignación. El usuario asignado recibirá un correo electrónico en el que se le ha asignado la acción de mejora y, a continuación, podrá abrir la acción de mejora desde el panel.

A continuación, el usuario asignado puede llevar a cabo las acciones recomendadas que se describen en las instrucciones de implementación.

## <a name="perform-work-and-store-documentation"></a>Realizar la documentación del trabajo y la tienda

Al realizar el trabajo de implementación, puede cargar archivos y notas directamente en la acción de mejora en la sección de **notas y documentación** . Esto proporciona un repositorio centralizado y seguro para ayudarle a demostrar la satisfacción de los controles para cumplir con las normas y regulaciones de cumplimiento. Cualquier usuario con acceso de solo lectura puede leer el contenido de esta sección. La capacidad para cargar, descargar o eliminar campos, o para escribir o editar notas, está restringida a roles con derechos de edición.

Entre los campos de la sección **notas y documentación** se incluyen:

**Documentos cargados**

- Seleccione **administrar documentos** para cargar los archivos relevantes.
- Cuando se abra el panel desplegable administrar documentos, seleccione **Agregar documento**y, a continuación, seleccione el archivo en el sistema. Tipos de archivos aceptados: 
  - Documentos (. doc,. xls,. ppt,. txt,. pdf)
  - Imágenes (. jpg,. png)
  - Vídeo (. mkv)
  - Archivos comprimidos (. zip,. rar)
- Una vez que el archivo se resuelva en el panel, seleccione **Cerrar,** que guarda automáticamente los datos adjuntos del archivo. Verá el archivo que aparece debajo de los **documentos cargados.** 
- Para descargar o eliminar el documento, seleccione **administrar documentos** de debajo de la lista de documentos. En el panel desplegable, haga clic o pulse en la fila del documento para resaltarla y, a continuación, seleccione **Descargar** o **eliminar.**

**Implementación, prueba y notas adicionales**

- Para agregar notas en cualquiera de estos tres campos, seleccione **Editar notas de implementación** debajo de cualquiera de thse campos.
- Cuando se abra el panel flotante, escriba notas en el campo de texto y, a continuación, seleccione **Guardar y cerrar**.
- Para editar notas, seleccione **Editar notas de implementación**, realice las modificaciones y, a continuación, seleccione **Guardar y cerrar**.

No hay ningún límite de caracteres en los campos de Notes. Se recomienda mantener notas breves para que pueda verlas y editarlas fácilmente desde la página de detalles de acciones de mejora.

## <a name="change-improvement-action-status"></a>Estado de la acción de mejora de cambios

Puede registrar el estado y la fecha de la implementación, y la fecha y el estado de la prueba, para cada acción de mejora. A continuación se muestran los campos disponibles y las opciones de estado:

- **Estado**de la implementación: Seleccione una de estas opciones de estado:
    - **No implementado** : acción no implementada todavía
    - **Implementado** : acción implementada
    - **Implementación alternativa** : Seleccione esta opción si usó otras herramientas de terceros o tomó otras acciones no incluidas en las recomendaciones de Microsoft.
    - **Planificada** : se planea la acción para la implementación
    - **No en el ámbito** : una opción para acciones no relevantes para su organización; al seleccionar este estado, se excluye la acción de la puntuación; Si se anula la selección, se incluirá la acción en puntuación
- **Fecha de implementación**: campo disponible cuando el estado de la implementación se establece en **implementaciones** o **implementación alternativa**; alternar entre el calendario emergente para seleccionar la fecha
- **Estado**de la prueba: Seleccione una de estas opciones:
    - **No evaluado** : no se han iniciado las pruebas
    - **Aprobada**: la implementación se ha probado correctamente
    - Error en la prueba de **riesgo bajo** , riesgo bajo
    - **Riesgo medio fallido** : no se pudieron probar las pruebas, riesgo medio
    - Error en la prueba de **riesgo alto** , riesgo alto
- **Fecha de prueba**: alternar a través del calendario emergente para seleccionar la fecha

> [!NOTE]
> Los campos de implementación y estado de pruebas los puede editar cualquier usuario con permisos de edición, no solo el usuario **asignado a** .

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Asignar una acción de mejora a los evaluadores para su finalización

Después de completar el trabajo y cargar la evidencia, el siguiente paso consiste en establecer el estado y la fecha de la implementación, y asignar la acción de mejora a un asesor de validación.

Entre los tipos de evaluadores se incluyen:

- Evaluadores internos que realizan la validación de controles dentro de la organización
- Evaluadores externos que examinan, comprueban y certifican el cumplimiento, como las organizaciones independientes de terceros que auditan los servicios en la nube de Microsoft

El asesor valida el trabajo, examina la documentación y selecciona el estado de prueba adecuado.

**Si el estado de la prueba es "superado"**: la acción se ha completado y los **puntos logrados** muestran el número total de puntos posibles logrados y contados hacia la puntuación de cumplimiento general.

**Si el estado de la prueba es cualquier grado de "error"**: la acción no cumple los requisitos y el asesor puede volver a asignarla al usuario adecuado para un trabajo adicional.

## <a name="solutions-page"></a>Página de soluciones

La **Página soluciones** es otro punto de partida para trabajar con acciones de mejora y aumentar el resultado. 

Para ir a la página soluciones, seleccione la pestaña **soluciones** del panel o seleccione **ver todas las soluciones** debajo de **soluciones que afectan a su puntuación** en la sección superior derecha del panel.

La página soluciones muestra el recurso compartido de puntos potenciales y ganados organizados por solución. Ver los puntos y acciones de mejora restantes en esta vista ayuda a comprender qué soluciones necesitan atención más inmediata.

### <a name="filtering-your-solutions-view"></a>Filtrar la vista de soluciones

Para filtrar la vista de las soluciones: 

1. Seleccione **filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el panel de **filtros** de control flotante, realice una comprobación junto a los criterios que desee (normas y regulaciones, solución, tipo de acción, grupo de administradores de cumplimiento, categoría).
3. Seleccione el botón **aplicar** . El panel de filtros se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regla seleccionando el tipo de agrupación en el menú desplegable de **grupos** situado encima de la lista de evaluaciones.

### <a name="taking-actions-from-the-solutions-page"></a>Emprender acciones desde la página soluciones

La página soluciones muestra las soluciones de su organización que están conectadas a acciones de mejora. En la tabla se muestra la contribución de cada solución a la puntuación general, los puntos de mejora de la puntuación alcanzados y posibles dentro de esa solución y el número restante de acciones de mejora agrupadas en esa solución que pueden aumentar la puntuación. 

Hay dos formas de realizar acciones en esta pantalla:

1. En la fila de la solución deseada, en la columna **acciones restantes** , haga clic o pulse en el número de hipervínculo. Esto le llevará a una vista filtrada de la pantalla acciones de mejora que muestra acciones de mejora no probadas para dicha solución.

2. En la fila de la solución deseada, en la columna **Abrir solución** , seleccione **abrir**. Esto le llevará a la solución o ubicación en los centros de seguridad y cumplimiento de Microsoft 365 y Office 365 donde puede llevar a cabo la acción recomendada.

## <a name="assessments-page"></a>Página evaluaciones

La página evaluaciones muestra las evaluaciones que seleccione para realizar un seguimiento de su organización. El denominador de puntuación de cumplimiento se determina por todas las evaluaciones con seguimiento. Cuanto más evaluaciones agregue, más acciones de mejora verá en la página acciones de mejora y mayor será el denominador de puntuación.

Para ir a la página evaluaciones, seleccione la pestaña **evaluaciones** del panel.

En esta página, puede ver rápidamente información importante sobre cada evaluación:

- **Status**: el estado hacia la finalización de todas las acciones de mejora en la evaluación se mostrará como:
    - **No conforme**: las acciones de mejora en la evaluación no se han implementado y se han probado correctamente; el trabajo todavía no ha empezado
    - **En curso**: el trabajo se está llevando a cabo para implementar o probar las acciones de mejora; Esto puede significar, por ejemplo, que una acción de mejora en la evaluación ha sido asignada para el trabajo, está en proceso de implementación y prueba.
- **Progreso**de la evaluación: porcentaje de trabajo realizado hacia la finalización final de la evaluación, medido por el número de controles que se han probado correctamente.
- **Acciones administradas por el cliente**: el número de acciones completadas para satisfacer la implementación de los controles administrados por el cliente.
- **Acciones administradas por Microsoft**: el número de acciones completadas para satisfacer la implementación de controles administrados por Microsoft
- **Grupo de evaluación**: nombre del grupo que ha creado, en el que reside la evaluación.
- **Servicios relacionados**: servicio Microsoft 365 asociado
- **Regulaciones relacionadas**: el estándar normativo, la política o la legislación que la evaluación busca cumplir.

### <a name="default-assessments"></a>Evaluaciones predeterminadas

De forma predeterminada, verá la evaluación de línea base de protección de datos 365 de Microsoft en la página evaluaciones. La puntuación de cumplimiento también proporciona varias evaluaciones no actualizadas ([vea la lista completa](compliance-score.md#templates)). Si desea agregar más evaluaciones para cubrir otras normativas y estándares, puede hacerlo en el administrador de cumplimiento.

### <a name="managing-assessments"></a>Administración de evaluaciones

Durante la vista previa pública, la funcionalidad para ver, crear, exportar y archivar evaluaciones se mantiene en la herramienta Administrador de cumplimiento. 

Para administrar sus evaluaciones, seleccione **administrar evaluaciones en el administrador de cumplimiento** en la parte superior de la lista de evaluaciones.

El otro vínculo en la parte superior de la lista de evaluaciones, **acciones de Microsoft en el administrador de cumplimiento**, le lleva a la página del administrador de cumplimiento que muestra los controles de Microsoft que contribuyen a la puntuación de cumplimiento.

### <a name="filtering-your-assessments-view"></a>Filtrar la vista de evaluaciones

Para filtrar la vista de las evaluaciones:

1. Seleccione **filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el panel de **filtros** de flotante, active la casilla de verificación que se encuentra junto al criterio que desee (estándares y regulaciones, grupo de administradores de cumplimiento).
3. Seleccione el botón **aplicar** . El panel de filtros se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regla seleccionando el tipo de agrupación en el menú desplegable de **grupos** situado encima de la lista de evaluaciones.

### <a name="managing-improvement-actions-within-an-assessment"></a>Administración de acciones de mejora dentro de una evaluación

En la lista de evaluaciones, en la columna **acciones administradas por el cliente** , seleccione el texto vinculado en la fila de la evaluación correspondiente. Esto le llevará una vista filtrada de la página acciones de mejora que muestra las acciones de dicha evaluación.

## <a name="reporting"></a>Reporting

Puede exportar un informe de todas las acciones de mejora en la puntuación de cumplimiento. En la página **acciones de mejora** , seleccione **exportar** en la esquina superior izquierda de la pantalla, encima de la lista de acciones. Esto generará una hoja de cálculo de Excel con todas las acciones de mejora y las categorías de filtro que se muestran en la página **acciones de mejora** , que puede ver y guardar en el equipo local.

También puede exportar un informe desde el administrador de cumplimiento. En el administrador de cumplimiento, vaya a la pestaña **información de controles** y seleccione **exportar** en la sección superior derecha de la pantalla. Esto genera una hoja de cálculo de Excel que puede ver y guardar.
