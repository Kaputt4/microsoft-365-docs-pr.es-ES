---
title: Capacidades de Movilidad y seguridad básicas
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
description: La movilidad y la seguridad básicas pueden ayudarle a proteger y administrar dispositivos móviles.
ms.openlocfilehash: 746131e90e207d7b888a3ddcaf4ff0656606a2c7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877121"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Capacidades de Movilidad y seguridad básicas

La movilidad y la seguridad básicas pueden ayudarle a proteger y administrar dispositivos móviles como iPhone, iPad, Android y Windows Phones que usan los usuarios de Microsoft 365 con licencia de su organización. Puede crear directivas de administración de dispositivos móviles con configuraciones que puedan ayudar a controlar el acceso al correo electrónico y documentos de Microsoft 365 de su organización para dispositivos móviles y aplicaciones compatibles. Si un dispositivo se pierde o se lo roban, puede borrarlo de forma remota para quitar la información confidencial de la organización.

## <a name="supported-devices"></a>Dispositivos admitidos

Puede usar la movilidad y la seguridad básicas para proteger y administrar los siguientes dispositivos.

- iOS 11.0 o versiones posteriores

- Android 5.0 o versiones<sup>posteriores 3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> El control de acceso para dispositivos Windows 8.1 RT está limitado a Exchange ActiveSync.

<sup>2</sup> El control de acceso para dispositivos Windows 8.1 RT está limitado a Exchange ActiveSync.
El control de acceso para Windows 10 requiere una suscripción que incluya Azure AD Premium y el dispositivo debe unirse a Azure Active Directory.

<sup>3</sup> El control de acceso para dispositivos Windows 8.1 RT está limitado a Exchange ActiveSync.
Después de junio de 2020, las versiones de Android posteriores a 9 no pueden administrar la configuración de contraseña excepto en dispositivos DesA de Knox.

>[!NOTE]
>Los dispositivos ya inscritos con versiones anteriores del sistema operativo siguen funcionando, aunque las funcionalidades pueden cambiar sin previo aviso.

Si los usuarios de su organización usan dispositivos móviles que no son compatibles con movilidad y seguridad básicas, es posible que desee bloquear el acceso de una aplicación Exchange ActiveSync correo electrónico de Microsoft 365 para esos dispositivos, para ayudar a que los datos de su organización sean más seguros. Para ver los pasos para bloquear Exchange ActiveSync, consulta [Administrar la configuración de acceso de dispositivos en Movilidad y seguridad básicas.](manage-device-access-settings.md)

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Control de acceso para documentos y correo electrónico de Microsoft 365

Las aplicaciones admitidas para los distintos tipos de dispositivos móviles de la tabla siguiente solicitan a los usuarios que se inscriban en Movilidad y seguridad básicas, donde hay una nueva directiva de administración de dispositivos móviles que se aplica al dispositivo de un usuario y el usuario no ha inscrito previamente el dispositivo. Si el dispositivo de un usuario no cumple con una directiva, en función de cómo configure la directiva, es posible que se bloquee el acceso de un usuario a los recursos de Microsoft 365 en estas aplicaciones o que tenga acceso, pero Microsoft 365 informa de una infracción de directiva.

|**Producto**|**iOS 10.0 o posterior**|**Android 5.0 o posterior**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync incluye correo electrónico integrado y aplicaciones de terceros, como TouchDown, que usan Exchange ActiveSync versión 14.1 o posterior. |Correo |Correo electrónico |
|**Office**   y  **OneDrive para la Empresa** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**En teléfonos y tabletas:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Solamente en teléfonos:** <br/> Office Mobile |

>[!NOTE]
- >La compatibilidad con iOS 10.0 y versiones posteriores incluye dispositivos iPhone y iPad.
- >La administración de dispositivos blackBerry OS no es compatible con la seguridad básica y la movilidad. Use BlackBerry Business Cloud Services (BBCS) de BlackBerry para administrar dispositivos blackBerry OS. Los dispositivos Blackberry que ejecutan el sistema operativo Android se admiten como dispositivos Android estándar
- >No se pedirá a los usuarios que se inscriban y no se les bloqueará ni se les notifica por infracción de directiva si usan el explorador móvil para acceder a sitios de SharePoint de Microsoft 365, documentos en Office Online o correo electrónico en Outlook Web App.

En el siguiente diagrama se muestra lo que sucede cuando un usuario con un nuevo dispositivo inicia sesión en una aplicación que admite el control de acceso con movilidad y seguridad básicas. Se bloquea al usuario el acceso a los recursos de Microsoft 365 en la aplicación hasta que inscribe su dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Control de acceso de movilidad básica y seguridad":::

> [!NOTE]
> Las directivas y las reglas de acceso creadas en Movilidad y seguridad básicas para Microsoft 365 Empresa Standard invalidarán Exchange ActiveSync las directivas de buzón de dispositivo móvil y las reglas de acceso de dispositivo creadas en el Centro de administración de Exchange. Después de inscribir un dispositivo en movilidad básica y seguridad para Microsoft 365 Empresa Standard, se omitirá cualquier directiva de buzón de dispositivo móvil o regla de acceso de dispositivo de Exchange ActiveSync aplicada al dispositivo. Para obtener más información sobre Exchange ActiveSync, [consulte Exchange ActiveSync en Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=524380)

## <a name="policy-settings-for-mobile-devices"></a>Configuración de directivas para dispositivos móviles

Si crea una directiva para bloquear el acceso con determinadas configuraciones activadas, se bloquea a los usuarios el acceso a los recursos de Microsoft 365 al usar una aplicación compatible que aparece en el control de acceso para el correo electrónico y los documentos de [Microsoft 365.](capabilities.md) 

La configuración que puede impedir que los usuarios accedan a los recursos de Microsoft 365 se encuentran en estas secciones:

- Seguridad

- Cifrado

- Descodificar

- Perfil de correo electrónico administrado  

Por ejemplo, el siguiente diagrama muestra lo que sucede cuando un usuario con un dispositivo inscrito no cumple una opción de seguridad de una directiva de administración de dispositivos móviles que se aplica a su dispositivo. El usuario inicia sesión en una aplicación que admite el control de acceso con movilidad y seguridad básicas. Se les bloquea el acceso a los recursos de Microsoft 365 en la aplicación hasta que su dispositivo cumpla con la configuración de seguridad.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Mensaje de cumplimiento de movilidad básica y seguridad":::

En las secciones siguientes se muestra la configuración de directiva que puede usar para ayudar a proteger y administrar los dispositivos móviles que se conectan a los recursos de la organización de Microsoft 365.

## <a name="security-settings"></a>Configuración de seguridad

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
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

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Requerir cifrado de datos en dispositivos<sup>1</sup> |No|Sí|Sí|

<sup>1</sup> Con Samsung Knox, también puede requerir cifrado en tarjetas de almacenamiento. 

## <a name="jail-broken-setting"></a>Configuración de descodificación 

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|El dispositivo no se puede descodificar ni descifrar |Sí|Sí|Sí|

## <a name="managed-email-profile-option"></a>Opción de perfil de correo electrónico administrado 

La siguiente opción puede impedir que los usuarios accedan a su correo electrónico de Microsoft 365 si usan un perfil de correo electrónico creado manualmente. Los usuarios de dispositivos iOS deben eliminar su perfil de correo electrónico creado manualmente para que puedan tener acceso a su correo electrónico. Después de eliminar el perfil, se crea automáticamente un nuevo perfil en el dispositivo. Para obtener instrucciones sobre cómo los usuarios finales pueden obtener cumplimiento, consulte [Se encontró una cuenta de correo electrónico existente.](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|El perfil de correo electrónico es administrado |Sí|No|No|

## <a name="cloud-settings"></a>Configuración de nube

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Requerir copia de seguridad cifrada |Sí|No|No|
|Bloquear copia de seguridad de la nube |Sí|No|No|
|Bloquear sincronización de documentos |Sí|No|No|
|Bloquear sincronización de fotos  |Sí|No|No|
|Permitir copia de seguridad de Google  |N/D|No|Sí|
|Permitir la sincronización automática de cuentas de Google  |N/D|No|Sí|

## <a name="system-settings"></a>Configuración del sistema

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear captura de pantalla |Sí|No|Sí|
|Bloquear el envío de datos de diagnóstico de dispositivos |Sí|No|Sí|

## <a name="application-settings"></a>Configuración de aplicaciones

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear las videoconferencias en el dispositivo |Sí|No|No|
|Bloquear el acceso a la tienda de aplicaciones |Sí|No|Sí|
|Requerir contraseña al acceder a la tienda de aplicaciones |No|Sí|Sí|

## <a name="device-capabilities-settings"></a>Configuración de las funcionalidades del dispositivo

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear conexión con almacenamiento extraíble |Sí|Sí|No|
|Bloquear conexión Bluetooth |Sí|Sí|No|

## <a name="additional-settings"></a>Otras configuraciones

Puede establecer la siguiente configuración de directiva adicional mediante los cmdlets de PowerShell del Centro de & seguridad y cumplimiento. Para obtener más información, vea [PowerShell del Centro & seguridad y cumplimiento.](https://docs.microsoft.com/powershell/exchange/scc-powershell)

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|
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

## <a name="settings-supported-by-windows"></a>Configuración compatible con Windows

Puedes administrar dispositivos Windows 10 inscribándolos como dispositivos móviles. Después de implementar una directiva aplicable, los usuarios con dispositivos Con Windows 10 tendrán que inscribirse en Movilidad básica y Seguridad la primera vez que usen la aplicación de correo electrónico integrada para acceder a su correo electrónico de Microsoft 365 (requiere una suscripción a Azure AD Premium).

La siguiente configuración es compatible con dispositivos Windows 10 inscritos como dispositivos móviles. Esta configuración no impedirá que los usuarios accedan a los recursos de Microsoft 365.

### <a name="security-settings"></a>Configuración de seguridad

- Requerir una contraseña alfanumérica

- Longitud mínima de la contraseña

- Número de errores de inicio de sesión antes borrar el dispositivo

- Minutos de inactividad antes de bloquear el dispositivo

- Expiración de contraseña (días)

- Recordar el historial de contraseñas y evitar la reutilización

>[!NOTE]
>La siguiente configuración que regula las contraseñas solo controla las cuentas locales de Windows. Las cuentas de Windows proporcionadas a través de unirse a un dominio o Azure Active Directory no se ven afectadas por esta configuración.

### <a name="system-settings"></a>Configuración del sistema

Bloquear el envío de datos de diagnóstico desde el dispositivo.

### <a name="additional-settings"></a>Otras configuraciones

Puede establecer esta configuración de directiva adicional mediante cmdlets de PowerShell:

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>Borrar de forma remota un dispositivo móvil

Si se pierde o se roba un dispositivo, puede quitar los datos confidenciales de la organización y ayudar a evitar el acceso a los recursos de la organización de Microsoft 365 realizando un borrado desde el Centro de seguridad & Cumplimiento > Administración de **dispositivos** de prevención de pérdida de  >  datos. Puede realizar un borrado selectivo para quitar solo los datos de la organización o un borrado completo para eliminar toda la información de un dispositivo y restaurar la configuración original.

Para obtener más información, consulte [Borrar un dispositivo móvil en Movilidad y seguridad básicas.](wipe-mobile-device.md)

## <a name="related-topics"></a>Temas relacionados

[Información general sobre movilidad y seguridad básicas para Microsoft 365](overview.md)

[Crear directivas de seguridad de dispositivos en Movilidad y seguridad básicas](create-device-security-policies.md)