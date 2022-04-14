---
title: 'Escenario de derrame de datos de la serie de soluciones eDiscovery: búsqueda y purga'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Use eDiscovery y herramientas de búsqueda para administrar y responder a un incidente de derrame de datos en su organización.
ms.openlocfilehash: 106a67bff07f76d3ac40798d8bb4e28a254b923d
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64847341"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>Serie de soluciones de eDiscovery: escenario de desbordamiento de datos: búsqueda y purga

 **¿Qué es el derrame de datos y por qué debe preocuparse?** El derrame de datos se produce cuando un documento confidencial se libera en un entorno que no es de confianza. Cuando se detecta un incidente de derrame de datos, es importante evaluar rápidamente el tamaño y las ubicaciones del derrame, examinar las actividades del usuario a su alrededor y, a continuación, purgar permanentemente los datos derramados del sistema.
  
## <a name="data-spillage-scenario"></a>Escenario de derrame de datos

Es responsable de seguridad de la información en Contoso. Se le informa de una situación de derrame de datos en la que un empleado compartió sin saberlo un documento altamente confidencial con varias personas a través del correo electrónico. Quiere evaluar rápidamente quién recibió este documento interna y externamente. Una vez identificado, le gustaría compartir los resultados de los casos con otros investigadores para revisarlos y, a continuación, quitar permanentemente los datos de Office 365. Una vez completada la investigación, desea generar un informe con la evidencia de eliminación permanente y otros detalles del caso para cualquier referencia futura.
  
### <a name="scope-of-this-article"></a>Ámbito de este artículo

En este documento se proporciona una lista de instrucciones sobre cómo quitar permanentemente un mensaje de Microsoft 365 para que no sea accesible ni recuperable. Para eliminar un mensaje y hacerlo recuperable hasta que expire el período de retención de elementos eliminados, consulte [Búsqueda y eliminación de mensajes de correo electrónico en su organización](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Flujo de trabajo para administrar incidentes de desbordamiento de datos

Este es un procedimiento para administrar un incidente de derrame de datos:

![Flujo de trabajo de 8 pasos para administrar incidentes de desbordamiento de datos.](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[(Opcional) Paso 1: Administrar quién puede acceder al caso y establecer límites de cumplimiento](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Paso 2: Crear un caso de exhibición de documentos electrónicos](#step-2-create-an-ediscovery-case)<br/>
[Paso 3: Búsqueda de los datos derramados](#step-3-search-for-the-spilled-data)<br/>
[Paso 4: Revisar y validar los resultados de los casos](#step-4-review-and-validate-case-findings)<br/>
[Paso 5: Uso del registro de seguimiento de mensajes para comprobar cómo se han compartido los datos derramados](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Paso 6: Preparar los buzones](#step-6-prepare-the-mailboxes)<br/>
[Paso 7: Eliminar permanentemente los datos derramados](#step-7-permanently-delete-the-spilled-data)<br/>
[Paso 8: Comprobar, proporcionar una prueba de eliminación y auditoría](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Cosas que debe saber antes de empezar

- El flujo de trabajo de desbordamiento de datos descrito en este artículo no elimina mensajes de chat en Microsoft Teams. Para buscar y eliminar Teams mensajes de chat, consulte [Buscar y purgar mensajes de chat en Teams](search-and-delete-Teams-chat-messages.md).

- Cuando un buzón está en espera, un mensaje eliminado permanece en la carpeta Elementos recuperables hasta que expire el período de retención o se libere la suspensión. [En el paso 6 se](#step-6-prepare-the-mailboxes) describe cómo quitar la retención de los buzones. Consulte con los departamentos legales o de administración de registros antes de quitar la suspensión. Su organización puede tener una directiva que defina si un buzón en espera o un incidente de derrame de datos tiene prioridad. 

- Para controlar qué buzones de usuario puede buscar y administrar un investigador de derrame de datos que pueda acceder al caso, puede configurar los límites de cumplimiento y crear un grupo de roles personalizado, que se describe en el [paso 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). Para ello, debe ser miembro del grupo de roles Administración de la organización o tener asignado el rol de administración de roles. Si usted o un administrador de su organización ya ha establecido límites de cumplimiento, puede omitir el paso 1.

- Para crear un caso, debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos o ser miembro de un grupo de roles personalizado al que se haya asignado el rol Administración de casos. Si no es miembro, pida a un administrador de Microsoft 365 [que le agregue al grupo de roles del administrador de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

- Para crear y ejecutar una búsqueda de contenido, tiene que ser miembro del grupo de roles Administrador de eDiscovery o tener asignado el rol de administración Búsqueda de cumplimiento. Para eliminar mensajes, tiene que ser miembro del grupo de roles Administración de la organización o tener asignado el rol de administración Búsqueda y eliminación. Para obtener información sobre cómo agregar usuarios a un grupo de roles, vea [Asignar permisos de exhibición de documentos electrónicos](./assign-ediscovery-permissions.md).

- Para buscar en las actividades de eDiscovery del registro de auditoría en el paso 8, la auditoría debe estar activada para su organización. Puede buscar actividades que se realizaron en los últimos 90 días. Para obtener más información sobre cómo habilitar y usar la auditoría, consulte la sección [Auditoría del proceso de investigación del derrame de datos en el](#auditing-the-data-spillage-investigation-process) paso 8.

## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>(Opcional) Paso 1: Administrar quién puede acceder al caso y establecer límites de cumplimiento

En función de la práctica de la organización, debe controlar quién puede acceder al caso de exhibición de documentos electrónicos que se usa para investigar un incidente de derrame de datos y configurar los límites de cumplimiento. La manera más fácil de hacerlo es agregar investigadores como miembros de un grupo de roles existente en el Centro de cumplimiento de Microsoft 365 y, a continuación, agregar el grupo de roles como miembro del caso de eDiscovery. Para obtener información sobre los grupos de roles de eDiscovery integrados y cómo agregar miembros a un caso de exhibición de documentos electrónicos, vea [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).
  
También puede crear un nuevo grupo de roles que se adapte a las necesidades de la organización. Por ejemplo, es posible que desee que un grupo de investigadores de derrame de datos de la organización accedan a todos los casos de derrame de datos y colaboren en ellos. Para ello, cree un grupo de roles "Investigador de derrame de datos", asigne los roles adecuados (Export, RMS Decrypt, Review, Preview, Compliance Search y Case Management), agregue los investigadores de derrame de datos al grupo de roles y, a continuación, agregue el grupo de roles como miembro del caso de eDiscovery de derrame de datos. Consulte [Set up compliance boundaries for eDiscovery investigations in Office 365 (Configurar límites de cumplimiento para investigaciones de eDiscovery en Office 365](set-up-compliance-boundaries.md)) para obtener instrucciones detalladas sobre cómo hacerlo. 
  
## <a name="step-2-create-an-ediscovery-case"></a>Paso 2: Crear un caso de exhibición de documentos electrónicos

Un caso de exhibición de documentos electrónicos proporciona una manera eficaz de administrar la investigación de derrame de datos. Puede agregar miembros al grupo de roles que creó en el paso 1, agregar el grupo de roles como miembro de un nuevo caso de exhibición de documentos electrónicos, realizar búsquedas iterativas para buscar los datos derramados, exportar un informe para compartir, realizar un seguimiento del estado del caso y, a continuación, volver a consultar los detalles del caso si es necesario. Considere la posibilidad de establecer una convención de nomenclatura para los casos de exhibición de documentos electrónicos usados para incidentes de desbordamiento de datos y proporcionar toda la información posible en el nombre y la descripción del caso para que pueda localizar y hacer referencia en el futuro si es necesario.
  
Para crear un nuevo caso, puede usar eDiscovery en el centro de seguridad y cumplimiento. Consulte "Crear un nuevo caso" en [Comenzar con eDiscovery principal](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).
  
## <a name="step-3-search-for-the-spilled-data"></a>Paso 3: Búsqueda de los datos derramados

Ahora que ha creado un caso y un acceso administrado, puede usar el caso para buscar iterativamente los datos derramados e identificar los buzones que contienen los datos derramados. Usará la misma consulta de búsqueda que usó para buscar los mensajes de correo electrónico para eliminar esos mismos mensajes en el [paso 7](#step-7-permanently-delete-the-spilled-data).
  
Para crear una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos, vea [Buscar contenido en un caso de eDiscovery principal](search-for-content-in-core-ediscovery.md).
  
> [!IMPORTANT]
> Las palabras clave que se usan en la consulta de búsqueda pueden contener los datos derramados reales que está buscando. Por ejemplo, si busca documentos que contengan un número de seguridad social y lo usa como palabra clave de búsqueda, debe eliminar la consulta posteriormente para evitar más derrames. Consulte [Eliminación de la consulta de búsqueda en el](#deleting-the-search-query) paso 8.
  
## <a name="step-4-review-and-validate-case-findings"></a>Paso 4: Revisar y validar los resultados de los casos

Después de crear una búsqueda de contenido, debe revisar y validar que los resultados de la búsqueda y comprobar que solo constan de los mensajes de correo electrónico que se deben eliminar. En una búsqueda de contenido, puede obtener una vista previa de un muestreo aleatorio de 1000 mensajes de correo electrónico sin exportar los resultados de la búsqueda para evitar más derrames de datos. Puede obtener más información sobre las limitaciones de la versión preliminar en [Límites de búsqueda de contenido](limits-for-content-search.md).
  
Si tiene más de 1000 buzones o más de 100 mensajes de correo electrónico por buzón para revisar, puede dividir la búsqueda inicial en varias búsquedas mediante palabras clave o condiciones adicionales, como intervalo de fechas o remitente o destinatario, y revisar los resultados de cada búsqueda individualmente. Asegúrese de anotar todas las consultas de búsqueda que se usarán al eliminar mensajes en [el paso 7](#step-7-permanently-delete-the-spilled-data).

Cuando encuentre un mensaje de correo electrónico que contenga datos derramados, compruebe los destinatarios del mensaje para determinar si se ha compartido externamente. Para realizar un seguimiento adicional de un mensaje, puede recopilar información del remitente y intervalos de fechas para poder usar los registros de seguimiento de mensajes. Este proceso se describe en [el paso 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).

Después de comprobar los resultados de la búsqueda, es posible que desee compartir sus conclusiones con otros usuarios para una revisión secundaria. Las personas que ha asignado al caso en el paso 1 pueden revisar el contenido del caso en eDiscovery y Advanced eDiscovery y aprobar los resultados del caso. También puede generar un informe sin exportar el contenido real. También puede usar este mismo informe como prueba de eliminación, que se describe en [el paso 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).
  
 **Para generar un informe estadístico:**
  
1. Vaya a la página **Buscar** en el caso de exhibición de documentos electrónicos y haga clic en la búsqueda para la que desea generar un informe. 
    
2. En la página de control flotante, haga clic en **Más > exportar informe**.
 
      Se muestra la página Exportar informe.

    ![Seleccione la búsqueda y, a continuación, haga clic en Más > exportar informe en la página de control flotante.](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Seleccione **Todos los elementos, incluidos los que tienen formato no reconocido, se cifran o no se indexaron por otros motivos** y, a continuación, haga clic en **Generar informe**.

4. En el caso de eDiscovery, haga clic en **Exportar** para mostrar la lista de trabajos de exportación. Es posible que tenga que hacer clic en **Actualizar** para actualizar la lista para mostrar el trabajo de exportación que ha creado.

5. Haga clic en el trabajo de exportación y, a continuación, haga clic en **Descargar** informe en la página de control flotante.
 
    ![En la página Exportar, haga clic en la exportación y, a continuación, haga clic en "Descargar informe".](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

El informe **Exportar resumen** contiene el número de ubicaciones encontradas con los resultados y el tamaño de los resultados de la búsqueda. Puede usarlo para compararlo con el informe generado después de la eliminación y proporcionar como prueba de eliminación. El informe **Resultados** contiene un resumen más detallado de los resultados de la búsqueda, incluidos el asunto, el remitente, los destinatarios, si se leyó el correo electrónico, las fechas y el tamaño de cada mensaje. Si alguno de los detalles de este informe contiene los datos reales derramados, asegúrese de eliminar permanentemente el archivo Results.csv cuando se complete la investigación.

Para obtener más información sobre la exportación de informes, vea [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Paso 5: Uso del registro de seguimiento de mensajes para comprobar cómo se han compartido los datos derramados

Para investigar aún más si se ha compartido el correo electrónico con datos derramados, opcionalmente puede consultar los registros de seguimiento de mensajes con la información del remitente y la información del intervalo de fechas que recopiló en el paso 4. El período de retención para el seguimiento de mensajes es de 30 días para los datos en tiempo real y de 90 días para los datos históricos.
  
Puede usar seguimiento de mensajes en el centro de seguridad y cumplimiento o usar los cmdlets correspondientes en Exchange Online PowerShell. Es importante tener en cuenta que el seguimiento de mensajes no ofrece garantías completas sobre la integridad de los datos devueltos. Para obtener más información sobre el uso del seguimiento de mensajes, consulte: 
  
- [Seguimiento de mensajes en el Centro de seguridad y cumplimiento](../security/office-365-security/message-trace-scc.md)
    
- [Nuevo seguimiento de mensajes en el Centro de cumplimiento de & de seguridad](https://techcommunity.microsoft.com/t5/exchange-team-blog/new-message-trace-in-office-365-security-038-compliance-center/ba-p/607893)
    
## <a name="step-6-prepare-the-mailboxes"></a>Paso 6: Preparar los buzones

Después de revisar y validar que los resultados de la búsqueda contienen solo los mensajes que se deben eliminar, debe recopilar una lista de las direcciones de correo electrónico de los buzones afectados para usarlas en el paso 7 al eliminar los datos derramados. También puede que tenga que preparar los buzones para poder eliminar permanentemente los mensajes de correo electrónico en función de si la recuperación de elementos únicos está habilitada en los buzones que contienen los datos derramados o si alguno de esos buzones está en espera.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Obtener una lista de direcciones de buzones con datos derramados

Hay dos maneras de recopilar una lista de direcciones de correo electrónico de buzones con datos derramados.

**Opción 1: Obtener una lista de direcciones de buzones con datos derramados**

1. Abra el caso de eDiscovery, vaya a la página **Buscar** y seleccione la búsqueda de contenido adecuada. 
    
2. En la página de control flotante, haga clic en **Ver resultados**.
    
3. En la lista desplegable de **resultados individuales**, haga clic en **Estadísticas de búsqueda**.
    
4. En la lista desplegable **Tipo** , haga clic en **Ubicaciones principales**.
    
    ![Obtenga una lista de buzones que contienen resultados de búsqueda en la página Ubicaciones principales de las estadísticas de búsqueda.](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Se muestra una lista de buzones que contienen resultados de búsqueda. También se muestra el número de elementos de cada buzón que coinciden con la consulta de búsqueda.
    
5. Copie la información de la lista y guárdela en un archivo o haga clic en **Descargar** para descargar la información en un archivo CSV. 
    
**Opción 2: Obtener ubicaciones de buzones del informe de exportación**

Abra el informe Exportar resumen que descargó en [el paso 4](#step-4-review-and-validate-case-findings). En la primera columna del informe, la dirección de correo electrónico de cada buzón aparece en **Ubicaciones**.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Prepare los buzones para que pueda eliminar los datos derramados.

Si la recuperación de elementos únicos está habilitada o si un buzón está en espera, se conservará un mensaje eliminado permanentemente (purgado) en la carpeta Elementos recuperables. Por lo tanto, antes de poder purgar los datos derramados, debe comprobar las configuraciones de buzón existentes y deshabilitar la recuperación de elementos únicos y quitar cualquier directiva de retención o suspensión. Tenga en cuenta que puede preparar un buzón a la vez y, a continuación, ejecutar el mismo comando en buzones diferentes o crear un script de PowerShell para preparar varios buzones al mismo tiempo.

- Consulte "Paso 1: Recopilar información sobre el buzón" en [Eliminar elementos de la carpeta Elementos recuperables de buzones basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) para obtener instrucciones sobre cómo comprobar si la recuperación de elementos únicos está habilitada o si el buzón está en espera o si está asignado a una directiva de retención. 

- Consulte "Paso 2: Preparar el buzón" en [Eliminar elementos de la carpeta Elementos recuperables de buzones basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) para obtener instrucciones sobre cómo deshabilitar la recuperación de elementos únicos. 

- Consulte "Paso 3: Quitar todas las retenciones del buzón" en [Eliminar elementos de la carpeta Elementos recuperables de buzones basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) para obtener instrucciones sobre cómo quitar una directiva de retención o suspensión de un buzón. 

- Consulte "Paso 4: Quitar la retención de retraso del buzón" en [Eliminar elementos de la carpeta Elementos recuperables de buzones basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) para obtener instrucciones sobre cómo quitar la retención de retraso que se coloca en el buzón después de quitar cualquier tipo de suspensión.

> [!IMPORTANT]
> Consulte con los departamentos legales o de administración de registros antes de quitar una directiva de retención o suspensión. Su organización puede tener una directiva que defina si un buzón en espera o un incidente de derrame de datos tiene prioridad. 
  
Asegúrese de revertir el buzón a configuraciones anteriores después de comprobar que los datos derramados se han eliminado permanentemente. Consulte los detalles del [paso 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Paso 7: Eliminar permanentemente los datos derramados

Con las ubicaciones de buzón que recopiló y preparó en el paso 6 y la consulta de búsqueda que se creó y refinó en el paso 3 para buscar mensajes de correo electrónico que contienen los datos derramados, ahora puede eliminar permanentemente los datos derramados.  Como se explicó anteriormente, para eliminar mensajes, debe ser miembro del grupo de roles Administración de la organización o tener asignado el rol de administración Buscar y purgar. Para obtener información sobre cómo agregar usuarios a un grupo de roles, vea [Asignar permisos de exhibición de documentos electrónicos](./assign-ediscovery-permissions.md).

Para eliminar los mensajes derramados, consulte [Búsqueda y eliminación de mensajes de correo electrónico](search-for-and-delete-messages-in-your-organization.md).

Tenga en cuenta los siguientes límites al eliminar los datos derramados:

- El número máximo de buzones de una búsqueda que puede usar para eliminar elementos realizando una acción de búsqueda y purga es de 50 000. Si la búsqueda que crea en el paso 3 busca en más de 50 000 buzones, se producirá un error en la acción de purga. Hacer la búsqueda en más de 50 000 buzones en una sola búsqueda suele ocurrir cuando se configura para que incluya a todos los buzones de la organización. Esta restricción aplica incluso cuando haya menos de 50 000 buzones que contengan elementos que coincidan con la consulta de la búsqueda.

- Se puede eliminar un máximo de 10 elementos por buzón a la vez. Como la función de buscar y quitar mensajes está diseñada para ser una herramienta de respuesta a incidentes, este límite ayuda a garantizar que los mensajes se quitan rápidamente de los buzones. Esta característica no está diseñada para limpiar buzones de usuarios.

> [!IMPORTANT]
> Los elementos de correo electrónico en un conjunto de revisiones en un caso de eDiscovery avanzado no se pueden eliminar utilizando los procedimientos de este artículo. Esto se debe a que los elementos de un conjunto de revisión son copias de elementos del servicio en directo que se copian y almacenan en una ubicación Azure Storage. Esto significa que no se devolverán mediante una búsqueda de contenido que cree en el paso 3. Para eliminar elementos en un conjunto de revisiones, tiene que eliminar el caso de eDiscovery avanzado que contiene el conjunto de revisiones. Para más información, consulte [Cerrar o eliminar un caso de eDiscovery avanzado](close-or-delete-case.md).
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Paso 8: Comprobar, proporcionar una prueba de eliminación y auditoría

El último paso del flujo de trabajo para administrar un incidente de desbordamiento de datos es comprobar que los datos derramados se quitaron permanentemente del buzón yendo al caso de eDiscovery y volviendo a ejecutar la misma consulta de búsqueda que se usó para eliminar esos datos para confirmar que no se devuelven resultados. Después de confirmar que los datos derramados se han quitado permanentemente, puede exportar un informe e incluirlo (junto con el informe original) como prueba de eliminación. A continuación, puede [cerrar el caso](close-reopen-delete-core-ediscovery-cases.md) , lo que le permitirá volver a abrirlo si tiene que hacer referencia a él en el futuro. Además, también puede revertir los buzones a su estado anterior, eliminar la consulta de búsqueda usada para buscar los datos derramados y buscar registros de auditoría de las tareas realizadas al administrar el incidente de desbordamiento de datos.
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Revertir los buzones a su estado anterior

Si cambió cualquier configuración de buzón en el paso 6 para preparar los buzones antes de que se eliminaran los datos derramados, deberá revertirlos a su estado anterior. Consulte "Paso 6: Revertir el buzón a su estado anterior" en [Eliminar elementos de la carpeta Elementos recuperables de buzones basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state).
  
### <a name="deleting-the-search-query"></a>Eliminación de la consulta de búsqueda

Si las palabras clave de la consulta de búsqueda que creó y usó en el paso 3 contienen algunos de los datos derramados reales, debe eliminar la consulta de búsqueda para evitar más derrames de datos.
  
1. En el Centro de seguridad y cumplimiento, abra el caso de exhibición de documentos electrónicos, vaya a la página **Buscar** y seleccione la búsqueda de contenido adecuada.

2. En la página de control flotante, haga clic en **Eliminar**.

    ![Seleccione la búsqueda y, a continuación, haga clic en Eliminar en la página de control flotante.](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)

### <a name="auditing-the-data-spillage-investigation-process"></a>Auditoría del proceso de investigación del derrame de datos

Puede buscar en el registro de auditoría las actividades de exhibición de documentos electrónicos que se realizaron durante la investigación. También puede buscar en el registro de auditoría para devolver los registros de auditoría del comando **New-ComplianceSearchAction -Purge** que ejecutó en el paso 7 para eliminar los datos derramados. Para más información, vea:

- [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md)

- [Buscar actividades de eDiscovery en el registro de auditoría](search-for-ediscovery-activities-in-the-audit-log.md)
