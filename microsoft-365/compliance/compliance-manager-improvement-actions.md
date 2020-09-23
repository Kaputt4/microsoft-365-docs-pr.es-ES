---
title: Asignar y completar acciones de mejora en el administrador de cumplimiento de Microsoft
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
description: Obtenga información sobre cómo realizar implementaciones y pruebas en los controles del administrador de cumplimiento de Microsoft. Asignar trabajo, almacenar documentación y exportar informes.
ms.openlocfilehash: 99b08ca1336c3f347764230896af47fe1486d4b2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204534"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Asignar y completar acciones de mejora en el administrador de cumplimiento

**En este artículo:** En este artículo se explica cómo **administrar el flujo de trabajo de cumplimiento** con acciones de mejora. Obtenga información sobre cómo **asignar acciones de mejora** para implementar y probar, **administrar actualizaciones**y exportar **informes**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Administrar flujos de trabajo de cumplimiento con acciones de mejora

Las acciones de mejora centralizan las actividades de cumplimiento. Cada acción de mejora proporciona una guía de implementación detallada para ayudarle a alinearse con las normas y estándares de protección de datos. Se pueden asignar acciones a los usuarios de su organización para realizar tareas de implementación y pruebas. También puede almacenar la documentación, las notas y las actualizaciones de estado de registro dentro de la acción.

Todas las acciones de mejora se muestran en la página acciones de mejora. Obtenga más información sobre cómo [ver las acciones de mejora](compliance-manager-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Página de detalles de acciones de mejora

Cada acción de mejora tiene una página de detalles que muestra su estado actual, los estándares relacionados y los requisitos normativos y las instrucciones de implementación recomendadas. [Las acciones técnicas](compliance-score-calculation.md#technical-and-non-technical-actions) incluyen un vínculo **lanzar ahora** que le lleva a la solución adecuada para su implementación. Puede adjuntar la documentación de implementación y pruebas directamente en la página de detalles de una acción de mejora.

Para ver la página de detalles de una acción de mejora:

1. Vaya a la página acciones de mejora.
2. Seleccione la fila de la acción de mejora que desea, que abre su página de detalles.

Puede ver fácilmente la acción de mejora siguiente o anterior en la lista seleccionando la flecha arriba o abajo en la esquina superior derecha de la pantalla. Si ha filtrado la lista en la página acciones de mejora, al subir o bajar se le llevará al siguiente elemento de esa lista filtrada.

## <a name="assign-improvement-actions"></a>Asignar acciones de mejora

Para comenzar el trabajo de implementación en una acción de mejora, puede realizar el trabajo usted mismo o asignarlo a otro usuario. La persona asignada podría ser:

- Un propietario de la directiva de la empresa
- Un implementador de TI
- Otro empleado con responsabilidad de realizar la tarea

Una vez que haya identificado al destinatario de la asignación, asegúrese de que tienen un [rol de administrador de cumplimiento](compliance-manager-setup.md#set-user-permissions-and-assign-roles) suficiente para realizar el trabajo. A continuación, siga los pasos siguientes para asignar la acción de mejora:

1. En la página de detalles de acciones de mejora, seleccione **Editar estado** cerca de la sección superior izquierda de la pantalla.

2. En el panel de control flotante Editar estado, seleccione el cuadro **asignado a** para mostrar una lista de usuarios **sugeridos** para las personas. Puede seleccionar el usuario de la lista o escribir la dirección de correo electrónico de la persona a la que desea asignarlo.

3. Seleccione **Guardar y cerrar**. El usuario asignado recibirá un correo electrónico en el que se explica que se ha asignado la acción de mejora, con un vínculo directo a la acción de mejora.

A continuación, el usuario asignado puede realizar las acciones recomendadas.

## <a name="perform-work-and-store-documentation"></a>Realizar la documentación del trabajo y la tienda

Puede cargar archivos y notas relacionados con la implementación y las pruebas de trabajo directamente en la sección de **notas y documentación** . Este entorno es un repositorio centralizado y seguro que le ayuda a demostrar la satisfacción de los controles para cumplir con las normas y regulaciones de cumplimiento. Cualquier usuario con acceso de solo lectura puede leer el contenido de esta sección. Solo los usuarios con derechos de edición pueden cargar y descargar archivos y escribir o editar notas.

La sección de **notas y documentación** contiene los campos para los documentos cargados, las notas de implementación, las notas de prueba y notas adicionales.

#### <a name="uploaded-documents"></a>Documentos cargados

- Seleccione **administrar documentos** para cargar los archivos relevantes.
- Cuando se abra el panel desplegable administrar documentos, seleccione **Agregar documento**y, a continuación, seleccione el archivo en el sistema. Tipos de archivos aceptados:
    - Documentos (. doc,. xls,. ppt,. txt,. pdf)
    - Imágenes (. jpg,. png)
    - Vídeo (. mkv)
    - Archivos comprimidos (. zip,. rar)
- Una vez que el archivo se resuelva en el panel, seleccione **cerrar**, que guarda automáticamente los datos adjuntos del archivo. Verá el archivo que aparece debajo de los **documentos cargados**.
- Para descargar o eliminar el documento, seleccione **administrar documentos** de debajo de la lista de documentos. En el panel flotante, seleccione la fila del documento para resaltarla y, a continuación, seleccione **Descargar** o **eliminar**.

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Notas de implementación, notas de prueba y notas adicionales

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
    - **Fuera de ámbito** – la acción no es relevante para su organización y no contribuye a su calificación
- **Fecha de implementación**: disponible para seleccionar Cuándo el estado de implementación es "implementado" o "implementación alternativa"
- **Estado**de la prueba: disponible para seleccionar Cuándo el estado de implementación es "implementado" o "implementación alternativa":
    - **No evaluado: no** se ha probado la acción
    - La implementación que se ha **aprobado** ha sido comprobada por un asesor
    - Error en la prueba de **riesgo bajo** , riesgo bajo
    - **Riesgo medio fallido** : no se pudieron probar las pruebas, riesgo medio
    - **Se ha producido un riesgo alto** : error en las pruebas, alto riesgo
    - **Fuera de ámbito** : la acción está fuera del ámbito de la evaluación y no contribuye a su calificación
- **Fecha de prueba**: alternar a través del calendario emergente para seleccionar la fecha

Las acciones comunes se sincronizan entre grupos. Cuando dos evaluaciones distintas en el mismo grupo comparten acciones de mejora que usted administra, las actualizaciones que realice en los detalles de implementación o el estado de una acción se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. Esta sincronización le permite implementar una acción de mejora y cumplir varios requisitos en varias regulaciones.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Asignar una acción de mejora a los evaluadores para su finalización

Después de completar el trabajo, realizar las pruebas y cargar la evidencia, el siguiente paso consiste en asignar la acción de mejora a un asesor de validación. El asesor valida el trabajo, examina la documentación y selecciona el estado de prueba adecuado.

**Si el estado de la prueba se establece en "remitido"**: la acción se ha completado y los puntos obtenidos muestran los puntos máximos logrados. A continuación, los puntos se cuentan hacia la puntuación de cumplimiento general.

**Si el estado de la prueba se establece en "error"**: la acción no cumple con los requisitos y el asesor puede volver a asignarla al usuario adecuado para un trabajo adicional.

## <a name="accepting-updates-to-improvement-actions"></a>Aceptar actualizaciones para las acciones de mejora

Cuando hay una actualización disponible para una acción de mejora, verá una notificación junto a su nombre. Puede aceptar la actualización o aplazarla más tarde.

#### <a name="what-causes-an-update"></a>Qué causa una actualización

Una actualización se produce cuando hay cambios relacionados con la puntuación, la automatización o el ámbito. Los cambios pueden implicar nuevas instrucciones para las acciones de mejora basadas en los cambios normativos, o podrían deberse a cambios en el producto. Solo las acciones de mejora que administran las organizaciones reciben notificaciones de actualización.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dónde verá las notificaciones de actualización de evaluación

Cuando se actualiza una acción de mejora, verá una etiqueta de **actualización pendiente** junto a su nombre en la página acciones de mejora y en la página de detalles de sus evaluaciones relacionadas.

Vaya a la página de detalles de la acción de mejora y seleccione el botón **revisar actualización** en el banner superior para revisar los detalles de los cambios y aceptar o aplazar la actualización.

#### <a name="review-update-to-accept-or-defer"></a>Revisión de la actualización para aceptar o aplazar

Después de seleccionar **revisar actualización** en la página de detalles de la acción de mejora, aparece un panel flotante en la parte derecha de la pantalla. El panel de control flotante proporciona detalles clave sobre la actualización, como las evaluaciones afectadas y los cambios de puntuación y ámbito.

Seleccione **Aceptar actualización** para aceptar todos los cambios en la acción de mejora. **Los cambios aceptados son permanentes**.

> [!NOTE]
> Cuando acepta una actualización de una acción, también está aceptando actualizaciones para cualquier otra versión o instancias de esta acción. Las actualizaciones se propagarán a todo el espacio empresarial para las acciones técnicas y propagarán todo el grupo de acciones no técnicas.

Si selecciona **Cancelar**, la actualización no se aplicará a la acción de mejora. Sin embargo, seguirá viendo la notificación de **actualización pendiente** hasta que acepte la actualización.

**Por qué se recomienda aceptar actualizaciones**

La aceptación de actualizaciones le ayudará a disponer de las instrucciones más actualizadas sobre el uso de soluciones y la realización de las acciones de mejora adecuadas para ayudarle a cumplir los requisitos de la certificación disponibles.

**Por qué es posible que quiera aplazar una actualización**

Si está realizando una evaluación que incluye la acción de mejora, es posible que desee asegurarse de que ha terminado de trabajar en ella antes de aceptar la actualización. Puede aplazar la actualización para una hora posterior seleccionando **Cancelar** en el panel revisar control flotante de actualización.

## <a name="export-a-report"></a>Exportar un informe

Seleccione **exportar** en la esquina superior izquierda de la pantalla para descargar una hoja de cálculo de Excel que contenga todas las acciones de mejora y las categorías de filtro que se muestran en la página acciones de mejora.