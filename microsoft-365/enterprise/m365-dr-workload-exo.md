---
title: Data Residency para Exchange Online
description: Más información sobre Data Residency para Exchange Online
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
ms.openlocfilehash: 17799d6d69daa50d6d9cb70ec3632314d5c64d3a
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806314"
---
# <a name="data-residency-for-exchange-online"></a>Data Residency para Exchange Online

## <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

### <a name="product-terms"></a>Términos del producto

Condiciones necesarias:

El inquilino tiene un país de registro incluido en Geografía de la región local, la Unión Europea o la Estados Unidos.

_Para conocer el idioma actual, consulte la <a href="https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all" target="_blank">**página web**</a> De los Términos de producto de privacidad y seguridad y vea la sección titulada "Ubicación de los datos del cliente en reposo para core online services"._

**Compromiso:**

>[!NOTE]
>Si el cliente aprovisiona su inquilino en Australia, Brasil, Canadá, la Unión Europea, Francia, Alemania, India, Japón, Noruega, Qatar, Sudáfrica, Corea del Sur, Suecia, Suiza, Emiratos Árabes Unidos, Reino Unido o Estados Unidos, Microsoft almacenará los siguientes datos de cliente en reposo solo dentro de ese geo: Exchange Online  contenido de buzón (cuerpo del correo electrónico, entradas de calendario y contenido de datos adjuntos de correo electrónico)

### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. El inquilino tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. El inquilino tiene una suscripción Data Residency avanzada válida para todos los usuarios del inquilino.
1. Los datos del cliente de Exchange Online suscripción se aprovisionan en Geografía local o Geografía local expandida

**Compromiso:**

Consulte la [página compromiso de ADR](m365-dr-commitments.md#exchange-online) para conocer los compromisos específicos proporcionados a través de los Términos del producto. Algunos ejemplos de los datos confirmados son todos los tipos de buzones, incluidos los buzones de usuario, los buzones de recursos y los buzones de archivo.

### <a name="multi-geo-add-on"></a>Complemento multigeográfica

Condiciones necesarias:

1. Los inquilinos tienen una suscripción multigeográfica válida que cubre todos los usuarios asignados a una _geografía satélite_.
1. El cliente debe tener una Enterprise Agreement activa.
1. El total de unidades multigeográficas adquiridas debe ser superior al 5 % del total de puestos aptos en el inquilino.

**Compromiso:**

Los clientes pueden asignar una geografía satélite compatible con multigeográfica a un tipo de buzón compatible. Consulte la [sección Disponibilidad multigeográfica de Microsoft 365](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability) de la página Multi-Geo de Microsoft 365 para obtener más información. Los datos en reposo de Office 365 Services para el buzón tal como se definen en los términos del producto se almacenarán en la geografía por satélite asignada. Los tipos de buzón admitidos incluyen Exchange Online buzones de usuario principal y de archivo, buzones de recursos, buzones de grupo de Microsoft 365 y buzones compartidos.

## <a name="multi-geo-capabilities-in-exchange-online"></a>Capacidades multigeográficas en Exchange Online

Los clientes pueden asignar una _geografía por satélite_ compatible con Multi-Geo a un usuario. Consulte la [sección Disponibilidad multigeográfica de Microsoft 365](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability) de la página Multi-Geo de Microsoft 365 para obtener más información. Los datos en reposo del usuario para Office 365 Services, tal como se definen en los términos del producto, se almacenarán en la _geografía por satélite_ asignada. Esto incluye todos los tipos de buzones de Exchange Online, incluidos los buzones de usuario, los buzones de recursos, los buzones de grupo de Microsoft 365, los buzones compartidos y los buzones de archivo.

Puede colocar buzones en ubicaciones _de geografía satélite_ mediante:

1. Crear un nuevo buzón Exchange Online directamente en una ubicación _de geografía satélite_.
1. Mover un buzón de Exchange Online existente a una ubicación _de geografía satélite_ cambiando la ubicación de datos preferida del usuario.
1. Incorporación de un buzón de correo desde una organización local de Exchange directamente en una ubicación _de geografía satélite_ .

### <a name="mailbox-placement-and-moves"></a>Colocación y movimiento de buzones

Una vez que Microsoft complete los pasos de configuración multigeográfica de requisitos previos, Exchange Online respetará el atributo PreferredDataLocation en los objetos de usuario de Azure AD.
Exchange Online sincroniza la propiedad PreferredDataLocation de AAD con la propiedad MailboxRegion del servicio de directorio Exchange Online. El valor de MailboxRegion determina la geografía de la _región de macro_ o _la geografía de la región local_ donde se colocarán los buzones de usuario y los buzones de archivo asociados. No es posible configurar los buzones de correo principal y de archivo de un usuario para que residan en distintas ubicaciones _geográficas_ . Solo se puede configurar una _geografía de región de macro_ o geografía de _región local_ por objeto de usuario.

- Cuando PreferredDataLocation está configurado en un usuario con un buzón existente, el buzón se colocará en una cola de reubicación y se moverá automáticamente a la _geografía de la región de macro_ especificada o a la _geografía de la región local_ especificada.
- Cuando PreferredDataLocation está configurado en un usuario sin un buzón de correo existente, al aprovisionar el buzón, se aprovisionará en la _región de macro_ geografía especificada o geografía _de la región local_.
- Cuando PreferredDataLocation no se especifica en un usuario, al aprovisionar el buzón, se aprovisionará en la _geografía aprovisionada principal_.
- Si el código PreferredDataLocation es incorrecto (por ejemplo, un error tipográfico de NAN en lugar de NAM), el buzón se aprovisionará en la _geografía aprovisionada principal_.

>[!NOTE]
>Las funcionalidades multigeográficas y las reuniones hospedadas regionalmente en Skype Empresarial Online usan la propiedad PreferredDataLocation en los objetos de usuario para buscar servicios. Si configura los valores de PreferredDataLocation en objetos de usuario para reuniones hospedadas regionalmente, el buzón de esos usuarios se moverá automáticamente a la _región de macro_ geografía o geografía _de región local_ especificada después de habilitar multigeográfica en el inquilino de Microsoft 365.

### <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Limitaciones de características para multigeográfica en Exchange Online

- Las características de seguridad y cumplimiento (por ejemplo, auditoría y exhibición de documentos electrónicos) que están disponibles en el Centro de administración de Exchange (EAC) no están disponibles en las organizaciones multigeográficas. En su lugar, debe usar el Centro de cumplimiento de seguridad de Microsoft 365 & para configurar las características de seguridad y cumplimiento.
- Outlook para Mac los usuarios pueden experimentar una pérdida temporal de acceso a su carpeta de archivo en línea mientras mueve su buzón a una nueva ubicación _geográfica_. Esta condición se produce cuando los buzones principal y de archivo del usuario se encuentran en ubicaciones _geográficas_ diferentes, ya que los movimientos de buzón entre zonas geográficas pueden completarse en momentos diferentes.
- Los usuarios no pueden compartir carpetas de buzones entre las ubicaciones _geography_ de Outlook en la Web (anteriormente conocidas como Outlook Web App o OWA). Por ejemplo, un usuario de la Unión Europea no puede usar Outlook en la Web para abrir una carpeta compartida en un buzón que se encuentra en Estados Unidos. Sin embargo, los usuarios de Outlook en la Web pueden abrir otros buzones en diferentes ubicaciones _de Geografía_ mediante una ventana del explorador independiente, como se describe en Abrir el buzón de otra persona en una ventana del explorador independiente en Outlook Web App.

>[!NOTE]
>Outlook en Windows admite el uso compartido de carpetas de buzón entre zonas geográficas.

- Las carpetas públicas se admiten en organizaciones multigeográficas. Sin embargo, las carpetas públicas deben permanecer en la ubicación _Geografía aprovisionada principal_ . No puede mover carpetas públicas a ubicaciones geográficas satélite.
- En un entorno multigeográfico, no se admite la auditoría entre buzones de correo geográfico. Por ejemplo, si a un usuario se le asignan permisos para acceder a un buzón compartido en una ubicación _geográfica_ diferente, las acciones de buzón realizadas por ese usuario no se registran en el registro de auditoría de buzones del buzón compartido. Los eventos de auditoría del administrador de Exchange también están disponibles para la ubicación predeterminada. Para más información, consulte Administrar auditoría del buzón..

### <a name="administering-exchange-multi-geo"></a>Administración de Multi-Geo de Exchange

#### <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Administración de buzones de Exchange Online en un entorno multigeográfico

Exchange Online PowerShell es necesario para ver y configurar las propiedades multigeográficas en el entorno de Microsoft 365. Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Necesitará la v1.1.166.0 o una versión posterior en la v1.x del [módulo PowerShell de Microsoft Azure Active Directory](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) para ver la propiedad **PreferredDataLocation** en los objetos de usuario. No se puede modificar el valor de **PreferredDataLocation** directamente a través del PowerShell de AAD en los objetos de usuario que se sincronizan en AAD a través de AAD Connect. Solo se pueden modificar objetos basados en la nube a través del PowerShell de AAD. Para conectarse al PowerShell de Azure AD, consulte [Conectarse al PowerShell](connect-to-microsoft-365-powershell.md).

En Exchange Online Multi-Geo entornos, no es necesario realizar ningún paso manual para agregar zonas geográficas al inquilino. Después de recibir la publicación del Centro de mensajes que indica que la geogeografía múltiple está lista para Exchange Online, todas las zonas geográficas disponibles estarán listas y configuradas para su uso.

#### <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Conectarse directamente a una ubicación geográfica con el PowerShell de Exchange Online

Normalmente, Exchange Online PowerShell se conectará a la ubicación _de geografía aprovisionada principal_. Pero también puede conectarse directamente a ubicaciones _de geografía satélite_ . Debido a las mejoras de rendimiento, se recomienda conectarse directamente a la ubicación _geografía satélite_ cuando solo administre usuarios en esa ubicación.

Los requisitos para instalar y usar el módulo de PowerShell Exchange Online se describen en **[Instalación y mantenimiento del módulo de PowerShell Exchange Online](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-module)**.

Para conectar Exchange Online PowerShell a una ubicación _de Geography_ específica, el parámetro ConnectionUri es diferente de las instrucciones de conexión normales. El resto de comandos y valores son los mismos.

En concreto, debe agregar el valor ?email=\<emailaddress\> al final del valor ConnectionUri. \<emailaddress\> es la dirección de correo electrónico de **cualquier** buzón en la ubicación _geográfica_ de destino. Los permisos para ese buzón o la relación con sus credenciales no son un factor; la dirección de correo electrónico simplemente indica a Exchange Online PowerShell dónde conectarse.
  
Los clientes de GCC de Microsoft 365 o Microsoft 365 normalmente no necesitan usar el parámetro _ConnectionUri_ para conectarse a Exchange Online PowerShell. Sin embargo, para conectarse a una ubicación _de Geography_ específica, debe usar el parámetro ConnectionUri para poder usar ?email=\<emailaddress\> en el valor.
  
#### <a name="connect-to-a-_geography_-location-in-exchange-online-powershell"></a>Conexión a una ubicación _geográfica_ en Exchange Online PowerShell

Las siguientes instrucciones de conexión funcionan para las cuentas que están configuradas o no para la autenticación multifactor (MFA).

1. En una ventana de Windows PowerShell, cargue el módulo EXO V2 ejecutando el comando siguiente:

  ```powershell
   Import-Module ExchangeOnlineManagement
   ```
  
1. En el ejemplo siguiente, admin@contoso.onmicrosoft.com es la cuenta de administrador y la ubicación geográfica de destino es donde reside el buzón olga@contoso.onmicrosoft.com.
  
  ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```
  
1. Escriba la contraseña del admin@contoso.onmicrosoft.com en el símbolo del sistema que aparece. Si la cuenta está configurada para MFA, también debe escribir el código de seguridad.
  
#### <a name="view-the-available-_geography_-locations-that-are-configured-in-your-exchange-online-organization"></a>Visualización de las ubicaciones _de geografía_ disponibles configuradas en la organización de Exchange Online

Para ver la lista de ubicaciones _geográficas_ configuradas en Microsoft 365 Multi-Geo, ejecute el siguiente comando en Exchange Online PowerShell:

  ```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```
  
#### <a name="view-the-_primary-provisioned-geography_-location-for-your-exchange-online-organization"></a>Visualización de la ubicación _de geografía aprovisionada principal_ de la organización de Exchange Online

Para ver la ubicación _de geografía aprovisionada principal_ del inquilino, ejecute el siguiente comando en Exchange Online PowerShell:

 ```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

#### <a name="find-the-_geography_-location-of-a-mailbox"></a>Buscar la ubicación _geográfica_ de un buzón

El cmdlet **Get-Mailbox** en el PowerShell de Exchange Online muestra las siguientes propiedades multigeográficas en buzones:

- **Base de datos**: las tres primeras letras del nombre de la base de datos corresponden al código _Geography_ , que indica dónde se encuentra actualmente el buzón. Para los buzones de archivo en línea, podría usarse la propiedad **ArchiveDatabase**.
- **MailboxRegion**: especifica el código de ubicación _Geography_ establecido por el administrador (sincronizado desde PreferredDataLocation en Azure AD).
- **MailboxRegionLastUpdateTime**: Indica cuándo se actualizó MailboxRegion por última vez (de forma automática o manual).

Para ver estas propiedades de un buzón, use la siguiente sintaxis:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

  Por ejemplo, para ver la información de ubicación _geography_ del buzón de correo chris@contoso.onmicrosoft.com, ejecute el siguiente comando:

  ```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

  El resultado del comando tiene este aspecto:

  ```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```
  
 > [!NOTE]
 >Si el código de ubicación _Geography_ del nombre de la base de datos no coincide con el valor **MailboxRegion**, el buzón se colocará automáticamente en una cola de reubicación y se moverá a la ubicación _Geography_ especificada por el valor **MailboxRegion** (Exchange Online busca una falta de coincidencia entre estos valores de propiedad).

#### <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Mover un buzón existente basado únicamente en la nube a una ubicación geográfica específica

Un usuario basado únicamente en la nube es un usuario que no está sincronizado con el inquilino a través de AAD Connect. Dicho usuario se creó directamente en Azure AD. Use los cmdlets **Get-MsolUser** y **Set-MsolUser** en el módulo de Azure AD para Windows PowerShell para ver o especificar la ubicación _geography_ donde se almacenará el buzón de un usuario solo en la nube.

Para ver el valor **PreferredDataLocation** de un usuario, use la siguiente sintaxis en el PowerShell de Azure AD:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Por ejemplo, para ver el valor de **PreferredDataLocation** para el usuario michelle@contoso.onmicrosoft.com, ejecute el siguiente comando:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Para modificar el valor de **PreferredDataLocation** para un objeto de un usuario basado únicamente en la nube, use la siguiente sintaxis en el PowerShell de Azure AD:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Por ejemplo, para definir el valor de **PreferredDataLocation** en la ubicación geográfica Unión Europea (EUR) para el usuario michelle@contoso.onmicrosoft.com, ejecute el siguiente comando:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Como se mencionó anteriormente, no puede usar este procedimiento para los objetos de usuario sincronizados de Active Directory local. Tiene que cambiar el valor de **PreferredDataLocation** en Active Directory y sincronizarlo con AAD Connect. Para obtener más información, consulte [Sincronización de Azure Active Directory Connect: configurar la ubicación de datos preferida para recursos de Microsoft 365](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - El tiempo que se tarda en reubicar un buzón a una nueva ubicación geográfica depende de varios factores:
>
>   - El tamaño y tipo de buzón.
>   - La cantidad de buzones que se migrarán.
>   - La disponibilidad de recursos de migración.

#### <a name="move-an-inactive-mailbox-to-a-specific-_geography_"></a>Mover un buzón inactivo a una _geografía_ específica
  
No se pueden mover buzones inactivos que se conservan con fines de cumplimiento (por ejemplo, buzones en suspensión por juicio) cambiando su valor **PreferredDataLocation** . Para mover un buzón inactivo a otra _ubicación geográfica_, siga estos pasos:

1. Recupere el buzón inactivo. Para obtener instrucciones, consulte [Recuperación de un buzón inactivo](/microsoft-365/compliance/recover-an-inactive-mailbox).

1. Evite que el Asistente para carpetas administradas procese el buzón recuperado reemplazando \<MailboxIdentity\> por el nombre, alias, cuenta o dirección de correo electrónico del buzón y ejecutando el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

1. Asigne una licencia **Exchange Online plan 2** al buzón recuperado. Este paso es necesario para volver a colocar el buzón en suspensión por juicio. Para obtener instrucciones, consulte [Asignación de licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

1. Configure el valor **PreferredDataLocation** en el buzón, tal como se describe en la sección anterior.

1. Después de confirmar que el buzón se ha movido a la nueva ubicación geográfica, vuelva a colocar el buzón recuperado en suspensión por juicio. Para obtener instrucciones, consulte [Colocación de un buzón en suspensión por juicio](/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).

1. Después de comprobar que la suspensión por juicio está en vigor, permita que el Asistente para carpetas administradas procese de nuevo el buzón reemplazando \<MailboxIdentity\> por el nombre, alias, cuenta o dirección de correo electrónico del buzón y ejecutando el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

1. Vuelva a inactivar el buzón quitando la cuenta de usuario asociada al buzón. Para obtener instrucciones, consulte [Eliminación de un usuario de la organización](/admin/add-users/delete-a-user). Este paso también libera la licencia Exchange Online plan 2 para otros usos.

**Nota**: Al mover un buzón inactivo a otra ubicación geográfica, puede afectar a los resultados de la búsqueda de contenido o a la capacidad de buscar en el buzón desde la ubicación geográfica anterior. Para obtener más información, consulte [Búsqueda y exportación de contenido en entornos multigeográficos](/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).
  
#### <a name="create-new-cloud-mailboxes-in-a-specific-_geography_-location"></a>Creación de buzones de correo en la nube en una ubicación _geográfica_ específica

Para crear un nuevo buzón en una ubicación _geográfica_ específica, debe realizar cualquiera de estos pasos:

- Configure el valor **PreferredDataLocation** como se describe en la sección [Anterior Mover un buzón existente solo en la nube a una ubicación _geográfica_ específica](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) _antes_ de crear el buzón en Exchange Online. Por ejemplo, configure el valor **PreferredDataLocation** en un usuario antes de asignar una licencia.

- Asignar una licencia al mismo tiempo que se define el valor de **PreferredDataLocation**.

Para crear un nuevo usuario con licencia solo en la nube (no sincronizado con AAD Connect) en una ubicación _geográfica_ específica, use la sintaxis siguiente en PowerShell de Azure AD:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

Este ejemplo crea una cuenta de usuario para Elizabeth Brunner con los valores siguientes:

- Nombre de usuario principal: ebrunner@contoso.onmicrosoft.com
- Nombre: Elizabeth
- Apellido: Brunner
- Nombre para mostrar: Elizabeth Brunner
- Contraseña: Se genera de forma aleatoria y se muestra en los resultados del comando (debido a que no se usa el parámetro _contraseña_)
- Licencia: `contoso:ENTERPRISEPREMIUM` (E5)
- Ubicación: Australia (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Para obtener más información sobre cómo crear nuevas cuentas de usuario y cómo encontrar valores de LicenseAssignment en el PowerShell de Azure AD, consulte [Crear cuentas de usuario con PowerShell](create-user-accounts-with-microsoft-365-powershell.md) y [Ver licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Si usa Exchange Online PowerShell para habilitar un buzón y necesita que el buzón se cree directamente en la ubicación _geográfica_ especificada en **PreferredDataLocation**, debe usar un cmdlet Exchange Online como **Enable-Mailbox** o **New-Mailbox** directamente en el servicio en la nube. Si usa el cmdlet **Enable-RemoteMailbox** en PowerShell de Exchange local, el buzón se creará en la ubicación _Geografía aprovisionada principal_ .

#### <a name="onboard-existing-on-premises-mailboxes-in-a-specific-_geography_-location"></a>Incorporación de buzones locales existentes en una ubicación _geográfica_ específica

Puede usar las herramientas y procesos de incorporación estándar para migrar un buzón del entorno local de una organización de Exchange a Exchange Online, incluidos el [Panel de migración en el EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) y el cmdlet [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) del PowerShell de Exchange Online.

El primer paso consiste en comprobar que existe un objeto de usuario para que cada buzón se quiere incorporar y comprobar que el valor de **PreferredDataLocation** está configurado correctamente en Azure AD. Las herramientas de incorporación respetarán el valor de **PreferredDataLocation** y migrarán los buzones directamente a la ubicación geográfica especificada.

O bien, puede usar los pasos siguientes para incorporar buzones directamente en una ubicación _geográfica_ específica mediante el cmdlet [New-MoveRequest](/powershell/module/exchange/new-moverequest) en Exchange Online PowerShell.

1. Compruebe que existe el objeto de usuario para cada buzón que se va a incorporar y que **PreferredDataLocation** está definido en el valor deseado en Azure AD. El valor de **PreferredDataLocation** se sincronizará con el atributo **MailboxRegion** del objeto de usuario del correo correspondiente en Exchange Online.

1. Conéctese directamente a la ubicación _de Geografía satélite_ específica mediante las instrucciones de conexión de anteriormente en este tema.

1. En el PowerShell de Exchange Online, almacene en una variable las credenciales de administrador del entorno local que se usan para realizar una migración de buzones ejecutando el siguiente comando:

   ```powershell
   $RC = Get-Credential
   ```

1. En el PowerShell de Exchange Online, cree un nuevo **New-MoveRequest** similar al del ejemplo siguiente:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

1. Repita el paso 4 para cada buzón que quiera migrar del entorno local de Exchange a la ubicación geográfica satélite a la que está conectado actualmente.

1. Si quiere migrar más buzones a ubicaciones geográficas satélite diferentes, repita los pasos 2 a 4 para cada ubicación específica.

## <a name="multi-geo-reporting"></a>Informes multigeográficas
  
> [!NOTE]
> La característica de informes multigeográfica está actualmente en versión preliminar, no está disponible en todas las organizaciones y está sujeta a cambios.

**Informes de uso multigeográfica** en el Centro de administración de Microsoft 365 muestra el recuento de usuarios por ubicación _geográfica_. El informe muestra la distribución de usuarios durante el mes actual y proporciona los datos históricos para los últimos 6 meses.

## <a name="migration"></a>Migración

Dado que se tarda tiempo en mover cada usuario al nuevo centro de datos _Geography_ para un único inquilino, algunos usuarios seguirán estando en el centro de datos antiguo _Geography_ durante el traslado, mientras que otros estarán en el nuevo centro de datos _Geography_. Esto significa que es posible que algunas características que implican el acceso a varios buzones no funcionen por completo durante un período del proceso de traslado, que puede durar semanas. Estas características se describen en las secciones siguientes.

### <a name="open-shared-folder-in-outlook-web-access"></a>Abrir "Carpeta compartida" en Outlook Web Access

Algunos usuarios abren una carpeta de correo compartido desde otro buzón (en el que el usuario tiene permisos de lectura o escritura) en Outlook Web Access mediante la característica "Carpeta compartida". En la tabla siguiente se describe cómo funciona el acceso a carpetas compartidas durante el traslado de un buzón. Tenga en cuenta que los usuarios con permisos completos para un buzón compartido pueden abrir el buzón mediante Outlook Web Access durante el traslado.

| Configuración | Descripción |
|:-----|:-----|
|El usuario tiene permiso de carpeta de buzón para otro buzón  <br/> |Potencialmente limitado.  <br/> Si el usuario A y el buzón B no están en la misma _ubicación geográfica_ durante el traslado del inquilino, el usuario A no puede abrir la carpeta del buzón B en Outlook Web Access si el usuario A solo tiene permiso para una carpeta específica en el buzón B.  <br/> Para agregar una carpeta compartida, haga clic con el botón derecho en el nombre de usuario en el panel de navegación izquierdo y seleccione **Agregar carpeta compartida**.  <br/> |
|Usuario con permiso de buzón completo para otro buzón  <br/> |Totalmente compatible.  <br/> Si el usuario A tiene permiso de "acceso completo" al buzón B, el usuario A puede hacer clic en la carpeta compartida en el panel de navegación izquierdo de Outlook Web Access para abrir una ventana que muestre el buzón B.  Un usuario puede abrir un buzón compartido con Outlook Web Access durante el traslado sin ningún impacto adverso. La limitación solo se aplica al uso compartido de nivel de carpeta en un buzón de correo.

El proceso de migración de datos de correo electrónico a Microsoft 365 durante el Exchange Online es un escenario común y se admite. La migración a la nube entre las zonas geográficas del centro de datos no interfiere con las migraciones locales a buzones de correo en la nube.

### <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?

Puede encontrar la ubicación de datos real en el Centro de Administración de inquilinos.  Como administrador de inquilinos, puede encontrar la ubicación de datos real para los datos confirmados; para ello, vaya a Administración->Settings->Org Settings->Organization Profile->Data Location.
