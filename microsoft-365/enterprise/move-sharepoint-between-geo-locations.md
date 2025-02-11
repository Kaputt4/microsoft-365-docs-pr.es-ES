---
title: 'Mover un sitio SharePoint a otra ubicación geográfica '
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo mover un sitio de SharePoint a otra ubicación geográfica dentro del entorno multigeográfico y comunicar las expectativas de los cambios a los usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1a9787887f34d89faf87dbe20984c39762f3b9f
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68536904"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Mover un sitio SharePoint a otra ubicación geográfica 

Con el movimiento geográfico de sitios de SharePoint, puede mover dichos sitios a otras ubicaciones geográficas dentro de su entorno multigeográfico. 

Los siguientes tipos de sitios pueden moverse entre ubicaciones geográficas:

- Sitios conectados a grupos de Microsoft 365, incluidos los sitios asociados a Microsoft Teams
- Sitios modernos sin una asociación de grupo de Microsoft 365
- Sitios clásicos de SharePoint
- Sitios de comunicación

Debe ser un administrador global o un administrador de SharePoint para mover un sitio entre ubicaciones geográficas.

Hay una ventana de solo lectura durante el movimiento geográfico del sitio de SharePoint de aproximadamente 4-6 horas, dependiendo del contenido del sitio.

## <a name="best-practices"></a>Procedimientos recomendados

- Pruebe un movimiento del sitio de SharePoint en un sitio de prueba para familiarizarse con el procedimiento.
- Compruebe si el sitio se puede mover antes de programar o realizar el cambio.
- Cuando sea posible, programe movimientos de sitios entre ubicaciones geográficas fuera del horario laboral para reducir el impacto con el usuario.
- Comuníquese con los usuarios afectados antes del movimiento de sitios.

## <a name="communicating-to-your-users"></a>Comunicación con los usuarios

Es importante comunicar el resultado esperado a los usuarios de los sitios (generalmente los que pueden editarlos), al migrar los sitios de SharePoint entre ubicaciones geográficas. Esto puede ayudar a reducir la confusión de los usuarios y las llamadas a su departamento de soporte técnico. Envíe un correo a los usuarios antes de mover los sitios e infórmeles de lo siguiente:

- Cuándo se espera que inicie el movimiento y cuánto tiempo se espera que tarde en completarse.
- La ubicación geográfica de destino para el sitio y la dirección URL para obtener acceso a la nueva ubicación.
- Necesitan cerrar sus archivos sin realizar ediciones durante el desplazamiento.
- Los permisos de archivo y el uso compartido no cambiará como resultado del movimiento.
- Acciones previstas de la experiencia del usuario en un entorno multigeográfico

Asegúrese de enviar a los usuarios un correo electrónico cuando se complete correctamente el movimiento para informarles de que pueden reanudar su trabajo en los sitios.

## <a name="scheduling-sharepoint-site-moves"></a>Programación de movimientos de sitios de SharePoint 

Puede programar los movimientos de sitios de SharePoint por adelantado (como se describe más adelante en este artículo). Puede programar los movimientos como sigue:

- Puede programar un máximo de 4000 movimientos cada vez.
- Al empezar el movimiento, puede programar más, con un máximo de 4000 movimientos pendientes en la cola y en cualquier momento.
- El tamaño máximo de un sitio de SharePoint que se puede mover es de 1 terabyte (1 TB).

Para programar un movimiento geográfico de sitio de SharePoint para un momento posterior, incluya uno de los parámetros siguiente al iniciar:

- `PreferredMoveBeginDate`: Es probable que se inicie el cambio en este momento especificado.
- `PreferredMoveEndDate`: Es probable que se complete el movimiento dentro de este tiempo especificado, en el mejor de los casos.

La hora para ambos parámetros debe especificarse según el Tiempo universal coordinado (UTC).

## <a name="moving-the-site"></a>Mover el sitio

El movimiento geográfico del sitio de SharePoint requiere que se conecte y se realice desde la URL del administrador de SharePoint en la ubicación geográfica donde se encuentra el sitio.

Por ejemplo, si la dirección URL del sitio es `https://contosohealthcare.sharepoint.com/sites/Turbines`, conéctese a la dirección URL Administración de SharePoint en `https://contosohealthcare-admin.sharepoint.com`:

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![Ventana del Shell de administración de SharePoint Online que muestra el comando Connect-SPOService.](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>Validación del entorno

Se recomienda realizar una comprobación para asegurarse de que se puede mover el sitio, antes de programar su movimiento.

No se admite mover sitios con:

- Servicios de conectividad empresarial
- Formularios de InfoPath
- Se aplicaron las plantillas de Information Rights Management (IRM)

Para asegurarse de que todas las ubicaciones geográficas son compatibles, ejecute `Get-SPOGeoMoveCrossCompatibilityStatus`. Esto mostrará todas las ubicaciones geográficas y si el entorno es compatible con la ubicación geográfica de destino. Si una ubicación geográfica no es compatible, significa que hay una actualización en curso en esa ubicación. Inténtelo de nuevo en unos días.

Para realizar una comprobación de validación en el sitio, use `Start-SPOSiteContentMove` con el parámetro `-ValidationOnly` para comprobar si el sitio se puede mover. Por ejemplo:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Esto devolverá *Success* si el sitio está listo para moverse o *Fail* si hay algunas condiciones bloqueadas.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Inicio de un movimiento geográfico del sitio de SharePoint para un sitio sin grupo de Microsoft 365 asociado

De forma predeterminada, se cambiará la dirección URL inicial del sitio a la dirección URL de la ubicación geográfica de destino. Por ejemplo:

`https://Contoso.sharepoint.com/sites/projectx` a `https://ContosoEUR.sharepoint.com/sites/projectx`

En el caso de sitios sin asociación de grupos de Microsoft 365, también puede cambiar el nombre del sitio mediante el `-DestinationUrl` parámetro . Por ejemplo:

<https://Contoso.sharepoint.com/sites/projectx> a `https://ContosoEUR.sharepoint.com/sites/projecty`

Para iniciar el movimiento del sitio, ejecute:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Captura de pantalla de la ventana de PowerShell que muestra Start-SPOSiteContentMove cmdlet.](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Inicio de un traslado geográfico del sitio de SharePoint para un sitio conectado a un grupo de Microsoft 365

Para mover un sitio conectado a un grupo de Microsoft 365, el administrador global o el administrador de SharePoint primero deben cambiar el atributo Ubicación de datos preferida (PDL) para el grupo de Microsoft 365.

Para establecer la PDL para un grupo de Microsoft 365:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

Una vez que haya actualizado la PDL, puede iniciar el movimiento del sitio:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Cancelar un movimiento geográfico de sitios de SharePoint

Puede detener un movimiento geográfico de sitios de SharePoint, siempre que el movimiento no esté en curso ni se haya finalizado, mediante el cmdlet `Stop-SPOSiteContentMove`.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>Determinar el estado de un movimiento geográfico de sitios de SharePoint

Puede determinar el estado de un movimiento de sitios dentro y fuera de la ubicación geográfica a la que está conectado mediante los siguientes cmdlet:

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (sitios no conectados al grupo)
- [Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (sitios conectados a grupos)

Use el parámetro `-SourceSiteUrl` para especificar el sitio del que quiere ver el estado del movimiento.

Los estados del movimiento se describen en la tabla siguiente.

****

|Estado|Descripción|
|---|---|
|Ready to Trigger|No se ha iniciado el movimiento.|
|Scheduled|El movimiento está en cola, pero todavía no se ha iniciado.|
|InProgress (n/4)|El movimiento está en curso en uno de los siguientes estados: Validación (1/4), Copia de seguridad (2/4), Restauración (3/4), Limpieza (4/4).|
|Success|El movimiento se completó correctamente.|
|Failed|No se pudo realizar el movimiento.|
|

También puede aplicar la opción `-Verbose` para ver información adicional sobre el movimiento.

## <a name="user-experience"></a>Experiencia del usuario

Los usuarios del sitio deben notar una interrupción mínima al mover su sitio a otra ubicación geográfica. Excepto un estado breve de solo lectura durante el movimiento, los permisos y los vínculos existentes seguirán funcionando como se espera una vez completado el proceso.

### <a name="site"></a>Sitio

Mientras el movimiento está en curso, el sitio se establece en solo lectura. Una vez completado el movimiento, se dirige al usuario al sitio nuevo en la nueva ubicación geográfica al hacer clic en los marcadores u en otros vínculos del sitio.

### <a name="permissions"></a>Permisos

Los usuarios con permisos al sitio seguirán teniendo acceso durante el movimiento y después de su finalización.

### <a name="sync-app"></a>Aplicación de sincronización

La aplicación de sincronización detectará automáticamente y transferirá sin problemas la sincronización a la nueva ubicación del sitio una vez que se complete el traslado del sitio. El usuario no necesitará volver a iniciar sesión ni realizar ninguna otra acción. (Versión 17.3.6943.0625 o posterior de la aplicación de sincronización necesaria).

Si un usuario actualiza un archivo mientras el movimiento está en curso, la aplicación de sincronización le notificará que las cargas de archivos están pendientes mientras el movimiento está en curso.

### <a name="sharing-links"></a>Vínculos de uso compartido

Tras la finalización del movimiento geográfico de sitios de SharePoint, los vínculos compartidos existentes de los archivos que se movieron se redirigirán automáticamente a la nueva ubicación geográfica.

### <a name="most-recently-used-files-in-office-mru"></a>Los archivos usados recientemente de Office (MRU)

El servicio MRU se actualiza con la dirección URL del sitio y sus direcciones URL de contenido cuando se complete el movimiento. Eso se aplica a Word, Excel y PowerPoint

### <a name="onenote-experience"></a>Experiencia de OneNote

El cliente de win32 de OneNote y la aplicación UWP (Universal) detectarán automáticamente y sincronizarán perfectamente blocs de notas con la nueva ubicación del sitio cuando se complete el movimiento. El usuario no necesitará volver a iniciar sesión ni realizar ninguna otra acción. El único indicador visible para el usuario es que la sincronización de la notebook fallaría cuando el movimiento del sitio esté en curso. Esta experiencia está disponible en las siguientes versiones de cliente de OneNote:

- OneNote win32. versión 16.0.8326.2096 (y versiones posteriores)
- OneNote UWP: versión 16.0.8431.1006 (y versiones posteriores)
- Aplicación móvil de OneNote (versión 16.0.8431.1011 y versiones posteriores)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (aplicable a sitios conectados a grupos de Microsoft 365)

Cuando se complete el traslado geográfico del sitio de SharePoint, los usuarios tendrán acceso a sus archivos de sitio de grupo de Microsoft 365 en la aplicación Teams. Además, los archivos compartidos mediante chat de Teams desde el sitio, antes del movimiento geográfico, seguirán funcionando tras completar el mismo.

El traslado geográfico del sitio de SharePoint no admite el traslado de canales privados de una ubicación geográfica a otra. Los canales privados permanecen en la ubicación geográfica original.
  

### <a name="sharepoint-mobile-app-iosandroid"></a>Aplicación móvil de SharePoint para Android y iOS

Se admite la aplicación móvil de SharePoint entre las zonas geográficas y podrá detectar la nueva ubicación geográfica del sitio.

### <a name="sharepoint-workflows"></a>Flujos de trabajo de SharePoint

Los flujos de trabajo de SharePoint 2013 deben volver a publicarse después del traslado del sitio. Los flujos de trabajo de SharePoint 2010 deberían seguir funcionando con normalidad.

### <a name="apps"></a>Aplicaciones

Si va a mover un sitio con aplicaciones, debe restablecer la aplicación en la nueva ubicación geográfica del sitio, ya que es posible que la aplicación y sus conexiones no estén disponibles en la ubicación geográfica de destino.

### <a name="power-automate"></a>Power Automate

En la mayoría de los casos, los flujos de Power Automate seguirán funcionando después de un movimiento geográfico del sitio de SharePoint. Se recomienda probarlos una vez completado el movimiento.

### <a name="power-apps"></a>Power Apps

Power Apps debe volver a crearse en la ubicación de destino.

### <a name="data-movement-between-geo-locations"></a>Mover datos entre ubicaciones geográficas

SharePoint usa Azure Blob Storage para su contenido, mientras que los metadatos asociados a sitios y sus archivos se almacenan en SharePoint. Cuando el sitio se mueve de su ubicación geográfica de origen a la de destino, el servicio también moverá el Blob Storage asociado.  El movimiento de Blob Storage se completa en aproximadamente 40 días. Esto no afectará a la interacción de los usuarios con los datos. 

Puede comprobar el estado de movimiento de Blob Storage mediante el cmdlet [Get-SPOCrossGeoMoveReport](/powershell/module/sharepoint-online/get-spocrossgeomovereport) . 
