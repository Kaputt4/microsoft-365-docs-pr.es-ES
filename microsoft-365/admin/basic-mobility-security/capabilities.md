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
ms.openlocfilehash: a5f20b2999a1a54070433560904e9535a4d1524a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228284"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Capacidades de Movilidad y seguridad básicas

La movilidad y la seguridad básicas pueden ayudarle a proteger y administrar dispositivos móviles como iPhones, iPads, Androides y teléfonos Windows usados por usuarios con licencia Microsoft 365 en su organización. Puedes crear directivas de administración de dispositivos móviles con configuraciones que puedan ayudar a controlar el acceso a los documentos y correo electrónico Microsoft 365 de la organización para dispositivos móviles y aplicaciones compatibles. Si un dispositivo se pierde o se lo roban, puede borrarlo de forma remota para quitar la información confidencial de la organización.

## <a name="supported-devices"></a>Dispositivos admitidos

Puedes usar Movilidad y seguridad básicas para proteger y administrar los siguientes dispositivos.

- iOS 11.0 o versiones posteriores

- Android 5.0 o versiones<sup>posteriores 3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> El control de acceso Windows 8.1 dispositivos RT está limitado a Exchange ActiveSync.

<sup>2</sup> El control de Windows 10 requiere una suscripción que incluya Azure AD Premium y el dispositivo debe unirse a Azure Active Directory.

<sup>3</sup> Después de junio de 2020, las versiones de Android posteriores al 9 no pueden administrar la configuración de contraseña excepto en dispositivos Samsung Knox.

> [!NOTE]
> Los dispositivos ya inscritos con versiones anteriores del sistema operativo siguen funcionando aunque las capacidades pueden cambiar sin previo aviso.

Si los usuarios de la organización usan dispositivos móviles que no son compatibles con La movilidad y la seguridad básicas, es posible que quieras bloquear el acceso Exchange ActiveSync la aplicación Microsoft 365 un correo electrónico para esos dispositivos, para ayudar a que los datos de la organización sean más seguros. Para ver los pasos para bloquear Exchange ActiveSync, consulta [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Control de acceso para Microsoft 365 correo electrónico y documentos

Las aplicaciones admitidas para los distintos tipos de dispositivos móviles de la siguiente tabla piden a los usuarios que se inscriban en Movilidad y seguridad básicas donde hay una nueva directiva de administración de dispositivos móviles que se aplica al dispositivo de un usuario y el usuario no ha inscrito previamente el dispositivo. Si el dispositivo de un usuario no cumple una directiva, en función de cómo configure la directiva, es posible que un usuario no tenga acceso Microsoft 365 los recursos de estas aplicaciones o que tenga acceso, pero Microsoft 365 informe de una infracción de directiva.

|**Producto**|**iOS 10.0 o posterior**|**Android 5.0 o posterior**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync incluye correo electrónico integrado y aplicaciones de terceros, como TouchDown, que usan Exchange ActiveSync versión 14.1 o posterior. |Correo |Correo electrónico |
|**Office**   y  **OneDrive para la Empresa** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**En teléfonos y tabletas:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Solamente en teléfonos:** <br/> Office Mobile |

> [!NOTE]
>
> - La compatibilidad con iOS 10.0 y versiones posteriores incluye iPhone y iPad dispositivos.
> - La administración de dispositivos del sistema operativo BlackBerry no es compatible con seguridad básica y movilidad. Usa BlackBerry Business Cloud Services (BBCS) de BlackBerry para administrar dispositivos blackBerry OS. Los dispositivos Blackberry que ejecutan el sistema operativo Android se admiten como dispositivos Android estándar
> - No se pedirá a los usuarios que se inscriban y no se les bloqueará ni se les notifica por infracción de directivas si usan el explorador móvil para acceder Microsoft 365 SharePoint sitios, documentos en Office Online o correo electrónico en Outlook Web App.

En el siguiente diagrama se muestra lo que sucede cuando un usuario con un dispositivo nuevo inicia sesión en una aplicación que admite el control de acceso con Movilidad y seguridad básicas. El usuario no tiene acceso a Microsoft 365 en la aplicación hasta que inscribe su dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Control de acceso básico de movilidad y seguridad":::

> [!NOTE]
> Las directivas y las reglas de acceso creadas en Basic Mobility and Security for Microsoft 365 Empresa Estándar invalidarán Exchange ActiveSync directivas de buzón de dispositivo móvil y reglas de acceso de dispositivos creadas en el centro de administración de Exchange dispositivo. Una vez que un dispositivo se inscribe en Movilidad básica y seguridad para Microsoft 365 Empresa Estándar, se omitirá cualquier directiva de buzón de dispositivo móvil o regla de acceso de dispositivo Exchange ActiveSync aplicada al dispositivo. Para obtener más información sobre Exchange ActiveSync, vea [Exchange ActiveSync en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="policy-settings-for-mobile-devices"></a>Configuración de directivas para dispositivos móviles

Si crea una directiva para bloquear el acceso con determinadas opciones activadas, los usuarios no podrán acceder Microsoft 365 los recursos de Microsoft 365 al usar una aplicación compatible que se muestra en Control de acceso para documentos y correo electrónico de [Microsoft 365.](capabilities.md)

La configuración que puede impedir que los usuarios accedan Microsoft 365 recursos se encuentran en estas secciones:

- Seguridad

- Cifrado

- Descodificar

- Perfil de correo electrónico administrado

Por ejemplo, el siguiente diagrama muestra lo que sucede cuando un usuario con un dispositivo inscrito no cumple una opción de seguridad de una directiva de administración de dispositivos móviles que se aplica a su dispositivo. El usuario inicia sesión en una aplicación que admite el control de acceso con Movilidad y seguridad básicas. Se les bloquea el acceso Microsoft 365 recursos de la aplicación hasta que su dispositivo cumpla con la configuración de seguridad.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Mensaje de cumplimiento básico de movilidad y seguridad":::

En las secciones siguientes se enumera la configuración de directiva que puede usar para ayudar a proteger y administrar dispositivos móviles que se conectan a los recursos Microsoft 365 organización.

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
|Requerir cifrado de datos en<sup>dispositivos 1</sup> |No|Sí|Sí|

<sup>1</sup> Con Samsung Knox, también puede requerir cifrado en tarjetas de almacenamiento.

## <a name="jail-broken-setting"></a>Configuración de descodificación

|**Nombre de la configuración**|**iOS 7.1 y versiones posteriores**|**Android 5 y versiones posteriores**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|El dispositivo no se puede descodificar ni descifrar |Sí|Sí|Sí|

## <a name="managed-email-profile-option"></a>Opción de perfil de correo electrónico administrado

La siguiente opción puede impedir que los usuarios tengan acceso Microsoft 365 correo electrónico si usan un perfil de correo electrónico creado manualmente. Los usuarios de dispositivos iOS deben eliminar su perfil de correo electrónico creado manualmente para que puedan tener acceso a su correo electrónico. Después de eliminar el perfil, se crea automáticamente un nuevo perfil en el dispositivo. Para obtener instrucciones sobre cómo los usuarios finales pueden cumplir con las normas, consulte [Se encontró una cuenta de correo electrónico existente.](/intune-user-help/existing-company-email-account-found)

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

Puede establecer la siguiente configuración de directiva adicional mediante cmdlets de PowerShell del Centro de & seguridad. Para obtener más información, vea [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).

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

Puedes administrar Windows 10 dispositivos mediante la inscripción como dispositivos móviles. Una vez implementada una directiva aplicable, los usuarios con dispositivos Windows 10 tendrán que inscribirse en Movilidad básica y seguridad la primera vez que usen la aplicación de correo electrónico integrada para acceder Microsoft 365 su correo electrónico (requiere una suscripción premium de Azure AD).

La siguiente configuración es compatible con Windows 10 que están inscritos como dispositivos móviles. Esta configuración no impedirá que los usuarios accedan a Microsoft 365 recursos.

### <a name="security-settings"></a>Configuración de seguridad

- Requerir una contraseña alfanumérica

- Longitud mínima de la contraseña

- Número de errores de inicio de sesión antes borrar el dispositivo

- Minutos de inactividad antes de bloquear el dispositivo

- Expiración de contraseña (días)

- Recordar el historial de contraseñas y evitar la reutilización

> [!NOTE]
> La siguiente configuración que regula las contraseñas solo controla las Windows locales. Windows cuentas proporcionadas a través de unirse a un dominio o Azure Active Directory no se ven afectadas por esta configuración.

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

Si se pierde o se roba un dispositivo, puedes quitar datos confidenciales de la organización y ayudar a impedir el acceso a los recursos de la organización de Microsoft 365 realizando una eliminación desde el Centro de seguridad & cumplimiento > Prevención de pérdida de datos Administración de **dispositivos**  >  . Puede realizar un borrado selectivo para quitar solo los datos de la organización o un borrado completo para eliminar toda la información de un dispositivo y restaurar la configuración original.

Para obtener más información, [consulta Borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-content"></a>Contenido relacionado

[Información general sobre movilidad básica y seguridad para Microsoft 365](overview.md) (artículo)\
[Crear directivas de seguridad de dispositivos en Movilidad básica y seguridad](create-device-security-policies.md) (artículo)