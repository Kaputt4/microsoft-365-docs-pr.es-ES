---
title: Trabajar con acciones de mejora en el Administrador de cumplimiento de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Aprenda a implementar y probar controles trabajando con acciones de mejora en Microsoft Compliance Manager. Asignar informes de trabajo, almacenar documentación e exportar.
ms.openlocfilehash: 33b1de7dfc116cc1403d0e3619dfbec2f0853be3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319467"
---
# <a name="working-with-improvement-actions-in-compliance-manager"></a>Trabajar con acciones de mejora en el Administrador de cumplimiento

**En este artículo:** En este artículo se explica cómo **administrar el flujo de trabajo de cumplimiento** con acciones de mejora. Obtenga información sobre cómo **asignar acciones de mejora para** la implementación y pruebas, **administrar actualizaciones** y exportar **informes**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Administrar flujos de trabajo de cumplimiento con acciones de mejora

Las acciones de mejora centralizan las actividades de cumplimiento. Cada acción de mejora proporciona instrucciones de implementación detalladas que le ayudarán a alinearse con las normativas y estándares de protección de datos. Las acciones se pueden asignar a los usuarios de la organización para realizar el trabajo de implementación y pruebas. También puede almacenar documentación, notas y registrar actualizaciones de estado dentro de la acción.

Todas las acciones de mejora se enumeran en la página acciones de mejora. Obtenga más información [sobre cómo ver las acciones de mejora](compliance-manager-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Página de detalles de acciones de mejora

Cada acción de mejora tiene una página de detalles que muestra su estado actual, los estándares y requisitos normativos relacionados, y las instrucciones de implementación recomendadas. [Entre las acciones](compliance-score-calculation.md#technical-and-non-technical-actions) técnicas se **incluye un vínculo Iniciar ahora** que le llevará a la solución adecuada para su implementación. Puede adjuntar documentación de implementación y pruebas directamente en la página de detalles de una acción de mejora.

Para ver la página de detalles de una acción de mejora:

1. Vaya a la página de acciones de mejora.
2. Seleccione la fila de la acción de mejora prevista, que abre su página de detalles.

Puedes ver fácilmente la acción de mejora siguiente o anterior en la lista seleccionando la flecha arriba o abajo en la esquina superior derecha de la pantalla. Si filtraste la lista en la página de acciones de mejora, moverte hacia arriba o hacia abajo te llevará al siguiente elemento dentro de esa lista filtrada.

> [!TIP]
> Obtenga más información sobre los [distintos tipos de acciones de mejora y cómo se conceden](compliance-score-calculation.md#action-types-and-points) y se tienen en cuenta los puntos en la puntuación de cumplimiento.

## <a name="assign-improvement-actions"></a>Asignar acciones de mejora

Para iniciar el trabajo de implementación en una acción de mejora, puede realizar el trabajo usted mismo o asignarlo a otro usuario. La persona asignada podría ser:

- Un propietario de la directiva de la empresa
- Un implementador de TI
- Otro empleado con responsabilidad para realizar la tarea

Una vez que identifique al destinatario adecuado, asegúrese de que tienen un rol de [Administrador de cumplimiento](compliance-manager-setup.md#set-user-permissions-and-assign-roles) suficiente para realizar el trabajo. A continuación, siga los pasos siguientes para asignar la acción de mejora:

1. En la página de detalles de acciones de mejora, seleccione **Asignar acción** a la izquierda de la pantalla.

2. El **panel desplegable Asignar a** usuario muestra una **lista de usuarios sugeridos** . Puede seleccionar el usuario de la lista o escribir la dirección de correo electrónico de la persona a la que desea asignarla.

3. Seleccione **Asignar**. El usuario asignado recibirá un correo electrónico explicando que se les ha asignado la acción de mejora, con un vínculo directo a la acción de mejora.

> [!NOTE]
> Los clientes Community administración pública (GCC) altos y del Departamento de Defensa (DoD) no recibirán un correo electrónico cuando se les asignen acciones de mejora.

A continuación, el usuario asignado puede realizar las acciones recomendadas.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Asignar varias acciones de mejora a un solo usuario

Puede asignar varias acciones de mejora a un usuario siguiendo estos pasos:

1. Vaya a la página Acciones de mejora.
2. Seleccione el área a la izquierda del nombre de la acción de mejora. Aparecerá un icono de verificación redondeado que indica que ha seleccionado esa acción. Compruebe todas las acciones que desea asignar.
3. Seleccione el **vínculo Asignar al usuario** en la parte superior de la tabla de acciones de mejora.
4. Aparecerá una ventana emergente. En el **campo Asignar a** , empiece a escribir el nombre de la persona a la que desea asignar las acciones. También puede seleccionar en la lista de personas sugeridas.
5. Después de rellenar el **campo Asignar a** con el nombre del usuario asignado, seleccione **Asignar**.
6. A continuación, verá la página Acciones de mejora con el nuevo usuario asignado que aparece para las acciones que acaba de asignar.

## <a name="change-implementation-details"></a>Detalles de la implementación de cambios

Puede registrar el estado de implementación y la fecha de cada acción de mejora y agregar notas para la referencia interna. Cualquier usuario puede editar estos campos con permisos de edición, no solo por la persona asignada.

Para editar el estado de una acción de mejora, seleccione **Editar detalles de implementación** en la página de detalles. A continuación se muestran los campos y las opciones de estado disponibles:

- **Estado de implementación**
  - **No implementado**: acción aún no implementada
  - **Implementado**: acción implementada
  - **Implementación alternativa**: seleccione esta opción si usó otras herramientas de terceros o realizó otras acciones no incluidas en las recomendaciones de Microsoft
  - **Planeado**: la acción está planeada para la implementación
  - **Fuera del ámbito**: la acción no es relevante para la organización y no contribuye a la puntuación
- **Fecha de implementación**: disponible para seleccionar cuando el estado de implementación es "implementado" o "implementación alternativa"
- **Notas de implementación**: campo de texto para las notas sobre la implementación.

No hay ningún límite de caracteres en los campos de notas. Se recomienda mantener las notas breves para que pueda verlas y editarlas fácilmente desde la página de detalles de las acciones de mejora.

Las acciones comunes se sincronizan entre grupos. Cuando dos evaluaciones diferentes del mismo grupo comparten acciones de mejora administradas por usted, las actualizaciones que realice en los detalles de implementación o el estado de una acción se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. Esta sincronización le permite implementar una acción de mejora y cumplir varios requisitos en varias normativas.

## <a name="change-test-status"></a>Cambiar el estado de la prueba

En la **sección Pruebas** , puede ver el estado de las pruebas de la acción de mejora, la fecha de prueba y cualquier nota. El contenido de estos campos se puede cambiar en **Editar detalles de** prueba por cualquier usuario con permisos de edición.

Los campos disponibles son los siguientes:

- **Estado de la** prueba: disponible para seleccionar cuándo el estado de implementación es "implementado" o "implementación alternativa". Entre las opciones se incluyen:
  - **No evaluado**: la acción no se ha probado
  - **Pasado**: la implementación ha sido verificada por un evaluador
  - **Riesgo bajo con error**: error en las pruebas, bajo riesgo
  - **Riesgo medio fallido**: error en las pruebas, riesgo medio
  - **Alto riesgo de error**: error en las pruebas, alto riesgo
  - **Fuera del ámbito**: la acción está fuera del ámbito de la evaluación y no contribuye a la puntuación
- **Fecha de prueba**: alternar a través de la ventana emergente del calendario para seleccionar la fecha
- **Notas de prueba** y **notas adicionales**: campos de texto para notas para referencia interna

### <a name="update-testing-source"></a>Actualizar origen de pruebas

El Administrador de cumplimiento proporciona opciones para probar acciones de mejora. En la  sección Información general de cada acción de mejora, el área Origen de pruebas tiene un menú desplegable desde el que puede elegir cómo desea que se probará la acción: **Manual**, **Automático** y **Primario**. Obtenga más información sobre cada método de prueba a continuación.

#### <a name="manual-testing-source"></a>Origen de prueba manual
Las acciones de mejora establecidas para las pruebas manuales son acciones que se prueban e implementan manualmente. Se establecen los estados de implementación y estado de prueba necesarios y se cargan los archivos de evidencia en la **pestaña** Documentos. Para algunas acciones, este es el único método disponible para probar acciones de mejora.

#### <a name="automatic-testing-source"></a>Origen de pruebas automáticas
Si una acción de implementación es apta para ser probada automáticamente por el Administrador de cumplimiento, verá la **opción Automático** para el origen de pruebas. El Administrador de cumplimiento detectará las señales de otras soluciones de cumplimiento que haya configurado en su entorno de Microsoft 365, así como las acciones complementarias que también supervisa La puntuación segura de Microsoft. El **campo** Lógica de prueba de  la pestaña Pruebas mostrará qué tipo de directiva o configuración es necesaria en otra solución para que la acción pase y gane puntos hacia la puntuación de cumplimiento.

Cuando las señales indican que una acción de mejora se ha implementado correctamente, recibirás automáticamente los puntos elegibles para esa acción, lo que tendrá en cuenta las puntuaciones de los controles y evaluaciones relacionados. Obtenga más información sobre cómo [la evaluación continua afecta a la puntuación de cumplimiento](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).

 Las pruebas automáticas están en modo predeterminado para todas las acciones de mejora elegibles. Puedes ajustar esta configuración para probar automáticamente solo determinadas acciones de mejora, o puedes desactivar las pruebas automáticas para todas las acciones. Obtenga más información sobre cómo funcionan las pruebas automatizadas y cómo ajustar la configuración en [Configurar pruebas automatizadas](compliance-manager-setup.md#manage-automated-testing-settings).

#### <a name="parent-testing-source"></a>Origen de pruebas primario

Cuando seleccione **Primario como origen** de prueba para una acción de mejora, elegirá otra acción a la que se vinculará la acción. La acción en vigor se convierte en el "elemento secundario" de la acción que designe como "primario". Al designar un elemento primario para una acción de mejora, esa acción será inherente a los detalles de implementación y prueba de la acción principal. Cada vez que cambie el estado de la acción primaria, el estado del elemento secundario heredará dichos cambios. La acción secundaria también aceptará todas las evidencias  de su pestaña Documentos que pertenecen a la acción principal, lo que podría invalidar los datos que existían anteriormente en documents de la **acción secundaria**.

> [!NOTE]
> Tener un origen de prueba de **Parent** no significa necesariamente que el Administrador de cumplimiento prueba automáticamente la acción. Por ejemplo, si el origen de pruebas de la acción principal es **manual**, la acción secundaria tomará el estado de la acción principal, que es una prueba manual e implementación por parte de la organización.

Para configurar un origen de prueba primario, siga estos pasos:

- En una página de detalles de la acción de mejora, busque la **sección Información** general.
- En el **encabezado Origen de** pruebas, **seleccione Primario** en el menú desplegable.
- Seleccione **Asignar elemento primario**.
- En el  panel desplegable Asignar acción de mejora primaria, busque la acción de mejora que desea asignar como elemento primario de la lista o escriba el nombre de la acción en la barra de búsqueda cerca de la parte superior. Cuando identifique la acción prevista, seleccione la casilla que aparece a la izquierda del nombre de la acción cuando mantenga el mouse sobre ella y, a continuación, **seleccione Guardar**.

Volverás a la página de detalles de la acción. En **Origen de prueba** en **la sección** Información general, la nueva acción que designó como elemento primario se muestra en **Acción principal**.

## <a name="review-standards-and-regulations"></a>Revisar estándares y reglamentos

La **sección de estándares y** reglamentos proporciona una lista de estándares y reglamentos que se pueden buscar y filtrar asociados con la acción de mejora. Estos pueden ser vistos por el **control correspondiente**, el identificador de **control**, la **familia de controles** y la **regulación** implicada.

## <a name="perform-work-and-store-documentation"></a>Realizar documentación de trabajo y almacén

Puede cargar archivos y notas relacionados con el trabajo de implementación y pruebas directamente en la **sección** Documentos. Este entorno es un repositorio seguro y centralizado para ayudarle a demostrar la satisfacción de los controles para cumplir con los estándares y normativas de cumplimiento. Cualquier usuario con acceso de solo lectura puede leer contenido en esta sección. Solo los usuarios con derechos de edición pueden cargar y descargar archivos.

#### <a name="uploaded-documents"></a>Documentos cargados

- Seleccione **Administrar documentos para** cargar los archivos relevantes.
- Cuando se abra el panel desplegable Administrar documentos, seleccione **Agregar documento** y, a continuación, seleccione el archivo del sistema. Tipos de archivo aceptados:
  - Documentos (.doc, .xls, .ppt, .txt, .pdf)
  - Imágenes (.jpg, .png)
  - Vídeo (.mkv)
  - Archivos comprimidos (.zip, .rar)
- Una vez que el archivo se resuelva en el panel, seleccione **Cerrar**, que guarda automáticamente los datos adjuntos del archivo. A continuación, verá el archivo que aparece debajo de **Documentos cargados**.
- Para descargar o eliminar el documento, seleccione **Administrar documentos** desde debajo de la lista de documentos. En el panel desplegable, seleccione la fila del documento para resaltarla y, a continuación, **seleccione Descargar** o **Eliminar**.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Asignar acciones de mejora al evaluador para su finalización

Después de completar el trabajo, realizar pruebas y cargar pruebas, el siguiente paso es asignar la acción de mejora a un evaluador para su validación. El evaluador valida el trabajo, examina la documentación y selecciona el estado de prueba adecuado.

**Si el estado de la prueba se establece en "Pasado"**: la acción se completa y los puntos alcanzados muestran los puntos máximos alcanzados. A continuación, los puntos se cuentan para la puntuación general de cumplimiento.

**Si el estado de la** prueba se establece en "Error": la acción no cumple los requisitos y el evaluador puede asignarlo de nuevo al usuario adecuado para trabajos adicionales.

## <a name="accepting-updates-to-improvement-actions"></a>Aceptar actualizaciones de acciones de mejora

Cuando haya una actualización disponible para una acción de mejora, verás una notificación junto a su nombre. Puede aceptar la actualización o aplazar la actualización más adelante.

#### <a name="what-causes-an-update"></a>Qué causa una actualización

Una actualización se produce cuando hay cambios relacionados con la puntuación, la automatización o el ámbito. Los cambios pueden implicar nuevas instrucciones para acciones de mejora basadas en cambios normativos, o podrían deberse a cambios en el producto. Solo las acciones de mejora administradas por las organizaciones reciben notificaciones de actualización.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dónde verá las notificaciones de actualización de evaluación

Cuando se actualiza una acción de mejora, verá una etiqueta De actualización pendiente **junto a su** nombre en la página acciones de mejora y en la página de detalles de sus evaluaciones relacionadas.

Vaya a la página de detalles de la acción de mejora y seleccione  el botón Revisar actualización en el banner superior para revisar los detalles sobre los cambios y aceptar o aplazar la actualización.

#### <a name="review-update-to-accept-or-defer"></a>Revisar la actualización para aceptar o aplazar

Después de seleccionar **Revisar actualización en** la página de detalles de la acción de mejora, aparece un panel desplegable en el lado derecho de la pantalla. El panel desplegable proporciona detalles clave sobre la actualización, como las evaluaciones afectadas y los cambios en la puntuación y el ámbito.

Seleccione **Aceptar actualización** para aceptar todos los cambios realizados en la acción de mejora. **Los cambios aceptados son permanentes**.

> [!NOTE]
> Cuando acepta una actualización de una acción, también acepta actualizaciones de cualquier otra versión o instancia de esta acción. Las actualizaciones se propagarán en todo el espacio empresarial para las acciones técnicas y se propagarán en todo el grupo para acciones no técnicas.

Si selecciona **Cancelar**, la actualización no se aplicará a la acción de mejora. Sin embargo, seguirás consultando la notificación **De actualización** pendiente hasta que aceptes la actualización.

**Por qué se recomienda aceptar actualizaciones**

La aceptación de actualizaciones ayuda a garantizar que tenga las instrucciones más actualizadas sobre el uso de soluciones y la toma de las acciones de mejora adecuadas para ayudarle a cumplir los requisitos de la certificación en la mano.

**Por qué es posible que quieras aplazar una actualización**

Si estás en medio de completar una evaluación que incluya la acción de mejora, es posible que quieras asegurarte de haber terminado de trabajar en ella antes de aceptar la actualización. Puede aplazar la actualización más adelante **seleccionando Cancelar** en el panel desplegable de la actualización de revisión.

#### <a name="accept-all-updates-at-once"></a>Aceptar todas las actualizaciones a la vez

Si tiene varias actualizaciones y desea aceptarlas todas a la vez, seleccione el vínculo Aceptar  todas las actualizaciones en la parte superior de la tabla de acciones de mejora. Aparecerá un panel desplegable que enumera el número de acciones que se van a actualizar. Seleccione el **botón Aceptar actualizaciones** para aplicar todas las actualizaciones.

Tenga en cuenta que al volver a la página de acciones de mejora, es posible que vea un mensaje en la parte superior de la página pidiéndole que actualice la página para que se completen las actualizaciones.

## <a name="set-up-alerts-for-improvement-action-changes"></a>Configurar alertas para cambios en la acción de mejora

Puede configurar alertas para notificarle inmediatamente cuando se produzcan determinados cambios en las acciones de mejora, como un cambio en el estado de implementación o prueba, o un aumento o disminución en la puntuación. Obtener notificaciones rápidas de estos cambios puede ayudarle a mantenerse al tanto de los posibles riesgos de cumplimiento. Visite [Alertas y directivas de alertas del Administrador de cumplimiento](compliance-manager-alert-policies.md) para obtener información sobre cómo configurar alertas.

## <a name="export-a-report"></a>Exportar un informe

Seleccione **Exportar** en la esquina superior izquierda de la pantalla para descargar una hoja de cálculo Excel que contenga todas las acciones de mejora y las categorías de filtro que se muestran en la página acciones de mejora.