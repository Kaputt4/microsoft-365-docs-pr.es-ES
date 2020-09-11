---
title: Capacidades de movilidad y seguridad básicas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: La movilidad y la seguridad básica pueden ayudarle a proteger y administrar dispositivos móviles.
ms.openlocfilehash: a88afd539209d20046a778f8c6d16cadd51b5a9a
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430313"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Capacidades de movilidad y seguridad básicas

La movilidad y la seguridad básica pueden ayudarle a proteger y administrar dispositivos móviles como iPhone, iPad, Android y Windows Phone usados por usuarios con licencia de Microsoft 365 en su organización. Puede crear directivas de administración de dispositivos móviles con opciones de configuración que pueden ayudar a controlar el acceso al correo electrónico y los documentos de Microsoft 365 de la organización para aplicaciones y dispositivos móviles compatibles. Si un dispositivo se pierde o se lo roban, puede borrarlo de forma remota para quitar la información confidencial de la organización.

## <a name="supported-devices"></a>Dispositivos admitidos

Puede usar la movilidad y la seguridad básicas para proteger y administrar los siguientes dispositivos.

- iOS 11,0 o versiones posteriores
    
- Android 5,0 o versiones posteriores<sup>3</sup>
    
- Windows 8,1<sup>1</sup>
    
- Windows 8,1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 Mobile<sup>2</sup>   

<sup>1</sup> El control de acceso para dispositivos Windows 8,1 RT está limitado a Exchange ActiveSync.

<sup>2</sup> El control de acceso para dispositivos Windows 8,1 RT está limitado a Exchange ActiveSync.
El control de acceso para Windows 10 requiere una suscripción que incluya Azure AD Premium y que el dispositivo deba unirse a Azure Active Directory.

<sup>3</sup> El control de acceso para dispositivos Windows 8,1 RT está limitado a Exchange ActiveSync.
Después del 2020 de junio, las versiones de Android posteriores a 9 no pueden administrar la configuración de contraseña excepto en dispositivos Samsung Knox.

>[!NOTE]
>Los dispositivos ya inscritos en versiones anteriores del sistema operativo seguirán funcionando, aunque las funcionalidades podrían cambiar sin previo aviso.

Si los usuarios de la organización usan dispositivos móviles que no son compatibles con la movilidad y la seguridad básica, es posible que desee bloquear el acceso a la aplicación de Exchange ActiveSync al correo electrónico de Microsoft 365 para esos dispositivos, a fin de que los datos de la organización sean más seguros. Para conocer los pasos para bloquear Exchange ActiveSync, consulte [administrar la configuración de acceso a dispositivos en Basic Mobility and Security](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Control de acceso para el correo electrónico y los documentos de Microsoft 365

Las aplicaciones compatibles para los distintos tipos de dispositivos móviles en la tabla siguiente solicitan a los usuarios que se inscriban en la movilidad y la seguridad básicas en las que hay una nueva Directiva de administración de dispositivos móviles que se aplica a un dispositivo del usuario y que el usuario no haya inscrito previamente el dispositivo. Si el dispositivo de un usuario no cumple con una directiva, en función de cómo configure la Directiva, es posible que se bloquee a un usuario para que no pueda acceder a los recursos de Microsoft 365 en estas aplicaciones o que tenga acceso, pero Microsoft 365 informa de una infracción de la Directiva.

|**Producto**|**iOS 10,0 o posterior**|**Android 5,0 o posterior**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync incluye correo electrónico integrado y aplicaciones de terceros, como TouchDown, que usan Exchange ActiveSync versión 14,1 o posterior. |Correo |Correo electrónico |
|**Office**   y **OneDrive para la empresa** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**En teléfonos y tabletas**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Solamente en teléfonos:** <br/> Office Mobile |

>[!NOTE]
- >La compatibilidad con iOS 10,0 y versiones posteriores incluye dispositivos iPhone y iPad.
- >La administración de dispositivos de sistema operativo BlackBerry no es compatible con la administración de dispositivos móviles para Microsoft 365. Use BlackBerry Business Cloud Services (BBCS) de BlackBerry para administrar dispositivos de sistema operativo BlackBerry. Los dispositivos BlackBerry que ejecutan el sistema operativo Android son compatibles como dispositivos Android estándar
- >No se pedirá a los usuarios que realicen la inscripción y no se bloquearán ni se notificarán la infracción de la Directiva si usan el explorador móvil para acceder a sitios de SharePoint de Microsoft 365, documentos en Office online o correo electrónico en Outlook Web App.
    
El siguiente diagrama muestra lo que sucede cuando un usuario con un nuevo dispositivo inicia sesión en una aplicación que admite el control de acceso con movilidad y seguridad básicas. El usuario tiene bloqueado el acceso a los recursos de Microsoft 365 en la aplicación hasta que inscriba su dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Control de acceso de seguridad y movilidad básico":::

Nota: las directivas y reglas de acceso creadas en MDM para Microsoft 365 Business Standard reemplazarán las directivas de buzón de dispositivo móvil de Exchange ActiveSync y las reglas de acceso de dispositivo creadas en el centro de administración de Exchange. Una vez que un dispositivo está inscrito en MDM para Microsoft 365 Business Standard, se omitirá cualquier directiva de buzón de dispositivo móvil de Exchange ActiveSync o regla de acceso de dispositivo aplicada al dispositivo. Para obtener más información acerca de Exchange ActiveSync, vea [Exchange ActiveSync en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="policy-settings-for-mobile-devices"></a>Configuración de directivas para dispositivos móviles

Si crea una directiva para bloquear el acceso con determinados valores activados, los usuarios no podrán acceder a los recursos de Microsoft 365 cuando usen una aplicación compatible que aparezca en [control de acceso para el correo electrónico y los documentos de microsoft 365](capabilities.md). 

La configuración que puede impedir que los usuarios tengan acceso a los recursos de Microsoft 365 se encuentran en estas secciones:

- Seguridad
    
- Cifrado
    
- Descodificar
    
- Perfil de correo electrónico administrado  

Por ejemplo, el siguiente diagrama muestra lo que sucede cuando un usuario con un dispositivo inscrito no cumple una opción de seguridad de una directiva de administración de dispositivos móviles que se aplica a su dispositivo. El usuario inicia sesión en una aplicación que admite el control de acceso con movilidad y seguridad básicas. Se impide el acceso a los recursos de Microsoft 365 en la aplicación hasta que el dispositivo cumpla con la configuración de seguridad.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Mensaje básico de cumplimiento de seguridad y movilidad":::

En las secciones siguientes se enumeran las opciones de directiva que puede usar para ayudar a proteger y administrar los dispositivos móviles que se conectan a los recursos de la organización de Microsoft 365.

## <a name="security-settings"></a>Configuración de seguridad

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Requerir contraseña|Sí|Sí|Sí|
|Evitar contraseña simple|Sí|No|No|
|Requerir una contraseña alfanumérica|Sí|No|No|
|Longitud mínima de la contraseña |Sí|Sí|Sí|
|Número de errores de inicio de sesión antes borrar el dispositivo |Sí|Sí|Sí|
|Minutos de inactividad antes de bloquear el dispositivo |Sí|Sí|Sí|
|Expiración de contraseña (días) |Sí|Sí|Sí|
|Recordar el historial de contraseñas y evitar la reutilización |Sí|Sí|Sí|

## <a name="encryption-settings"></a>Configuración de cifrado 

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Requerir cifrado de datos en los dispositivos<sup>1</sup> |No|Sí|Sí|

<sup>1</sup> Con Samsung Knox, también puede requerir el cifrado en las tarjetas de almacenamiento. 

## <a name="jail-broken-setting"></a>Configuración de descodificación 

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|El dispositivo no se puede descodificar ni descifrar |Sí|Sí|Sí|

## <a name="managed-email-profile-option"></a>Opción de perfil de correo electrónico administrado 

La siguiente opción permite impedir que los usuarios tengan acceso a su correo electrónico de Microsoft 365 si están usando un perfil de correo electrónico creado manualmente. Los usuarios de dispositivos iOS deben eliminar su perfil de correo electrónico creado manualmente para que puedan tener acceso a su correo electrónico. Después de eliminar el perfil, se creará automáticamente un nuevo perfil en el dispositivo. Para obtener instrucciones sobre cómo los usuarios finales pueden obtener compatibilidad, vea se [encontró una cuenta de correo electrónico existente](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|El perfil de correo electrónico es administrado |Sí|No|No|

## <a name="cloud-settings"></a>Configuración de nube 

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Requerir copia de seguridad cifrada |Sí|No|No|
|Bloquear copia de seguridad de la nube |Sí|No|No|
|Bloquear sincronización de documentos |Sí|No|No|
|Bloquear sincronización de fotos  |Sí|No|No|
|Permitir copia de seguridad de Google  |N/D|No|Sí|
|Permitir la sincronización automática de cuentas de Google  |N/D|No|Sí|

## <a name="system-settings"></a>Configuración del sistema 

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear captura de pantalla |Sí|No|Sí|
|Bloquear el envío de datos de diagnóstico de dispositivos |Sí|No|Sí|

## <a name="application-settings"></a>Configuración de aplicaciones 

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear las videoconferencias en el dispositivo |Sí|No|No|
|Bloquear el acceso a la tienda de aplicaciones |Sí|No|Sí|
|Requerir contraseña al acceder a la tienda de aplicaciones |No|Sí|Sí|

## <a name="device-capabilities-settings"></a>Configuración de las funcionalidades del dispositivo 

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear conexión con almacenamiento extraíble |Sí|Sí|No|
|Bloquear conexión Bluetooth |Sí|Sí|No|

##  <a name="additional-settings"></a>Configuración adicional 

Puede establecer las siguientes opciones de directiva adicionales usando cmdlets de PowerShell. Para obtener más información, vea [PowerShell del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

|**Nombre de la configuración**|**iOS 7,1 y versiones posteriores**|**Android 5 y versiones posteriores**|
|:-----|:-----|:-----|
|CameraEnabled|Sí|Sí|
|RegionRatings|Sí|No|
|MoviesRatings|Sí|No|
|TVShowsRating |Sí|No|
|AppsRatings |Sí|No|
|AllowVoiceDialing |Sí|No|
|AllowVoiceAssistant |Sí|No|
|AllowAssistantWhileLocked  |Sí|No|
|AllowPassbookWhileLocked |Sí|No|
|MaxPasswordGracePeriod |Sí|No|
|PasswordQuality |No|Sí|
|SystemSecurityTLS  |Sí|No|
|WLANEnabled  |No|No|

## <a name="settings-supported-by-windows"></a>Configuración admitida por Windows 

Para administrar dispositivos de Windows 10, puedes inscribirlos como dispositivos móviles. Una vez implementada una Directiva aplicable, los usuarios con dispositivos de Windows 10 deberán inscribirse en la movilidad y la seguridad básicas la primera vez que usen la aplicación de correo electrónico integrada para acceder a su correo electrónico de Microsoft 365 (requiere una suscripción de Azure AD Premium).

La siguiente configuración se admite para dispositivos Windows 10 que están inscritos como dispositivos móviles. Esta configuración no impide que los usuarios obtengan acceso a los recursos de Microsoft 365.

### <a name="security-settings"></a>Configuración de seguridad

- Requerir una contraseña alfanumérica

- Longitud mínima de la contraseña
    
- Número de errores de inicio de sesión antes borrar el dispositivo
    
- Minutos de inactividad antes de bloquear el dispositivo
    
- Expiración de contraseña (días)
    
- Recordar el historial de contraseñas y evitar la reutilización   

>[!NOTE]
>Los siguientes valores de configuración que regulan solo las contraseñas controlan las cuentas locales de Windows. Las cuentas de Windows que se proporcionan a través de una Unión a un dominio o Azure Active Directory no se ven afectadas por esta configuración.

### <a name="system-settings"></a>Configuración del sistema

Bloquear el envío de datos de diagnóstico desde el dispositivo.

### <a name="additional-settings"></a>Otras configuraciones

Puede establecer estas opciones de configuración de directiva adicionales con los cmdlets de PowerShell:

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>Borrar de forma remota un dispositivo móvil

Si se pierde o se roba un dispositivo, puede eliminar los datos de la organización confidencial y ayudar a evitar el acceso a los recursos de la organización de Microsoft 365 mediante la eliminación del centro de seguridad & cumplimiento > la administración de dispositivos de **prevención de pérdida de datos**  >  **Device management**. Puede realizar un borrado selectivo para quitar solo los datos de la organización o un borrado completo para eliminar toda la información de un dispositivo y restaurar la configuración original.

Para obtener más información, consulte [borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Temas relacionados

[Información general sobre la movilidad y la seguridad básicas de Microsoft 365](overview.md)

[Crear directivas de seguridad de dispositivos en la movilidad y la seguridad básicas](create-device-security-policies.md)