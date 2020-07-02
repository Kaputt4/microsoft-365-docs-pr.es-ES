---
title: Trabajar con acciones de mejora en la puntuación de cumplimiento de Microsoft (versión preliminar)
f1.keywords:
- NOCSH
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
description: Obtenga información sobre cómo administrar las actividades de cumplimiento en la puntuación de cumplimiento de Microsoft trabajando con acciones de mejora.
ms.openlocfilehash: d10e04f144595e1976f4b20e894ccbc299aade7b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016595"
---
# <a name="work-with-improvement-actions-in-compliance-score-preview"></a>Trabajar con acciones de mejora en la puntuación de cumplimiento (versión preliminar)

**En este artículo:** En este artículo se explica cómo **administrar el flujo de trabajo de cumplimiento** con acciones de mejora. Obtenga información sobre cómo **asignar acciones de mejora** para la implementación y las pruebas, asignarlas a los evaluadores para la finalización y exportar **informes**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Administrar flujos de trabajo de cumplimiento con acciones de mejora

Las acciones de mejora centralizan las actividades de cumplimiento. Cada acción de mejora proporciona una guía de implementación detallada para ayudarle a alinearse con las normas y estándares de protección de datos. Se pueden asignar acciones a los usuarios de su organización para realizar tareas de implementación y pruebas. También puede almacenar la documentación, las notas y las actualizaciones de estado de registro dentro de la acción de mejora.

Todas las mejoras se muestran en la página acciones de mejora. Obtenga más información sobre [Cómo filtrar la vista de las acciones de mejora e interpretar los Estados de estado](compliance-score-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Página de detalles de acciones de mejora

Cada acción de mejora tiene una página de detalles que muestra su estado actual y los estándares y requisitos normativos relacionados. La guía de implementación detallada incluye un vínculo de **lanzamiento ahora** que le lleva a la solución adecuada para su implementación. Puede adjuntar la documentación de implementación y pruebas directamente en la página de detalles de una acción de mejora.

Para ver la página de detalles de una acción de mejora:

1. Vaya a la página acciones de mejora.
2. Seleccione la fila de la acción de mejora que desea, que abre su página de detalles.

Puede ver fácilmente la acción de mejora siguiente o anterior en la lista seleccionando la flecha arriba o abajo en la esquina superior derecha de la pantalla. Si ha filtrado la lista en la página acciones de mejora, al subir o bajar se le llevará al siguiente elemento de esa lista filtrada.

## <a name="assign-improvement-actions"></a>Asignar acciones de mejora

Para comenzar el trabajo de implementación en una acción de mejora, puede realizar el trabajo usted mismo o asignarlo a otro usuario. La persona asignada podría ser:

- Un propietario de la directiva de la empresa
- Un implementador de TI
- Otro empleado con responsabilidad de realizar la tarea

Una vez que haya identificado al destinatario de la asignación, asegúrese de que desempeña un [papel suficiente en la puntuación de cumplimiento](compliance-score-setup.md#set-user-permissions-and-assign-roles) (Administrador de cumplimiento, administrador de datos de cumplimiento, administrador de seguridad o administrador global) para realizar el trabajo y, a continuación, siga estos pasos:

1. En la página de detalles de acciones de mejora, seleccione **Editar estado** cerca de la sección superior izquierda de la pantalla.

2. En el panel de control flotante Editar estado, seleccione el cuadro **asignado a** para mostrar una lista de usuarios **sugeridos** para las personas. Puede seleccionar el usuario de la lista o escribir la dirección de correo electrónico de la persona a la que desea asignarlo.

3. Seleccione **Guardar y cerrar**. El usuario asignado recibirá un correo electrónico en el que se le ha asignado la acción de mejora y, a continuación, podrá abrir la acción de mejora desde el panel.

A continuación, el usuario asignado puede realizar las acciones recomendadas.

## <a name="perform-work-and-store-documentation"></a>Realizar la documentación del trabajo y la tienda

Puede cargar archivos y notas relacionados con la implementación y las pruebas de trabajo directamente en la sección de **notas y documentación** . Este entorno es un repositorio centralizado y seguro que le ayuda a demostrar la satisfacción de los controles para cumplir con las normas y regulaciones de cumplimiento. Cualquier usuario con acceso de solo lectura puede leer el contenido de esta sección. Solo los usuarios con derechos de edición pueden cargar y descargar archivos y escribir o editar notas.

Entre los campos de la sección **notas y documentación** se incluyen:

### <a name="uploaded-documents"></a>Documentos cargados

- Seleccione **administrar documentos** para cargar los archivos relevantes.
- Cuando se abra el panel desplegable administrar documentos, seleccione **Agregar documento**y, a continuación, seleccione el archivo en el sistema. Tipos de archivos aceptados:
    - Documentos (. doc,. xls,. ppt,. txt,. pdf)
    - Imágenes (. jpg,. png)
    - Vídeo (. mkv)
    - Archivos comprimidos (. zip,. rar)
- Una vez que el archivo se resuelva en el panel, seleccione **cerrar**, que guarda automáticamente los datos adjuntos del archivo. Verá el archivo que aparece debajo de los **documentos cargados**.
- Para descargar o eliminar el documento, seleccione **administrar documentos** de debajo de la lista de documentos. En el panel desplegable, haga clic o pulse en la fila del documento para resaltarla y, a continuación, seleccione **Descargar** o **eliminar**.

### <a name="implementation-notes-test-notes-and-additional-notes"></a>Notas de implementación, notas de prueba y notas adicionales

- Para agregar notas en cualquiera de estos tres campos, seleccione **Editar notas de implementación** debajo de cualquiera de estos campos.
- Cuando se abra el panel flotante, escriba notas en el campo de texto y, a continuación, seleccione **Guardar y cerrar**.
- Para editar notas, seleccione **Editar notas de implementación**, realice las modificaciones y, a continuación, seleccione **Guardar y cerrar**.

No hay ningún límite de caracteres en los campos de Notes. Se recomienda mantener notas breves para que pueda verlas y editarlas fácilmente desde la página de detalles de acciones de mejora.

## <a name="change-improvement-action-status"></a>Estado de la acción de mejora de cambios

Puede registrar el estado y la fecha de la implementación, y la fecha y el estado de la prueba, para cada acción de mejora. Los campos de **implementación** y **Estado de pruebas** pueden ser editados por cualquier usuario con permisos de edición, y no solo por la persona asignada.

Para editar el estado de una acción de mejora, seleccione **Editar estado** en la sección superior izquierda de la página de detalles. A continuación se muestran los campos disponibles y las opciones de estado:

- **Estado de la implementación**
    - **No implementado** : acción no implementada todavía
    - **Implementado** : acción implementada
    - **Implementación alternativa** : Seleccione esta opción si usó otras herramientas de terceros o tomó otras acciones no incluidas en las recomendaciones de Microsoft.
    - **Planificada** : se planea la acción para la implementación
    - **No en ámbito** – la acción no es relevante para la organización y no contribuye a su calificación
- **Fecha de implementación**: disponible para seleccionar Cuándo el estado de implementación es "implementado" o "implementación alternativa"
- **Estado**de la prueba: disponible para seleccionar Cuándo el estado de implementación es "implementado" o "implementación alternativa":
    - **No evaluado** : no se ha probado la acción
    - La implementación que se ha **aprobado**ha sido comprobada por un asesor
    - Error en la prueba de **riesgo bajo** , riesgo bajo
    - **Riesgo medio fallido** : no se pudieron probar las pruebas, riesgo medio
    - **Se ha producido un riesgo alto** : error en las pruebas, alto riesgo
    - **No en el ámbito** : la acción está fuera del ámbito de la evaluación y no contribuye a su calificación.
- **Fecha de prueba**: alternar a través del calendario emergente para seleccionar la fecha

Las acciones comunes se sincronizan entre grupos. Cuando dos evaluaciones distintas en el mismo grupo comparten acciones de mejora que usted administra, las actualizaciones que realice en los detalles de implementación o el estado de una acción se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. Esta sincronización le permite implementar una acción de mejora y cumplir varios requisitos en varias regulaciones.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Asignar una acción de mejora a los evaluadores para su finalización

Después de completar el trabajo, realizar las pruebas y cargar la evidencia, el siguiente paso consiste en asignar la acción de mejora a un asesor de validación.

Entre los tipos de evaluadores se incluyen:

- Evaluadores internos que realizan la validación de controles dentro de la organización
- Evaluadores externos que examinan, comprueban y certifican el cumplimiento, como las organizaciones independientes de terceros que auditan los servicios en la nube de Microsoft

El asesor valida el trabajo, examina la documentación y selecciona el estado de prueba adecuado.

**Si el estado de la prueba se establece en "remitido"**: la acción se ha completado y los puntos obtenidos muestran los puntos máximos logrados. A continuación, los puntos se cuentan hacia la puntuación de cumplimiento general.

**Si el estado de la prueba se establece en "error"**: la acción no cumple con los requisitos y el asesor puede volver a asignarla al usuario adecuado para trabajo adicional.

## <a name="export-a-report"></a>Exportar un informe

Seleccione **exportar** en la esquina superior izquierda de la pantalla para descargar una hoja de cálculo de Excel que contenga todas las acciones de mejora y las categorías de filtro que se muestran en la página acciones de mejora.