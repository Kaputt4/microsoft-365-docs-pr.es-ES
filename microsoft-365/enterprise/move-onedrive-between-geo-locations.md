---
title: Mover un sitio de OneDrive a otra ubicación geográfica
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Busque información sobre cómo mover un sitio de OneDrive a otra ubicación geográfica, incluida la programación de movimientos del sitio y la comunicación de expectativas a los usuarios.
ms.openlocfilehash: bafe97fd1dc049b1a9fbb0bdcc2d9d1660baead4
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68536552"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>Mover un sitio de OneDrive a otra ubicación geográfica

Con el movimiento geográfico de OneDrive, puede mover onedrive de un usuario a otra ubicación geográfica. El movimiento geográfico de OneDrive lo realiza el administrador de SharePoint Online o el administrador global de Microsoft 365. Antes de iniciar un movimiento geográfico de OneDrive, asegúrese de notificar al usuario cuyo OneDrive se está moviendo y recomendar que cierre todos los archivos durante el traslado. (Si el usuario tiene un documento abierto con el cliente de Office durante el traslado, al finalizar el movimiento, el documento deberá guardarse en la nueva ubicación). El traslado se puede programar para un momento futuro, si lo desea.

El servicio OneDrive usa Azure Blob Storage para almacenar contenido. El blob de Storage asociado al OneDrive del usuario se moverá de la ubicación geográfica de origen a destino en un plazo de 40 días después de que OneDrive de destino esté disponible para el usuario. El acceso a OneDrive del usuario se restaurará en cuanto onedrive de destino esté disponible.

Durante la ventana de movimiento geográfico de OneDrive (aproximadamente 2-6 horas), OneDrive del usuario está establecido en solo lectura. El usuario todavía puede acceder a sus archivos a través de la aplicación Sincronización de OneDrive o su sitio de OneDrive en SharePoint Online. Una vez completado el movimiento geográfico de OneDrive, el usuario se conectará automáticamente a su OneDrive en la ubicación geográfica de destino cuando navegue a OneDrive en el iniciador de aplicaciones de Microsoft 365. La aplicación de sincronización comenzará automáticamente la sincronización desde la nueva ubicación.

Los procedimientos descritos en este artículo necesitan el [Módulo de PowerShell de Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).

## <a name="communicating-to-your-users"></a>Comunicación con los usuarios

When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect. This can help reduce user confusion and calls to your help desk. Email your users before the move and let them know the following information:

- Cuándo se espera que se inicie la migración y cuánto tiempo se espera que tarde en completarse.
- La ubicación geográfica de destino para su cuenta de OneDrive y la dirección URL para obtener acceso a la nueva ubicación.
- Necesitan cerrar sus archivos y no realizar ediciones durante la migración.
- El uso compartido de los permisos de archivos no cambiará como resultado de la migración.
- Acciones previstas de la [experiencia del usuario en un entorno multigeográfico](multi-geo-user-experience.md)

Asegúrese de enviar a los usuarios un correo electrónico cuando se complete correctamente la migración para informarles de que pueden reanudar su trabajo en OneDrive.

## <a name="scheduling-onedrive-site-moves"></a>Programar movimientos de un sitio de OneDrive

You can schedule OneDrive site moves in advance (described later in this article). We recommend that you start with a small number of users to validate your workflows and communication strategies. Once you are comfortable with the process, you can schedule moves as follows:

- Puede programar un máximo de 4000 movimientos cada vez.
- Al empezar el movimiento, puede programar más, con un máximo de 4000 movimientos pendientes en la cola y en cualquier momento.
- El tamaño máximo de un OneDrive que se puede mover es 1 terabyte (1 TB).

## <a name="moving-a-onedrive-site"></a>Mover un sitio de OneDrive

Para realizar un movimiento geográfico de OneDrive, el administrador de inquilinos debe establecer primero la ubicación de datos preferida (PDL) del usuario en la ubicación geográfica adecuada. Una vez establecida la PDL, espere al menos 24 horas a que la actualización pdl se sincronice entre las ubicaciones geográficas antes de iniciar el movimiento geográfico de OneDrive.

Al usar los cmdlets de movimiento geográfico, conéctese al servicio SPO en la ubicación geográfica de OneDrive actual del usuario, con la sintaxis siguiente:

```powershell
Connect-SPOService -url https://<tenantName>-admin.sharepoint.com
```

Por ejemplo: para mover OneDrive del usuario "Matt@contosoenergy.onmicrosoft.com", conéctese al centro de Administración de Eur SharePoint, ya que OneDrive del usuario está en ubicación geográfica EUR:

```powershell
Connect-SPOService -url https://contosoenergyeur-admin.sharepoint.com
```

![Captura de pantalla de la ventana de PowerShell que muestra el cmdlet connect-sposervice.](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>Validación del entorno

Antes de iniciar la transferencia geográfica de OneDrive, se recomienda validar el entorno.

Para asegurarse de que todas las ubicaciones geográficas son compatibles, ejecute:

```powershell
Get-SPOGeoMoveCrossCompatibilityStatus
```

Esto mostrará todas las ubicaciones geográficas y si el entorno es compatible con la ubicación geográfica de destino. Si una ubicación geográfica no es compatible, significa que hay una actualización en curso en esa ubicación. Inténtelo de nuevo en unos días.

Si una instancia OneDrive contiene un subsitio, por ejemplo, no puede moverse. Puede usar el cmdlet Start-SPOUserAndContentMove cmdlet con el parámetro -ValidationOnly para validar si la instancia de OneDrive puede moverse:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly
```

This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move. Once you have validated that the OneDrive is ready to move, you can start the move.

## <a name="start-a-onedrive-geo-move"></a>Iniciar una transferencia geográfica de OneDrive

Para iniciar el movimiento, ejecute:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>
```

Con estos parámetros:

- _UserPrincipalName_: UPN del usuario cuya instancia de OneDrive se va a mover.
- _DestinationDataLocation_ : Geo-Location donde se debe mover OneDrive. Debe ser igual que la ubicación de datos preferida del usuario.

Por ejemplo, para mover la instancia de OneDrive de matt@contosoenergy.onmicrosoft.com de EUR a AUS, ejecute:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS
```

![Captura de pantalla de la ventana de PowerShell que muestra Start-SPOUserAndContentMove cmdlet.](../media/move-onedrive-between-geo-locations-image2.png)

Para programar una transferencia geográfica para más adelante, use uno de los parámetros siguientes:

- _PreferredMoveBeginDate_ – The move will likely begin at this specified time. Time must be specified in Coordinated Universal Time (UTC).
- _PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis. Time must be specified in Coordinated Universal Time (UTC).

## <a name="cancel-a-onedrive-geo-move"></a>Cancelar una transferencia geográfica de OneDrive

Puede detener el movimiento geográfico de OneDrive de un usuario, siempre que el movimiento no esté en curso o se complete mediante el cmdlet :

```powershell
Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>
```

Donde _UserPrincipalName_ es el UPN del usuario cuyo movimiento de OneDrive se quiere detener.

## <a name="determining-current-status"></a>Determinación del estado actual

Puede comprobar el estado de un movimiento geográfico de OneDrive dentro o fuera de la ubicación geográfica a la que está conectado mediante el cmdlet Get-SPOUserAndContentMoveState.

Los estados del movimiento se describen en la tabla siguiente.

|Estado|Descripción|
|---|---|
|NotStarted|El movimiento no se ha iniciado|
|InProgress (*n*/4)|El movimiento está en curso en uno de los siguientes estados: <ul><li>Validación (1/4)</li><li>Copia de seguridad (2/4)</li><li>Restauración (3/4)</li><li>Limpieza (4/4)</li></ul>|
|Success|El movimiento se completó correctamente.|
|Failed|No se pudo realizar el movimiento.|

Para buscar el estado del movimiento de un usuario específico, use el parámetro *UserPrincipalName* :

```powershell
Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>
```

Para encontrar el estado de todos los movimientos dentro o fuera de la ubicación geográfica a la que está conectado, use el parámetro *MoveState* con uno de los siguientes valores: NotStarted, InProgress, Success, Failed, All.

```powershell
Get-SPOUserAndContentMoveState -MoveState <value>
```

También puede agregar el parámetro *Verbose* para obtener descripciones más detalladas del estado de movimiento.

## <a name="user-experience"></a>Experiencia del usuario

Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location. Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.

### <a name="users-onedrive"></a>OneDrive del usuario

Mientras el movimiento está en curso, onedrive del usuario está establecido en solo lectura. Una vez completado el movimiento, el usuario se dirige a su OneDrive en la nueva ubicación geográfica cuando navega a OneDrive el iniciador de aplicaciones de Microsoft 365 o un explorador web.

### <a name="permissions-on-onedrive-content"></a>Permisos en contenido de OneDrive

Los usuarios con permisos para el contenido de OneDrive seguirán teniendo acceso al contenido durante el traslado y una vez completado.

### <a name="onedrive-sync-app"></a>Sincronización de OneDrive aplicación

La aplicación Sincronización de OneDrive detectará automáticamente y transferirá sin problemas la sincronización a la nueva ubicación de OneDrive una vez que se complete el movimiento geográfico de OneDrive. El usuario no necesita volver a iniciar sesión ni realizar ninguna otra acción.  (Versión 17.3.6943.0625 o posterior de la aplicación de sincronización necesaria).

Si un usuario actualiza un archivo mientras el movimiento geográfico de OneDrive está en curso, la aplicación de sincronización le notificará que las cargas de archivos están pendientes mientras el movimiento está en curso.

### <a name="sharing-links"></a>Vínculos de uso compartido

Tras la finalización de la transferencia geográfica de OneDrive, los vínculos compartidos existentes a los archivos que se movieron se redirigirán automáticamente a la nueva ubicación geográfica.

### <a name="onenote-experience"></a>Experiencia de OneNote

OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete. The user does not need to sign-in again or take any other action. The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress. This experience is available on the following OneNote client versions:

- OneNote win32. versión 16.0.8326.2096 (y versiones posteriores)
- OneNote UWP: versión 16.0.8431.1006 (y versiones posteriores)
- Aplicación móvil de OneNote (versión 16.0.8431.1011 y versiones posteriores)

### <a name="teams-app"></a>Aplicación de Teams

Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app. Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.

### <a name="onedrive-mobile-app-ios"></a>Aplicación móvil de OneDrive (iOS)

Tras la finalización de la transferencia geográfica de OneDrive, el usuario tendría que cerrar sesión e iniciarla de nuevo en la aplicación para dispositivos móviles iOS a fin de sincronizarla con la nueva ubicación de OneDrive.

### <a name="existing-followed-groups-and-sites"></a>Sitios y grupos seguidos existentes

Los sitios y grupos seguidos se mostrarán en OneDrive del usuario independientemente de su ubicación geográfica. Los sitios y grupos hospedados en otra ubicación geográfica se abrirán en una pestaña independiente.

### <a name="delve-geo-url-updates"></a>Actualizaciones de la dirección URL geográfica de Delve

Los usuarios se enviarán a la geoárea de Delve correspondiente a su PDL solo después de que su OneDrive se haya movido a la nueva ubicación geográfica.
