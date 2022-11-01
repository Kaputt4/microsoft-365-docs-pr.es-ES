---
title: Data Residency para SharePoint Online y OneDrive para la Empresa
description: Data Residency para SharePoint Online y OneDrive para la Empresa
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: b2ffb535ae34a2d5af836c14cd88dd295d7d574f
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806191"
---
# <a name="data-residency-for-sharepoint-online-and-onedrive-for-business"></a>Data Residency para SharePoint Online y OneDrive para la Empresa

## <a name="data-residency-commitments-available"></a>**Data Residency compromisos disponibles**

### <a name="product-terms"></a>Términos del producto

Condiciones necesarias:

- _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_, la Unión Europea o la Estados Unidos.

**Compromiso:**

_Para conocer el idioma actual, consulte los [Términos del producto de privacidad y seguridad](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) y vea la sección titulada "Ubicación de los datos del cliente en reposo para Core Online Services"._

### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción Data Residency avanzada válida para todos los usuarios del _inquilino_.
1. Los datos del cliente de la suscripción de SharePoint Online se aprovisionan en _Geografía de región local_ o _Geografía de región local expandida_.

**Compromiso:**

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#sharepoint-onlineonedrive-for-business) para conocer los datos específicos del cliente en reposo para SharePoint Online y OneDrive para la Empresa.

### <a name="multi-geo-add-on"></a>Complemento multigeográfica

Condiciones necesarias:

1. _Los inquilinos_ tienen una suscripción multigeográfica válida que cubre a todos los usuarios asignados a una _geografía satélite_.
1. El cliente debe tener una Enterprise Agreement activa.
1.El total de unidades multigeográficas adquiridas debe ser superior al 5 % del total de puestos elegibles en el _inquilino_.

**Compromiso:** Los clientes pueden asignar usuarios de SharePoint Online/OneDrive para la Empresa a cualquier _geografía satélite_ compatible con multigeográfica (consulte la sección 4.1.3). Los siguientes datos de cliente se almacenarán en el contenido de sitio _de Geografía satélite_: SharePoint Online correspondiente y los archivos almacenados en ese sitio, y los archivos cargados en OneDrive para la Empresa.  

## <a name="multi-geo-capabilities-in-sharepoint-online--onedrive-for-business"></a>**Funcionalidades multigeográficas en SharePoint Online/OneDrive para la Empresa**

Las funcionalidades multigeográficas de OneDrive y SharePoint Online permiten el control de recursos compartidos, como sitios de equipo de SharePoint y buzones de microsoft 365 group almacenados en reposo en una _región de macro_ geografía o _geografía de región local_ especificada.

Cada usuario, buzón de grupo y sitio de SharePoint tienen una ubicación de datos preferida (PDL) que indica la geografía de la _región de macro_ o _la geografía de la región local_ (ubicación donde se van a almacenar los datos relacionados). Los datos personales de los usuarios (buzón de Exchange y OneDrive) junto con cualquier Grupos de Microsoft 365 o sitios de SharePoint que creen se pueden almacenar en la ubicación de _geografía de la región de macro_ especificada o en _la ubicación geográfica de la región local_ para cumplir los requisitos de residencia de datos. Puede especificar administradores diferentes para cada ubicación _geográfica de región de macro_ o _región local_ .

Los usuarios obtienen una experiencia fluida al usar los servicios de Microsoft 365, incluidas las aplicaciones de Office, OneDrive y Search. Consulte Experiencia del usuario en un entorno multigeográfico para obtener más información.

### <a name="onedrive"></a>**OneDrive**

Un administrador puede aprovisionar o mover OneDrive de cada usuario a una ubicación _de geografía satélite_ de acuerdo con la PDL del usuario. A continuación, los archivos personales se conservan en esa ubicación _de Geografía satélite_ , aunque se pueden compartir con los usuarios de otras ubicaciones _geografía de la región de macros_ o _geografía de la región local_ .

### <a name="sharepoint-sites-and-groups"></a>**Sitios y grupos de SharePoint**
La administración de la característica multigeográfica está disponible en el Centro de administración de SharePoint.

Cuando un usuario crea un sitio conectado a un grupo de SharePoint en un entorno multigeográfico, su PDL se usa para determinar la ubicación _Geografía de la región de macro_ o _Geografía de la región local_ donde se crean el sitio y su buzón de grupo asociado. (Si el valor de PDL del usuario no se ha establecido o se ha establecido en Geografía de _región de macro_ o Ubicación _geográfica de región local_ que no se ha configurado como ubicación _de geografía satélite_ , el sitio y el buzón se crean en la _geografía aprovisionada principal_).

Los servicios de Microsoft 365 distintos de Exchange, OneDrive, SharePoint y Teams no están disponibles con multigeográfica. Sin embargo, Grupos de Microsoft 365 que crean estos servicios se configurarán con la PDL del creador y su buzón de correo del grupo de Exchange, el sitio de SharePoint se aprovisiona en la geografía de _la región de macro_ correspondiente o geografía _de la región local_ correspondiente.

### <a name="managing-the-multi-geo-environment"></a>**Administración del entorno multigeográfico**

La configuración y administración del entorno multigeográfico se realiza a través del Centro de administración de SharePoint.

#### <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>**Cuotas de almacenamiento de SharePoint en entornos multigeográficos**

De forma predeterminada, todas las ubicaciones _geography_ de un entorno multigeográfico comparten la cuota de almacenamiento de _inquilinos_ disponible.

Con la configuración de cuota de almacenamiento geográfico de SharePoint, puede administrar la cuota de almacenamiento para cada ubicación _geográfica_ . Al asignar una cuota de almacenamiento para una ubicación _geography_ , se convierte en la cantidad máxima de almacenamiento disponible para esa ubicación _geography_ y se deduce de la cuota de almacenamiento de _inquilino_ disponible. A continuación, la cuota de almacenamiento de _inquilino_ disponible restante se comparte entre las ubicaciones _geography_ configuradas para las que no se ha asignado una cuota de almacenamiento específica.

El administrador de SharePoint Online puede asignar la cuota de almacenamiento de SharePoint para cualquier ubicación _geográfica_ mediante la conexión a la _geografía aprovisionada principal_. _Los administradores de geografía_ de las ubicaciones _de geografía satélite_ pueden ver la cuota de almacenamiento, pero no pueden asignarla.

#### <a name="configure-a-storage-quota-for-a-_geography_-location"></a>**Configuración de una cuota de almacenamiento para una ubicación _geography_**

Use el [Shell de administración de Microsoft Office SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588) y conéctese a la ubicación _geografía aprovisionada principal_ para asignar la cuota de almacenamiento para una ubicación _geography_.

Para asignar la cuota de almacenamiento de una ubicación, ejecute el cmdlet:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

Para ver la cuota de almacenamiento de la ubicación _geography_ actual, ejecute:

```powershell
Get-SPOGeoStorageQuota
```

Para ver la cuota de almacenamiento para todas las ubicaciones _geography_ , ejecute:

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

Para quitar la cuota de almacenamiento asignada para una ubicación _geography_ , establezca `StorageQuota value = 0`:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```

### <a name="move-a-onedrive-site"></a>Mover un sitio de OneDrive

#### <a name="move-a-onedrive-site-to-a-different-_geography_-location"></a>Traslado de un sitio de OneDrive a otra ubicación _geográfica_

Con el traslado _de Geografía_ de OneDrive, puede mover onedrive de un usuario a otra ubicación _geográfica_ . El movimiento _geografía_ de OneDrive lo realiza el administrador de SharePoint Online o el administrador global de Microsoft 365. Antes de iniciar un movimiento _de Geografía_ de OneDrive, asegúrese de notificar al usuario cuyo OneDrive se está moviendo y recomendar que cierre todos los archivos durante el traslado. (Si el usuario tiene un documento abierto con el cliente de Office durante el traslado, al finalizar el movimiento, el documento deberá guardarse en la nueva ubicación). El traslado se puede programar para un momento futuro, si lo desea.

El servicio OneDrive usa Azure Blob Storage para almacenar contenido. El blob de Storage asociado al OneDrive del usuario se moverá de la ubicación de origen a _la ubicación geográfica_ de destino dentro de los 40 días posteriores a que OneDrive de destino esté disponible para el usuario. El acceso a OneDrive del usuario se restaurará en cuanto onedrive de destino esté disponible.

Durante la ventana de movimiento _de Geografía_ de OneDrive (aproximadamente 2-6 horas), OneDrive del usuario está establecido en solo lectura. El usuario todavía puede acceder a sus archivos a través de la aplicación Sincronización de OneDrive o su sitio de OneDrive en SharePoint Online. Una vez completado el traslado _de Geografía_ de OneDrive, el usuario se conectará automáticamente a su OneDrive en la ubicación _de geografía_ de destino cuando navegue a OneDrive en el iniciador de aplicaciones de Microsoft 365. La aplicación de sincronización comenzará automáticamente la sincronización desde la nueva ubicación.

Los procedimientos descritos en este artículo necesitan el [Módulo de PowerShell de Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).

#### <a name="communicating-to-your-users"></a>Comunicación con los usuarios

Al mover sitios de OneDrive entre ubicaciones _geography_ , es importante comunicar a los usuarios qué esperar. Esto puede ayudar a reducir la confusión de los usuarios y las llamadas a su departamento de soporte técnico. Email a los usuarios antes del traslado y hágales saber la siguiente información: -Cuando se espera que se inicie el movimiento y cuánto tiempo se espera que tome -a qué ubicación _geográfica_ se mueve su OneDrive, y la dirección URL para acceder a la nueva ubicación - Deben cerrar sus archivos y no realizar modificaciones durante el traslado.
-Los permisos de archivo y el uso compartido no cambiarán como resultado del movimiento.
-Qué esperar de la experiencia del usuario en un entorno multigeográfico

Asegúrese de enviar a los usuarios un correo electrónico cuando se complete correctamente la migración para informarles de que pueden reanudar su trabajo en OneDrive.

#### <a name="scheduling-onedrive-site-moves"></a>Programar movimientos de un sitio de OneDrive

Puede programar movimientos de sitio de OneDrive con antelación (se describe más adelante en este artículo). Se recomienda empezar con un pequeño número de usuarios para validar los flujos de trabajo y las estrategias de comunicación. Una vez que esté cómodo con el proceso, puede programar los movimientos de la siguiente manera: -Puede programar hasta 4000 movimientos a la vez.
-A medida que comienzan los movimientos, puede programar más, con un máximo de 4000 movimientos pendientes en la cola y en cualquier momento dado.
-El tamaño máximo de un OneDrive que se puede mover es de 1 terabyte (1 TB).

#### <a name="moving-a-onedrive-site"></a>**Mover un sitio de OneDrive**
Para realizar un movimiento _de Geografía_ de OneDrive, el administrador de _inquilinos_ primero debe establecer la ubicación de datos preferida (PDL) del usuario en la ubicación _geográfica_ adecuada. Una vez establecida la PDL, espere al menos 24 horas a que la actualización pdl se sincronice en las ubicaciones _de Geography_ antes de iniciar el movimiento _geografía_ de OneDrive.

Al usar los cmdlets _de movimiento geography_ , conéctese al servicio SPO en la ubicación de _Geografía_ de OneDrive actual del usuario, con la sintaxis siguiente:

```powershell
Connect-SPOService -url https://<tenantName>-admin.sharepoint.com
```

Por ejemplo: para mover OneDrive del usuario "Matt@contosoenergy.onmicrosoft.com", conéctese al centro de Administración de EUR SharePoint, ya que onedrive del usuario está en ubicación _geografía_ eur:

```powershell
Connect-SPOService -url https://contosoenergyeur-admin.sharepoint.com
```

#### <a name="validating-the-environment"></a>**Validación del entorno**
  
Antes de iniciar un movimiento _de Geografía_ de OneDrive, se recomienda validar el entorno.

Para asegurarse de que todas las ubicaciones _geography_ son compatibles, ejecute:

```powershell
Get-SPOGeoMoveCrossCompatibilityStatus
```

Verá una lista de las ubicaciones _de Geography_ y si el contenido se puede mover entre se denominará "Compatible". Si el comando devuelve "Incompatible" vuelva a intentar validar el estado más tarde.

Si una instancia OneDrive contiene un subsitio, por ejemplo, no puede moverse. Puede usar el cmdlet Start-SPOUserAndContentMove cmdlet con el parámetro -ValidationOnly para validar si la instancia de OneDrive puede moverse:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly
```

  This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move. Once you have validated that the OneDrive is ready to move, you can start the move.

#### <a name="start-a-onedrive-geo-move"></a>**Iniciar una transferencia geográfica de OneDrive**

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

Para programar un movimiento _de geografía_ para una hora posterior, use uno de los parámetros siguientes:

- _PreferredMoveBeginDate_ : es probable que el movimiento comience en este momento especificado. La hora debe especificarse en hora universal coordinada (UTC).
- _PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis. Time must be specified in Coordinated Universal Time (UTC).

#### <a name="cancel-a-onedrive-_geography_-move"></a>**Cancelación de un movimiento _de geografía de_ OneDrive**
  
Puede detener el movimiento _geography_ de OneDrive de un usuario, siempre que el movimiento no esté en curso o completado mediante el cmdlet :

```powershell
Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>
```

Donde _UserPrincipalName_ es el UPN del usuario cuyo movimiento de OneDrive se quiere detener.

#### <a name="determining-current-status"></a>**Determinación del estado actual**

Puede comprobar el estado de _un movimiento de_ Geografía de OneDrive dentro o fuera _de geography al_ que está conectado mediante el cmdlet Get-SPOUserAndContentMoveState.

Los estados del movimiento se describen en la tabla siguiente.

|Estado|Descripción|
|---|---|
|NotStarted|El movimiento no se ha iniciado|
|InProgress (_n_/4)|El movimiento está en curso en uno de los siguientes estados: <ul><li>Validación (1/4)</li><li>Copia de seguridad (2/4)</li><li>Restauración (3/4)</li><li>Limpieza (4/4)</li></ul>|
|Success|El movimiento se completó correctamente.|
|Failed|No se pudo realizar el movimiento.|

Para buscar el estado del movimiento de un usuario específico, use el parámetro _UserPrincipalName_ :

```powershell
Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>
```

Para encontrar el estado de todos los movimientos dentro o fuera de la ubicación _geography_ a la que está conectado, use el parámetro _MoveState_ con uno de los siguientes valores: NotStarted, InProgress, Success, Failed, All.

```powershell
Get-SPOUserAndContentMoveState -MoveState <value>
```

También puede agregar el parámetro _Verbose_ para obtener descripciones más detalladas del estado de movimiento.

#### <a name="user-experience"></a>**Experiencia del usuario**

Los usuarios de OneDrive deben observar una interrupción mínima si su OneDrive se mueve a una ubicación _geográfica_ diferente. Excepto un estado breve de solo lectura durante el movimiento, los permisos y los vínculos existentes seguirán funcionando como se espera una vez completado el proceso.

#### <a name="users-onedrive"></a>**OneDrive del usuario**

Mientras el movimiento está en curso, onedrive del usuario está establecido en solo lectura. Una vez completado el traslado, el usuario se dirige a su OneDrive en la nueva ubicación _geography_  cuando navega a OneDrive el iniciador de aplicaciones de Microsoft 365 o un explorador web.

#### <a name="permissions-on-onedrive-content"></a>**Permisos en contenido de OneDrive**

Los usuarios con permisos para el contenido de OneDrive seguirán teniendo acceso al contenido durante el traslado y una vez completado.

#### <a name="onedrive-sync-app"></a>**Sincronización de OneDrive aplicación**

La aplicación Sincronización de OneDrive detectará automáticamente y transferirá sin problemas la sincronización a la nueva ubicación de OneDrive una vez que se complete el movimiento _geografía_ de OneDrive. El usuario no necesita volver a iniciar sesión ni realizar ninguna otra acción. (Versión 17.3.6943.0625 o posterior de la aplicación de sincronización necesaria). Si un usuario actualiza un archivo mientras el movimiento _geografía_ de OneDrive está en curso, la aplicación de sincronización le notificará que las cargas de archivos están pendientes mientras el movimiento está en curso.

#### <a name="sharing-links"></a>**Vínculos para compartir**

Una vez completado el traslado _de Geografía_ de OneDrive, los vínculos compartidos existentes para los archivos que se han movido se redirigirán automáticamente a la nueva ubicación _geography_ .

#### <a name="onenote-experience"></a>**Experiencia de OneNote**

El cliente win32 de OneNote y la aplicación para UWP (universal) detectarán automáticamente y sincronizarán sin problemas cuadernos en la nueva ubicación de OneDrive una vez que se complete el traslado _de_ Geografía de OneDrive. El usuario no necesita volver a iniciar sesión ni realizar ninguna otra acción. El único indicador visible para el usuario es que la sincronización de cuadernos produciría un error cuando el movimiento _de Geografía_ de OneDrive está en curso. Esta experiencia está disponible en las siguientes versiones de cliente de OneNote:

- OneNote win32. versión 16.0.8326.2096 (y versiones posteriores)
- OneNote UWP: versión 16.0.8431.1006 (y versiones posteriores)
- Aplicación móvil de OneNote (versión 16.0.8431.1011 y versiones posteriores)

#### <a name="teams-app"></a>**Aplicación de Teams**

Una vez completada la migración _geográfica_ de OneDrive, los usuarios tendrán acceso a sus archivos de OneDrive en la aplicación Teams. Además, los archivos compartidos a través del chat de Teams desde su OneDrive antes del traslado de _Geography_ seguirán funcionando una vez completado el movimiento.

#### <a name="onedrive-mobile-app-ios"></a>**Aplicación móvil de OneDrive (iOS)**

Una vez completada la operación de traslado _de_ Geografía de OneDrive, el usuario tendría que cerrar sesión e iniciar sesión de nuevo en la aplicación móvil de iOS para sincronizarse con la nueva ubicación de OneDrive.

#### <a name="existing-followed-groups-and-sites"></a>**Sitios y grupos seguidos existentes**

Los sitios y grupos seguidos se mostrarán en OneDrive del usuario, independientemente de su ubicación _geográfica_ . Los sitios y grupos hospedados en otra ubicación _geography_ se abrirán en una pestaña independiente.

#### <a name="delve-geo-url-updates"></a>**Actualizaciones de la dirección URL geográfica de Delve**

Los usuarios se enviarán a La _geografía_ delve correspondiente a su PDL solo después de que su OneDrive se haya movido a la nueva _geografía_.

### <a name="move-a-sharepoint-site"></a>**Mover un sitio de SharePoint**
#### <a name="move-a-sharepoint-site-to-a-different-_geography_-location"></a>**Mover un sitio de SharePoint a otra ubicación _geográfica_**

Con el traslado _de geografía_ del sitio de SharePoint, puede mover sitios de SharePoint a otras ubicaciones _geográficas_ dentro del entorno multigeográfico.
Los siguientes tipos de sitio se pueden mover entre ubicaciones _geography_ :

- Sitios conectados a grupos de Microsoft 365, incluidos los sitios asociados a Microsoft Teams
- Sitios modernos sin una asociación de grupo de Microsoft 365
- Sitios clásicos de SharePoint
- Sitios de comunicación

Debe ser administrador global o administrador de SharePoint para mover un sitio entre ubicaciones _geográficas_ .
Hay una ventana de solo lectura durante el traslado _de geografía_ del sitio de SharePoint de aproximadamente 4-6 horas, dependiendo del contenido del sitio

#### <a name="best-practices"></a>**Procedimientos recomendados**

- Pruebe un movimiento del sitio de SharePoint en un sitio de prueba para familiarizarse con el procedimiento.
- Compruebe si el sitio se puede mover antes de programar o realizar el cambio.
- Cuando sea posible, programe movimientos de sitios entre ubicaciones geográficas fuera del horario laboral para reducir el impacto con el usuario.
- Comuníquese con los usuarios afectados antes del movimiento de sitios.

#### <a name="communicating-to-your-users"></a>**Comunicación con los usuarios**

Al mover sitios de SharePoint entre ubicaciones _geography_ , es importante comunicar a los usuarios de los sitios (por lo general, cualquier persona con la capacidad de editar el sitio) lo que se espera. Esto puede ayudar a reducir la confusión de los usuarios y las llamadas a su departamento de soporte técnico. Envíe un correo a los usuarios antes de mover los sitios e infórmeles de lo siguiente:

- Cuándo se espera que inicie el movimiento y cuánto tiempo se espera que tarde en completarse.
- A qué ubicación _geográfica_ se mueve su sitio y la dirección URL para acceder a la nueva ubicación
- Necesitan cerrar sus archivos sin realizar ediciones durante el desplazamiento.
- Los permisos de archivo y el uso compartido no cambiará como resultado del movimiento.
- Acciones previstas de la experiencia del usuario en un entorno multigeográfico

Asegúrese de enviar a los usuarios un correo electrónico cuando se complete correctamente el movimiento para informarles de que pueden reanudar su trabajo en los sitios.

#### <a name="scheduling-sharepoint-site-moves"></a>**Programación de movimientos de sitios de SharePoint**

Puede programar los movimientos de sitios de SharePoint por adelantado (como se describe más adelante en este artículo). Puede programar los movimientos como sigue:

- Puede programar un máximo de 4000 movimientos cada vez.
- Al empezar el movimiento, puede programar más, con un máximo de 4000 movimientos pendientes en la cola y en cualquier momento.
- El tamaño máximo de un sitio de SharePoint que se puede mover es de 1 terabyte (1 TB).

Para programar un traslado _de geografía_ del sitio de SharePoint para un momento posterior, incluya uno de los parámetros siguientes al iniciar el movimiento:

- PreferredMoveBeginDate: es probable que el movimiento comience en este momento especificado.
- PreferredMoveEndDate: es probable que el movimiento se complete en este momento especificado, con el mejor esfuerzo posible.

La hora para ambos parámetros debe especificarse según el Tiempo universal coordinado (UTC).

#### <a name="moving-the-site"></a>**Mover el sitio**

El traslado _de geografía_ del sitio de SharePoint requiere que se conecte y realice el traslado desde la dirección URL de Administración de SharePoint en la ubicación _geography_ donde se encuentra el sitio.

Por ejemplo, si la dirección URL del sitio es `https://contosohealthcare.sharepoint.com/sites/Turbines`, conéctese a la dirección URL Administración de SharePoint en `https://contosohealthcare-admin.sharepoint.com`:

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

#### <a name="validating-the-environment"></a>**Validación del entorno**

Se recomienda realizar una comprobación para asegurarse de que se puede mover el sitio, antes de programar su movimiento.

No se admite mover sitios con:

- Servicios de conectividad empresarial
- Formularios de InfoPath
- Se aplicaron las plantillas de Information Rights Management (IRM)

Para asegurarse de que todas las ubicaciones _geography_ son compatibles, ejecute `Get-SPOGeoMoveCrossCompatibilityStatus`. Esto mostrará todas las ubicaciones _geography_ y si el entorno es compatible con la ubicación _geography_ de destino.

Para realizar una comprobación de validación en el sitio, use `Start-SPOSiteContentMove` con el parámetro `-ValidationOnly` para comprobar si el sitio se puede mover. Por ejemplo:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Esto devolverá _Success_ si el sitio está listo para moverse o _Fail_ si hay algunas condiciones bloqueadas.

#### <a name="start-a-sharepoint-site-_geography_-move-for-a-site-with-no-associated-microsoft-365-group"></a>**Inicio de un traslado _de geografía_ del sitio de SharePoint para un sitio sin grupo de Microsoft 365 asociado**
  
De forma predeterminada, la dirección URL inicial del sitio cambiará a la dirección URL de la ubicación _geográfica_ de destino. Por ejemplo:

`https://Contoso.sharepoint.com/sites/projectx` a `https://ContosoEUR.sharepoint.com/sites/projectx`

En el caso de sitios sin asociación de grupos de Microsoft 365, también puede cambiar el nombre del sitio mediante el `-DestinationUrl` parámetro . Por ejemplo:

<https://Contoso.sharepoint.com/sites/projectx> a `https://ContosoEUR.sharepoint.com/sites/projecty`

Para iniciar el movimiento del sitio, ejecute:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

#### <a name="start-a-sharepoint-site-_geography_-move-for-a-microsoft-365-group-connected-site"></a>**Iniciar un traslado _de geografía_ del sitio de SharePoint para un sitio conectado a un grupo de Microsoft 365**

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

#### <a name="cancel-a-sharepoint-site-_geography_-move"></a>**Cancelación de un traslado _de geografía_ del sitio de SharePoint**

Puede detener un movimiento _de geografía_ del sitio de SharePoint, siempre que el movimiento no esté en curso o se complete mediante el cmdlet Stop-SPOSiteContentMove.

#### <a name="determining-the-status-of-a-sharepoint-site-_geography_-move"></a>**Determinación del estado de un traslado _de geografía_ del sitio de SharePoint**

Puede determinar el estado de un traslado de sitio fuera _de geography al_ que está conectado mediante los siguientes cmdlets:

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

#### <a name="user-experience"></a>**Experiencia del usuario**

Los usuarios del sitio deben observar una interrupción mínima cuando su sitio se mueve a una ubicación _geográfica_ diferente. Excepto un estado breve de solo lectura durante el movimiento, los permisos y los vínculos existentes seguirán funcionando como se espera una vez completado el proceso.

#### <a name="site"></a>**Site**

Mientras el movimiento está en curso, el sitio se establece en solo lectura. Una vez completado el traslado, el usuario se dirige al nuevo sitio en la nueva ubicación _geography_ cuando hace clic en marcadores u otros vínculos al sitio.

#### <a name="permissions"></a>**Permisos**

Los usuarios con permisos al sitio seguirán teniendo acceso durante el movimiento y después de su finalización.

#### <a name="sync-app"></a>**Aplicación de sincronización**

La aplicación de sincronización detectará automáticamente y transferirá sin problemas la sincronización a la nueva ubicación del sitio una vez que se complete el traslado del sitio. El usuario no necesitará volver a iniciar sesión ni realizar ninguna otra acción. (Versión 17.3.6943.0625 o posterior de la aplicación de sincronización necesaria). Si un usuario actualiza un archivo mientras el movimiento está en curso, la aplicación de sincronización le notificará que las cargas de archivos están pendientes mientras el movimiento está en curso.

#### <a name="sharing-links"></a>**Vínculos para compartir**
Cuando se complete el movimiento _geography_ del sitio de SharePoint, los vínculos compartidos existentes para los archivos que se han movido se redirigirán automáticamente a la nueva ubicación _geography_ .

#### <a name="most-recently-used-files-in-office-mru"></a>**Los archivos usados recientemente de Office (MRU)**

El servicio MRU se actualiza con la dirección URL del sitio y sus direcciones URL de contenido cuando se complete el movimiento. Eso se aplica a Word, Excel y PowerPoint

#### <a name="onenote-experience"></a>**Experiencia de OneNote**

El cliente de win32 de OneNote y la aplicación UWP (Universal) detectarán automáticamente y sincronizarán perfectamente blocs de notas con la nueva ubicación del sitio cuando se complete el movimiento. El usuario no necesitará volver a iniciar sesión ni realizar ninguna otra acción. El único indicador visible para el usuario es que la sincronización de la notebook fallaría cuando el movimiento del sitio esté en curso. Esta experiencia está disponible en las siguientes versiones de cliente de OneNote: -OneNote win32 – Versión 16.0.8326.2096 (y versiones posteriores) -OneNote UWP – Versión 16.0.8431.1006 (y versiones posteriores) -OneNote Mobile App – Versión 16.0.8431.1011 (y versiones posteriores)

#### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>**Teams (aplicable a sitios conectados a grupos de Microsoft 365)**

Cuando se complete el traslado _de geografía_ del sitio de SharePoint, los usuarios tendrán acceso a sus archivos de sitio de grupo de Microsoft 365 en la aplicación Teams. Además, los archivos compartidos a través del chat de Teams desde su sitio antes del traslado de _Geography_ seguirán funcionando una vez completado el movimiento.
El traslado _de geografía_ del sitio de SharePoint no admite el traslado de canales privados de una _geografía_ a otra. Los canales privados permanecen en la _geografía_ original.

#### <a name="sharepoint-mobile-app-iosandroid"></a>**Aplicación móvil de SharePoint para Android y iOS**
La aplicación móvil de SharePoint es compatible con _geografía_ cruzada y es capaz de detectar la nueva ubicación _geográfica_ del sitio.

#### <a name="sharepoint-workflows"></a>**Flujos de trabajo de SharePoint**
Los flujos de trabajo de SharePoint 2013 deben volver a publicarse después del traslado del sitio. Los flujos de trabajo de SharePoint 2010 deberían seguir funcionando con normalidad.

#### <a name="apps"></a>**Aplicaciones**
Si va a mover un sitio con aplicaciones, debe volver a confirmar la aplicación en la nueva ubicación _geography_ del sitio, ya que es posible que la aplicación y sus conexiones no estén disponibles en la ubicación _geography_ de destino.

#### <a name="power-automate"></a>**Power Automate**
En la mayoría de los casos, los flujos de Power Automate seguirán funcionando después de un traslado _de geografía_ del sitio de SharePoint. Se recomienda probarlos una vez completado el movimiento.

#### <a name="power-apps"></a>**Power Apps**

Power Apps debe volver a crearse en la ubicación de destino.

#### <a name="data-movement-between-geo-locations"></a>**Mover datos entre ubicaciones geográficas**

SharePoint usa Azure Blob Storage para su contenido, mientras que los metadatos asociados a sitios y sus archivos se almacenan en SharePoint. Una vez que el sitio se mueve de su ubicación _geográfica_ de origen a su ubicación _geográfica_ de destino, el servicio también moverá su almacenamiento de blobs asociado. El movimiento de Blob Storage se completa en aproximadamente 40 días. Esto no afectará a la interacción de los usuarios con los datos.

Puede comprobar el estado de movimiento de Blob Storage mediante el cmdlet [Get-SPOCrossGeoMoveReport](/powershell/module/sharepoint-online/get-spocrossgeomovereport) .
****

### <a name="enabling-sharepoint-multi-geo-in-your-_satellite-geography_-location"></a>**Habilitación de SharePoint Multi-Geo en la ubicación _de geografía satélite_**

Este artículo está destinado a los administradores globales o de SharePoint que han creado una ubicación de _geografía por satélite_ multigeográfica **antes** de que las funcionalidades de SharePoint Multi-Geo estén disponibles con carácter general el 27 de marzo de 2019 y que no hayan habilitado SharePoint Multi-Geo en sus ubicaciones _de geografía satélite_.

>[!NOTE]
>Si ha agregado una nueva ubicación _de Geography_ **después del 27 de marzo de 2019**, no es necesario realizar estas instrucciones, ya que la nueva ubicación _de Geography_ ya estará habilitada para OneDrive y SharePoint Multi-Geo.

Estas instrucciones le permitirán habilitar SharePoint en la ubicación _de Geografía satélite_, para que los usuarios de satélite multigeográfica puedan aprovechar las funcionalidades de OneDrive y SharePoint Multi-Geo en O365.

>[!IMPORTANT]
>Tenga en cuenta que esta es una activación unidireccional. Una vez que haya establecido el modo SPO, no podrá revertir el _inquilino_ al modo multigeográfico de OneDrive solo sin una escalación con soporte técnico.

#### <a name="to-set-a-_geography_-location-into-spo-mode"></a>**Para establecer una ubicación _geográfica_ en modo SPO**

Para establecer una ubicación _geográfica_ en modo SPO, conéctese a la ubicación _de geografía_ que desea establecer en modo SPO:

1. Abra el Shell de administración de SharePoint Online
2. Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3. Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience.](../media/Set-SPO-MultiGeo.jpg)
4. Esta operación normalmente tarda aproximadamente una hora mientras se realizan varias copias de seguridad de publicación en el servicio y se vuelve a marcar el _inquilino_. Después de al menos una hora, lleve a cabo un Get-SPOMultiGeoExperience.  Esto le mostrará si esta ubicación _geográfica_ está en modo SPO.</br></br>
![Imagen de Set-SPOMultiGeoExperience.](../media/Get-SPO-MultiGeo.jpg)

>[!Note]
>Ciertas memorias caché del servicio se actualizan cada 24 horas, por lo que es posible que durante un período de hasta 24 horas, la _geografía satélite_ se comporte intermitentemente como si estuviera todavía en modo ODB. Esto no causa problemas técnicos.

## <a name="migration"></a>Migración

Cuando se mueve SharePoint Online, también se mueven los datos de los siguientes servicios:
  
- OneDrive para la Empresa
- Servicios de vídeo de Microsoft 365
- Office en un explorador
- Microsoft 365 Apps para empresas
- Visio Pro para Microsoft 365

Una vez completado el movimiento de los datos de SharePoint Online, es posible que vea algunos de los siguientes efectos.
  
### <a name="microsoft-365-video-services"></a>Servicios de vídeo de Microsoft 365

- El movimiento de datos del vídeo tarda más que los movimientos del resto del contenido en SharePoint Online.
- Después de mover el contenido de SharePoint Online, habrá un período de tiempo en el que los vídeos no se puedan reproducir.
- Vamos a quitar las copias codificadas trans del centro de datos anterior y a transcodificarlas de nuevo en el nuevo centro de datos.

### <a name="search"></a>Búsqueda

En el curso de mover los datos de SharePoint Online, migramos el índice de búsqueda y la configuración de búsqueda a una nueva ubicación. Hasta que hayamos **completado** el traslado de los datos de SharePoint Online, seguiremos atendiendo a los usuarios desde el índice en la ubicación original. En la nueva ubicación, la búsqueda comienza automáticamente a rastrear el contenido después de haber completado el movimiento de los datos de SharePoint Online. A partir de este punto y en adelante, atenderemos a los usuarios desde el índice migrado. Los cambios en el contenido que se produjeron después de la migración no se incluyen en el índice migrado hasta que el rastreo los recoge. La mayoría de los clientes no se da cuenta de que los resultados son menos frescos justo después de haber completado el traslado de sus datos de SharePoint Online, pero algunos clientes podrían experimentar una actualización reducida en las primeras 24-48 horas.
  
Las siguientes características de búsqueda se ven afectadas:
  
- Resultados de búsqueda y elementos web de búsqueda: los resultados no incluyen los cambios que se produjeron después de la migración hasta que el rastreo los recoge.
- Delve: Delve no incluye los cambios que se produjeron después de la migración hasta que el rastreo los recoge.
- Informes de popularidad y búsqueda para el sitio: los recuentos de informes de Excel en la nueva ubicación solo incluyen recuentos y recuentos migrados de informes de uso que se han ejecutado después de haber completado el movimiento de los datos de SharePoint Online. Los recuentos del período provisional se pierden y no se pueden recuperar. Este período suele ser de un par de días. Algunos clientes pueden experimentar pérdidas más cortas o más largas.
- Portal de vídeo: los recuentos de vistas y las estadísticas del Portal de vídeo dependen de las estadísticas de los informes de Excel, por lo que los recuentos de vistas y las estadísticas de Video Portal se pierden durante el mismo período de tiempo que para los informes de Excel.
- eDiscovery: los elementos que cambiaron durante la migración no se muestran hasta que el rastreo recoge los cambios.
- Protección contra pérdida de datos (DLP): las directivas no se aplican en los elementos que cambian hasta que el rastreo recoge los cambios.

Como parte de la migración, la _geografía aprovisionada principal_ cambiará y todo el contenido nuevo se almacenará en reposo en la nueva _geografía aprovisionada principal_. El contenido existente se moverá en segundo plano sin ningún impacto durante un máximo de 90 días después del primer cambio en la ubicación de datos de SharePoint Online en el centro de administración.

## <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?

Puede encontrar la ubicación de datos real en el Centro de Administración de _inquilinos_.  Como administrador _de inquilinos_, puede encontrar la ubicación de datos real para los datos confirmados; para ello, vaya a Administración->Settings->Org Settings->Organization Profile->Data Location. Si no tiene un _inquilino_ creado, puede crear un _inquilino_ al registrarse para una prueba de M365.
