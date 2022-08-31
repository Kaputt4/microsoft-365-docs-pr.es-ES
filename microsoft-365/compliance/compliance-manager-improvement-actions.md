---
title: Trabajar con acciones de mejora en el Administrador de cumplimiento de Microsoft Purview
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
description: Obtenga información sobre cómo implementar y probar controles trabajando con acciones de mejora en el Administrador de cumplimiento de Microsoft Purview. Asigne trabajo, almacene documentación y exporte informes.
ms.openlocfilehash: 6388a4e1c4ce73e29481e1e1daa0ee27d733ed8b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67472972"
---
# <a name="working-with-improvement-actions-in-compliance-manager"></a>Trabajar con acciones de mejora en el Administrador de cumplimiento

**En este artículo:** En este artículo se explica cómo **administrar el flujo de trabajo de cumplimiento** con acciones de mejora. Obtenga información sobre cómo **asignar acciones de mejora** para la implementación y las pruebas, **administrar actualizaciones** y exportar **informes**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Administración de flujos de trabajo de cumplimiento con acciones de mejora

Las acciones de mejora centralizan las actividades de cumplimiento. Cada acción de mejora proporciona instrucciones de implementación detalladas para ayudarle a alinearse con las normas y las normas de protección de datos. Las acciones se pueden asignar a los usuarios de su organización para realizar el trabajo de implementación y pruebas. También puede almacenar la documentación, las notas y las actualizaciones de estado de registro dentro de la acción.

Todas las acciones de mejora se muestran en la página acciones de mejora. Obtenga más información sobre [cómo ver las acciones de mejora](compliance-manager-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Página de detalles de acciones de mejora

Cada acción de mejora tiene una página de detalles que muestra su estado actual, los estándares y requisitos normativos relacionados y las instrucciones de implementación recomendadas. [Las acciones técnicas](compliance-score-calculation.md#technical-and-non-technical-actions) incluyen un vínculo **Iniciar ahora** que le lleva a la solución adecuada para la implementación. Puede adjuntar documentación de implementación y pruebas directamente a la página de detalles de una acción de mejora.

Para ver la página de detalles de una acción de mejora:

1. Vaya a la página de acciones de mejora.
2. Seleccione la fila de la acción de mejora prevista, que abre su página de detalles.

Puede ver fácilmente la acción de mejora siguiente o anterior en la lista seleccionando la flecha arriba o abajo en la esquina superior derecha de la pantalla. Si filtró la lista en la página de acciones de mejora, subir o bajar le llevará al siguiente elemento de esa lista filtrada.

> [!TIP]
> Obtenga más información sobre los diferentes [tipos de acciones de mejora y cómo se conceden y factoricen los puntos](compliance-score-calculation.md#action-types-and-points) en la puntuación de cumplimiento.

## <a name="assign-improvement-actions"></a>Asignar acciones de mejora

Para comenzar el trabajo de implementación en una acción de mejora, puede realizar el trabajo usted mismo o asignarlo a otro usuario. La persona asignada podría ser:

- Un propietario de la directiva de la empresa
- Un implementador de TI
- Otro empleado con la responsabilidad de realizar la tarea

Una vez que identifique al asignador adecuado, asegúrese de que tienen un [rol de Administrador de cumplimiento](compliance-manager-setup.md#set-user-permissions-and-assign-roles) suficiente para realizar el trabajo. A continuación, siga los pasos siguientes para asignar la acción de mejora:

1. En la página de detalles de acciones de mejora, seleccione **Asignar acción** a la izquierda de la pantalla.

2. El panel flotante **Asignar a usuario** muestra una lista **de usuarios sugeridos** . Puede seleccionar el usuario de la lista o escribir la dirección de correo electrónico de la persona a la que desea asignarlo.

3. Seleccione **Asignar**. El usuario asignado recibirá un correo electrónico en el que se explica que se le ha asignado la acción de mejora, con un vínculo directo a la acción de mejora.

> [!NOTE]
> Los clientes del Departamento de Defensa (DD) y alto de la Comunidad gubernamental de EE. UU. (GCC) no recibirán un correo electrónico cuando se les asignen acciones de mejora.

A continuación, el usuario asignado puede realizar las acciones recomendadas.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Asignación de varias acciones de mejora a un único usuario

Puede asignar varias acciones de mejora a un usuario siguiendo estos pasos:

1. Vaya a la página Acciones de mejora.
2. Seleccione el área situada a la izquierda del nombre de la acción de mejora. Aparecerá un icono de comprobación redonda que indica que ha seleccionado esa acción. Compruebe todas las acciones que desea asignar.
3. Seleccione el vínculo **Asignar al usuario** en la parte superior de la tabla de acciones de mejora.
4. Aparecerá una ventana emergente. En el campo **Asignar a** , empiece a escribir el nombre de la persona a la que desea asignar las acciones. También puede seleccionar en la lista de personas sugeridas.
5. Después de rellenar el campo **Asignar a** con el nombre del receptor asignado, seleccione **Asignar**.
6. A continuación, verá la página Acciones de mejora con el nuevo asignado en la lista para las acciones que acaba de asignar.

## <a name="change-implementation-details"></a>Cambiar los detalles de la implementación

Puede registrar el estado de implementación y la fecha de cada acción de mejora y agregar notas para la referencia interna. Estos campos los puede editar cualquier usuario con permisos de edición, no solo por la persona asignada.

Para editar el estado de una acción de mejora, seleccione **Editar detalles de implementación** en la página de detalles. A continuación se muestran los campos disponibles y las opciones de estado:

- **Estado de implementación**
  - **No implementado**: acción aún no implementada
  - **Parcialmente implementada**: para las acciones probadas automáticamente, la acción se implementa parcialmente (ni pasa ni produce un error) y recibe una puntuación parcial.
  - **Implementado**: acción implementada
  - **Implementación alternativa**: seleccione esta opción si ha usado otras herramientas de terceros o ha realizado otras acciones no incluidas en las recomendaciones de Microsoft.
  - **Planeado**: la acción está planeada para la implementación
  - **Fuera del ámbito**: la acción no es relevante para su organización y no contribuye a la puntuación.
- **Fecha de implementación**: disponible para seleccionar cuándo se "implementa" o "implementación alternativa"
- **Notas de implementación**: campo de texto para las notas sobre la implementación.

No hay ningún límite de caracteres en los campos de notas. Se recomienda mantener las notas breves para que pueda verlas y editarlas fácilmente desde la página de detalles de acciones de mejora.

Las acciones comunes se sincronizan entre grupos. Cuando dos evaluaciones diferentes del mismo grupo comparten acciones de mejora administradas por usted, las actualizaciones que realice en los detalles de implementación o el estado de una acción se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. Esta sincronización le permite implementar una acción de mejora y cumplir varios requisitos en varias regulaciones.

## <a name="change-test-status"></a>Cambio del estado de la prueba

En la sección **Pruebas** , puede ver el estado de las pruebas de la acción de mejora, la fecha de prueba y las notas. Un usuario con permisos de edición puede seleccionar  **Editar detalles de pruebas** para editar contenido en la pestaña **Pruebas** .

#### <a name="testing-status-fields"></a>Campos de estado de prueba

**Estado de la prueba**
 
Puede editar el estado de prueba cuando el estado de implementación de una acción de mejora se "implemente" o "implementación alternativa".

Estados de prueba para [las acciones probadas manualmente](#manual-testing-source):
  - **Ninguno**: no se ha iniciado ningún trabajo en la acción
  - **No evaluado**: no se ha probado la acción
  - **Pasado**: un evaluador ha comprobado la implementación
  - **Riesgo bajo fallido**: error en las pruebas, riesgo bajo
  - **Riesgo medio erróneo**: error en las pruebas, riesgo medio
  - **Alto riesgo fallido**: error en las pruebas, riesgo alto
  - **Fuera del ámbito**: la acción está fuera del ámbito de la evaluación y no contribuye a la puntuación
  - **En curso**: pruebas en curso
  - **Corregido**: tbd

[Las acciones probadas automáticamente](#automatic-testing-source) también pueden mostrar uno de los siguientes estados en la columna **Estado** de prueba de la página **Acciones de mejora** :
   - **Para detectar:** señales en espera que indican el estado de la prueba
  - **No se pudo detectar**: no se pudo detectar un estado de prueba; se volverá a comprobar automáticamente
  - **Parcialmente probado**: la acción se ha probado parcialmente;  ni pasa ni produce errores

> [!NOTE]
> Las notas de estado y pruebas de las acciones de mejora probadas automáticamente no se pueden editar manualmente. El Administrador de cumplimiento actualiza estos campos automáticamente.

**Fecha de prueba**

Cambie por el elemento emergente del calendario para seleccionar la fecha de prueba.

**Notas de prueba** y **notas adicionales**

Escriba notas para su propia referencia interna en estos campos de texto libre.

**Historial de pruebas**

El historial de pruebas proporciona un informe descargado de todos los cambios de estado de prueba para la acción de mejora.

#### <a name="exporting-testing-history"></a>Exportación del historial de pruebas
Puede exportar un informe que le mostrará un historial de todos los cambios en el estado de prueba para una acción de mejora. Estos informes son especialmente útiles para supervisar el progreso de [las acciones que se prueban automáticamente](#automatic-testing-source), ya que estas acciones se actualizan con regularidad o con frecuencia en función de los datos del inquilino.

En la página de detalles de una acción de mejora, seleccione la pestaña **Pruebas** . En **Historial de pruebas**, seleccione el botón **Exportar historial de pruebas** . El informe se descargará como un archivo de Excel.

## <a name="update-testing-source"></a>Actualización del origen de las pruebas

El Administrador de cumplimiento proporciona opciones para probar las acciones de mejora. En la sección **Información general** de cada acción de mejora, el área **Origen de pruebas** tiene un menú desplegable desde el que puede elegir cómo desea probar la acción: **Manual**, **Automático** y **Primario**. Obtenga más información sobre cada método de prueba a continuación.

#### <a name="manual-testing-source"></a>Origen de pruebas manuales
Las acciones de mejora establecidas para las pruebas manuales son acciones que se prueban e implementan manualmente. Establezca los estados de implementación y estado de prueba necesarios, y cargue los archivos de evidencia en la pestaña **Documentos** . Para algunas acciones, este es el único método disponible para probar las acciones de mejora.

#### <a name="automatic-testing-source"></a>Origen de pruebas automáticas
El Administrador de cumplimiento puede probar automáticamente determinadas acciones de mejora. [Obtenga detalles](compliance-manager-setup.md#set-up-automated-testing) sobre qué acciones de mejora se pueden probar automáticamente y qué no.

Para las acciones de mejora que se pueden probar automáticamente, verá la opción **Automático** para probar el origen. El Administrador de cumplimiento detectará señales de otras soluciones de cumplimiento que haya configurado en el entorno de Microsoft 365, así como las acciones complementarias que microsoft Secure Score también supervisa. El campo **Lógica de prueba** de la pestaña **Pruebas** mostrará qué tipo de directiva o configuración es necesaria en otra solución para que la acción pase y obtenga puntos para la puntuación de cumplimiento.

Cuando las señales indican que una acción de mejora se ha implementado correctamente, recibirá automáticamente los puntos aptos para esa acción, que tendrán en cuenta las puntuaciones de los controles y evaluaciones relacionados. Obtenga más información sobre cómo [afecta la evaluación continua a la puntuación de cumplimiento](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).

 Las pruebas automáticas están activadas de forma predeterminada para todas las acciones de mejora aptas. Puede ajustar esta configuración para probar automáticamente solo ciertas acciones de mejora, o puede desactivar las pruebas automáticas para todas las acciones. Obtenga más información sobre cómo funcionan las pruebas automatizadas y cómo ajustar la configuración en [Configuración de pruebas automatizadas](compliance-manager-setup.md#manage-automated-testing-settings).

#### <a name="parent-testing-source"></a>Origen de las pruebas primarias

Al seleccionar **Primario** como origen de prueba para una acción de mejora, elegirá otra acción a la que se vinculará la acción. La acción en vigor se convierte en el "elemento secundario" de la acción que designa como "elemento primario". Cuando designa un elemento primario para una acción de mejora, esa acción será inherente a los detalles de implementación y prueba de la acción primaria. Cada vez que cambie el estado de la acción primaria, el estado del elemento secundario heredará esos cambios. La acción secundaria también aceptará todas las pruebas de la pestaña **Documentos** que pertenecen a la acción primaria, lo que podría invalidar los datos que existían anteriormente en los **documentos** de la acción secundaria.

> [!NOTE]
> Tener un origen de prueba de **Parent** no significa necesariamente que el Administrador de cumplimiento pruebe automáticamente la acción. Por ejemplo, si el origen de las pruebas de la acción primaria es **manual**, la acción secundaria tomará el estado de la acción primaria, que es una prueba e implementación manual por parte de la organización.

Para configurar un origen de pruebas primario, siga estos pasos:

- En una página de detalles de una acción de mejora, busque la sección **Información general** .
- En el encabezado **Testing Source (Origen de pruebas** ), seleccione **Parent (Primario** ) en el menú desplegable.
- Seleccione **Asignar elemento primario**.
- En el panel flotante **Asignar acción de mejora primaria** , busque la acción de mejora que desea asignar como elemento primario de la lista o escriba el nombre de la acción en la barra de búsqueda situada cerca de la parte superior. Cuando identifique la acción prevista, active la casilla que aparece a la izquierda del nombre de la acción al mantener el puntero sobre ella y, a continuación, seleccione **Guardar**.

Volverá a la página de detalles de la acción. En **Probar origen** en la sección **Información general** , la nueva acción que designó como elemento primario aparece en **Acción principal**.

## <a name="review-standards-and-regulations"></a>Revisión de estándares y reglamentos

La sección **de estándares y regulaciones** proporciona una lista filtrable y de búsqueda de estándares y reglamentos asociados a su acción de mejora. Estos pueden ser vistos por el **control** pertinente, el **identificador de control**, la **familia de control** y la **regulación** implicada.

## <a name="perform-work-and-store-documentation"></a>Documentación de trabajo y almacenamiento

Puede cargar pruebas en forma de archivos y vínculos relacionados con el trabajo de implementación y pruebas directamente en la sección **Documentos** . Este entorno es un repositorio seguro y centralizado que le ayudará a demostrar la satisfacción de los controles para cumplir los estándares y las regulaciones de cumplimiento. Cualquier usuario con acceso de solo lectura puede leer contenido en esta sección. Solo los usuarios con derechos de edición pueden cargar y descargar archivos.

#### <a name="upload-evidence"></a>Carga de pruebas

- En la página de detalles de la acción de mejora, vaya a la pestaña **Documentos** y seleccione **Agregar evidencia**.
- En el panel flotante **Agregar evidencia** , elija si desea agregar un **documento** o **un vínculo**. Los tipos de archivo aceptados para **Document** son:
  - Documentos (.doc, .xls, .ppt, .txt, .pdf)
  - Imágenes (.jpg, .png)
  - Vídeo (.mkv)
  - Archivos comprimidos (.zip, .rar)
- Vaya a para seleccionar el archivo que desea cargar. Si carga un vínculo, escriba un nombre para el vínculo y su dirección URL. Cuando haya terminado, seleccione **Agregar**. El elemento se mostrará ahora en la pestaña **Documentos** .

Para eliminar archivos o vínculos de evidencia, seleccione el menú de acción (los tres puntos) a la derecha del nombre del elemento y seleccione **Eliminar**. Confirme la eliminación cuando se le solicite.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Asignación de una acción de mejora al evaluador para la finalización

Después de completar el trabajo, realizar pruebas y cargar pruebas, el siguiente paso es asignar la acción de mejora a un evaluador para la validación. El evaluador valida el trabajo, examina la documentación y selecciona el estado de prueba adecuado.

**Si el estado de la prueba está establecido en "Pasado"**: la acción se completa y los puntos alcanzados muestran los puntos máximos alcanzados. A continuación, los puntos se cuentan para la puntuación de cumplimiento general.

**Si el estado de la prueba está establecido en "Failed"**: la acción no cumple los requisitos y el evaluador puede asignarlo de nuevo al usuario adecuado para un trabajo adicional.

## <a name="accepting-updates-to-improvement-actions"></a>Aceptación de actualizaciones para acciones de mejora

Cuando haya una actualización disponible para una acción de mejora, verá una notificación junto a su nombre. Puede aceptar la actualización o aplazarla más adelante.

#### <a name="what-causes-an-update"></a>¿Qué provoca una actualización?

Una actualización se produce cuando hay cambios relacionados con la puntuación, la automatización o el ámbito. Los cambios pueden implicar nuevas instrucciones para las acciones de mejora basadas en cambios normativos, o bien pueden deberse a cambios en el producto. Solo las acciones de mejora administradas por las organizaciones reciben notificaciones de actualización.

#### <a name="where-youll-see-assessment-update-notifications"></a>Donde verá las notificaciones de actualización de evaluación

Cuando se actualiza una acción de mejora, verá una etiqueta **de actualización Pendiente** junto a su nombre en la página acciones de mejora y en la página de detalles de sus evaluaciones relacionadas.

Vaya a la página de detalles de la acción de mejora y seleccione el botón **Revisar actualización** del banner superior para revisar los detalles sobre los cambios y aceptar o aplazar la actualización.

#### <a name="review-update-to-accept-or-defer"></a>Revisión de la actualización para aceptar o aplazar

Después de seleccionar **Revisar actualización** en la página de detalles de la acción de mejora, aparece un panel flotante en el lado derecho de la pantalla. El panel flotante proporciona detalles clave sobre la actualización, como las evaluaciones afectadas y los cambios en la puntuación y el ámbito.

Seleccione **Aceptar actualización** para aceptar todos los cambios en la acción de mejora. **Los cambios aceptados son permanentes**.

> [!NOTE]
> Al aceptar una actualización de una acción, también acepta actualizaciones de cualquier otra versión o instancia de esta acción. Novedades propagará todo el inquilino para acciones técnicas y propagará todo el grupo para acciones no técnicas.

Si selecciona **Cancelar**, la actualización no se aplicará a la acción de mejora. Sin embargo, seguirá viendo la notificación **De actualización pendiente** hasta que acepte la actualización.

**Por qué se recomienda aceptar actualizaciones**

Aceptar actualizaciones ayuda a garantizar que tiene las instrucciones más actualizadas sobre el uso de soluciones y la adopción de las acciones de mejora adecuadas para ayudarle a cumplir los requisitos de la certificación en cuestión.

**Por qué es posible que quiera aplazar una actualización**

Si está en medio de completar una evaluación que incluye la acción de mejora, es posible que desee asegurarse de que ha terminado de trabajar en ella antes de aceptar la actualización. Para aplazar la actualización más adelante, seleccione **Cancelar** en el panel flotante Revisar actualización.

#### <a name="accept-all-updates-at-once"></a>Aceptar todas las actualizaciones a la vez

Si tiene varias actualizaciones y quiere aceptarlas todas a la vez, seleccione el vínculo **Aceptar todas las actualizaciones** en la parte superior de la tabla de acciones de mejora. Aparecerá un panel flotante que enumera el número de acciones que se van a actualizar. Seleccione el botón **Aceptar actualizaciones** para aplicar todas las actualizaciones.

Tenga en cuenta que cuando vuelva a la página de acciones de mejora, es posible que vea un mensaje en la parte superior de la página que le pide que actualice la página para que se completen las actualizaciones.

## <a name="set-up-alerts-for-improvement-action-changes"></a>Configuración de alertas para cambios en las acciones de mejora

Puede configurar alertas para notificarle inmediatamente cuando se produzcan determinados cambios en las acciones de mejora, como un cambio en el estado de implementación o prueba, o un aumento o disminución de la puntuación. Recibir notificaciones rápidas de estos cambios puede ayudarle a mantenerse al tanto de los posibles riesgos de cumplimiento. Visite [Alertas y directivas de alertas del Administrador](compliance-manager-alert-policies.md) de cumplimiento para obtener información sobre cómo configurar alertas.

## <a name="export-a-report"></a>Exportación de un informe

Seleccione **Exportar** en la esquina superior izquierda de la pantalla para descargar una hoja de cálculo de Excel que contenga todas las acciones de mejora y las categorías de filtro que se muestran en la página acciones de mejora.

El archivo de Excel exportado también es lo que se usa para actualizar varias acciones de mejora a la vez. Obtenga detalles sobre cómo editar el archivo de exportación para [actualizar varias acciones de mejora](compliance-manager-update-actions.md).