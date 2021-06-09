---
title: Mover un sitio de OneDrive a otra ubicación geográfica
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Encuentre información sobre cómo mover un sitio OneDrive a una ubicación geográfica diferente, incluido cómo programar los movimientos del sitio y comunicar las expectativas a los usuarios.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693601"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>Mover un sitio de OneDrive a otra ubicación geográfica 

Con OneDrive geo move, puede mover la ubicación de un usuario OneDrive a una ubicación geográfica diferente. OneDrive el administrador de SharePoint online o el Microsoft 365 global realizan el movimiento geográfico. Antes de iniciar un OneDrive geo move, asegúrese de notificar al usuario cuya OneDrive se está desplazando y recomiende que cierren todos los archivos durante el movimiento. (Si el usuario tiene un documento abierto mediante el cliente Office durante el movimiento, al finalizar el movimiento, el documento tendrá que guardarse en la nueva ubicación). El movimiento se puede programar para una hora futura, si se desea.

El OneDrive usa Azure Blob Storage para almacenar contenido. El blob Storage asociado con el OneDrive del usuario se moverá del origen a la ubicación geográfica de destino en un plazo de 40 días después de que el OneDrive esté disponible para el usuario. El acceso a la cuenta del OneDrive se restaurará tan pronto como el destino OneDrive esté disponible.

Durante el período de transferencia geográfica de OneDrive (de 2 a 6 horas), el usuario de OneDrive se establece en solo lectura. Todavía tiene acceso a sus archivos mediante el cliente de sincronización de OneDrive o en su sitio de OneDrive en SharePoint Online. Al finalizar la transferencia geográfica de OneDrive, el usuario se conectará automáticamente a su OneDrive en la ubicación geográfica de destino cuando navegue a OneDrive en el iniciador de aplicaciones de Microsoft 365. El cliente de sincronización iniciará automáticamente la sincronización desde la nueva ubicación.

Los procedimientos descritos en este artículo necesitan el [Módulo de PowerShell de Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).

## <a name="communicating-to-your-users"></a>Comunicación con los usuarios

Al mover sitios de OneDrive entre ubicaciones geográficas, es importante comunicar a los usuarios lo que pueden esperar que ocurra. Esto permitirá reducir la confusión de los usuarios y las llamadas al departamento de soporte técnico. Envíe un correo electrónico a los usuarios antes de la migración y proporcióneles la información siguiente:

- Cuándo se espera que se inicie la migración y cuánto tiempo se espera que tarde en completarse.
- La ubicación geográfica de destino para su cuenta de OneDrive y la dirección URL para obtener acceso a la nueva ubicación.
- Necesitan cerrar sus archivos y no realizar ediciones durante la migración.
- El uso compartido de los permisos de archivos no cambiará como resultado de la migración.
- Acciones previstas de la [experiencia del usuario en un entorno multigeográfico](multi-geo-user-experience.md)

Asegúrese de enviar a los usuarios un correo electrónico cuando se complete correctamente la migración para informarles de que pueden reanudar su trabajo en OneDrive.

## <a name="scheduling-onedrive-site-moves"></a>Programar movimientos de un sitio de OneDrive

Puede programar de antemano los movimientos del sitio de OneDrive (tal como se describe más adelante en este artículo). Le recomendamos que empiece por un número pequeño de usuarios para validar los flujos de trabajo y las estrategias de comunicación. Una vez que esté familiarizado con el proceso, puede programar movimientos de la siguiente manera:

- Puede programar un máximo de 4000 movimientos cada vez.
- Al empezar el movimiento, puede programar más, con un máximo de 4000 movimientos pendientes en la cola y en cualquier momento.
- El tamaño máximo de un OneDrive que se puede mover es 1 terabyte (1 TB).

## <a name="moving-a-onedrive-site"></a>Mover un sitio de OneDrive

Para realizar un OneDrive geo move, el administrador de inquilinos primero debe establecer la ubicación de datos preferida (PDL) del usuario en la ubicación geográfica adecuada. Una vez establecida la PDL, espere al menos 24 horas para que la actualización de PDL se sincronice en las ubicaciones geográficas antes de iniciar OneDrive movimiento geográfico.

Al usar los cmdlets de movimiento geográfico, conéctese al servicio SPO en la ubicación geográfica actual del OneDrive usuario, con la siguiente sintaxis:

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

Por ejemplo: para mover OneDrive de usuario "Matt@contosoenergy.onmicrosoft.com", conéctese al Centro de administración de EUR SharePoint ya que la ubicación OneDrive del usuario se encuentra en la ubicación geográfica eur:

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Captura de pantalla de la ventana de PowerShell que muestra el cmdlet connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>Validación del entorno

Antes de iniciar la transferencia geográfica de OneDrive, se recomienda validar el entorno.

Para asegurarse de que todas las ubicaciones geográficas son compatibles, ejecute:

`Get-SPOGeoMoveCrossCompatibilityStatus`

Verá una lista de las ubicaciones geográficas y si se puede mover el contenido entre ellas se indicará como "Compatible". Si el comando devuelve "Incompatible" vuelva a intentar validar el estado más tarde.

Si una instancia OneDrive contiene un subsitio, por ejemplo, no puede moverse. Puede usar el cmdlet Start-SPOUserAndContentMove cmdlet con el parámetro -ValidationOnly para validar si la instancia de OneDrive puede moverse:

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

Se devolverá Success si OneDrive está listo para moverse o Fail si hay una suspensión legal o un subsitio que impida el movimiento. Cuando haya validado que OneDrive está listo para moverse, puede iniciar el movimiento.

## <a name="start-a-onedrive-geo-move"></a>Iniciar una transferencia geográfica de OneDrive

Para iniciar el movimiento, ejecute:  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

Con estos parámetros:

-   _UserPrincipalName_: UPN del usuario cuya instancia de OneDrive se va a mover.

-   _DestinationDataLocation:_ Geo-Location donde se OneDrive se debe mover el objeto. Esto debe ser igual que la ubicación de datos preferida del usuario.

Por ejemplo, para mover la instancia de OneDrive de matt@contosoenergy.onmicrosoft.com de EUR a AUS, ejecute:

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Captura de pantalla de la ventana de PowerShell que muestra el cmdlet Start-SPOUserAndContentMove](../media/move-onedrive-between-geo-locations-image2.png)

Para programar una transferencia geográfica para más adelante, use uno de los parámetros siguientes:

-   _PreferredMoveBeginDate_: es probable que el movimiento se inicie a la hora especificada. La hora debe especificarse en la hora universal coordinada (UTC).

-   _PreferredMoveEndDate_: es probable que el movimiento finalice antes de la hora especificada, sin garantía. La hora debe especificarse en la hora universal coordinada (UTC). 

## <a name="cancel-a-onedrive-geo-move"></a>Cancelar una transferencia geográfica de OneDrive 

Puede detener el movimiento geográfico de la OneDrive de un usuario, siempre que el movimiento no esté en curso o completado mediante el cmdlet:

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

Donde _UserPrincipalName_ es el UPN del usuario cuyo movimiento de OneDrive se quiere detener.

## <a name="determining-current-status"></a>Determinación del estado actual

Puede comprobar el estado de un OneDrive de movimiento geográfico dentro o fuera de la geo a la que está conectado mediante el cmdlet Get-SPOUserAndContentMoveState.

Los estados del movimiento se describen en la tabla siguiente.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Estado</strong></th>
<th align="left"><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">No se ha iniciado el movimiento.</td>
</tr>
<tr class="even">
<td align="left">InProgress (<em>n</em>/4)</td>
<td align="left">El movimiento está en curso en uno de los siguientes estados: validación (1/4), copia de seguridad (2/4), restauración (3/4), limpieza (4/4).</td>
</tr>
<tr class="odd">
<td align="left">Success</td>
<td align="left">El movimiento se completó correctamente.</td>
</tr>
<tr class="even">
<td align="left">Failed</td>
<td align="left">No se pudo realizar el movimiento.</td>
</tr>
</tbody>
</table>

Para buscar el estado del movimiento de un usuario específico, use el parámetro UserPrincipalName:

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

Para encontrar el estado de todos los movimientos dentro o fuera de la ubicación geográfica a la que está conectado, use el parámetro MoveState con uno de los siguientes valores: NotStarted, InProgress, Success, Failed, All.

`Get-SPOUserAndContentMoveState -MoveState <value>`

También puede agregar el parámetro `-Verbose` para obtener una descripción más detallada del estado del movimiento.

## <a name="user-experience"></a>Experiencia del usuario

Los usuarios de OneDrive no deberían advertir ninguna interrupción si su instancia de OneDrive se mueve a otra ubicación geográfica. Excepto un breve estado de solo lectura durante el cambio, los vínculos y permisos existentes seguirán funcionando como se espera una vez completado el movimiento.

### <a name="onedrive-for-business"></a>OneDrive para la Empresa

Mientras el movimiento está en curso, el OneDrive usuario se establece en solo lectura. Una vez completado el movimiento, el usuario se dirige a su OneDrive en la nueva ubicación geográfica cuando navega a OneDrive el iniciador de aplicaciones Microsoft 365 o un explorador web.

### <a name="permissions-on-onedrive-content"></a>Permisos en contenido de OneDrive

Los usuarios con permisos para OneDrive contenido seguirán teniendo acceso al contenido durante el movimiento y después de que se complete.

### <a name="onedrive-sync-client"></a>Cliente de sincronización de OneDrive 

El cliente de sincronización de OneDrive detectará automáticamente la sincronización y la transferirá de forma fluida a la nueva ubicación de OneDrive cuando se haya completado el movimiento geográfico de OneDrive. El usuario no tiene que volver a iniciar la sesión ni realizar ninguna otra acción. (Se necesita la versión 17.3.6943.0625 o posteriores del cliente de sincronización).

Si un usuario actualiza un archivo mientras el movimiento geográfico de OneDrive está en curso, el cliente de sincronización le notificará que hay cargas de archivos pendientes mientras el movimiento está en curso.

### <a name="sharing-links"></a>Vínculos de uso compartido 

Tras la finalización de la transferencia geográfica de OneDrive, los vínculos compartidos existentes a los archivos que se movieron se redirigirán automáticamente a la nueva ubicación geográfica.

### <a name="onenote-experience"></a>Experiencia de OneNote 

El cliente OneNote win32 y la aplicación UWP (Universal) detectarán automáticamente los blocs de notas y los sincronizarán perfectamente con la nueva ubicación de OneDrive cuando se haya completado la transferencia geográfica de OneDrive. El usuario no tiene que volver a iniciar sesión ni realizar ninguna otra acción. El único indicador visible para el usuario sería un error de sincronización de blocs de notas cuando la transferencia geográfica de OneDrive está en curso. Esta experiencia está disponible en las siguientes versiones de cliente OneNote:

-   OneNote win32. versión 16.0.8326.2096 (y versiones posteriores)

-   OneNote UWP: versión 16.0.8431.1006 (y versiones posteriores)

-   Aplicación móvil de OneNote (versión 16.0.8431.1011 y versiones posteriores)

### <a name="teams-app"></a>Aplicación de Teams

Tras la finalización de la transferencia geográfica de OneDrive, los usuarios tendrán acceso a sus archivos de OneDrive en la aplicación de Teams. Además, los archivos compartidos a través de chats de Teams desde su instancia de OneDrive anteriores a la transferencia geográfica seguirán funcionando tras completar el movimiento.

### <a name="onedrive-for-business-mobile-app-ios"></a>Aplicación móvil de OneDrive para la Empresa (iOS) 

Tras la finalización de la transferencia geográfica de OneDrive, el usuario tendría que cerrar sesión e iniciarla de nuevo en la aplicación para dispositivos móviles iOS a fin de sincronizarla con la nueva ubicación de OneDrive.

### <a name="existing-followed-groups-and-sites"></a>Sitios y grupos seguidos existentes

Los sitios y grupos seguidos se mostrarán en el sitio del OneDrive independientemente de su ubicación geográfica. Los sitios y grupos hospedados en otra ubicación geográfica se abrirán en una pestaña independiente.

### <a name="delve-geo-url-updates"></a>Delve Actualizaciones de direcciones URL geográficas

Los usuarios se enviarán a la Delve correspondiente a su PDL solo después de que su OneDrive se haya movido a la nueva ubicación geográfica.
