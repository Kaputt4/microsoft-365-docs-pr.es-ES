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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: Basic Mobility and Security puede ayudarle a proteger y administrar sus dispositivos móviles.
ms.openlocfilehash: b0e303af27d731cf3dba3af13019b3b993e52bfe
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64937771"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Capacidades de Movilidad y seguridad básicas

Basic Mobility and Security puede ayudarle a proteger y administrar dispositivos móviles como iPhone, iPads, Android y teléfonos Windows usados por los usuarios con licencia Microsoft 365 de su organización. Puede crear directivas de administración de dispositivos móviles con una configuración que pueda ayudar a controlar el acceso al correo electrónico Microsoft 365 de la organización y a los documentos para dispositivos móviles y aplicaciones compatibles. Si un dispositivo se pierde o se lo roban, puede borrarlo de forma remota para quitar la información confidencial de la organización.

## <a name="supported-operating-systems"></a>Sistemas operativos compatibles 

Siga la guía de sistemas operativos Microsoft Intune para los sistemas operativos mínimos admitidos para dispositivos por Basic Mobility and Security. Para obtener más información, consulte [Intune sistemas operativos compatibles](/mem/intune/fundamentals/supported-devices-browsers).

Puede usar Basic Mobility and Security para proteger y administrar los siguientes dispositivos.

- iOS
- Android (incluido Samsung Knox)<sup>1</sup>
- Windows <sup>2, 3</sup>

<sup>1</sup> Después de junio de 2020, las versiones de Android posteriores a 9 no pueden administrar la configuración de contraseñas, excepto en dispositivos Samsung Knox.

<sup>2</sup> El control de acceso para Windows 8.1 dispositivos RT está limitado a Exchange ActiveSync.

<sup>3</sup> El control de acceso para Windows 10 requiere una suscripción que incluya Azure AD Premium y el dispositivo debe estar unido a Azure Active Directory.

> [!NOTE]
> Los dispositivos ya inscritos con versiones anteriores del sistema operativo siguen funcionando, aunque es posible que las funcionalidades cambien sin previo aviso.

Si los usuarios de su organización usan dispositivos móviles que no son compatibles con Basic Mobility and Security, es posible que desee bloquear Exchange ActiveSync acceso de la aplicación a Microsoft 365 correo electrónico para esos dispositivos, para ayudar a que los datos de su organización sean más seguros. Para ver los pasos para bloquear Exchange ActiveSync, consulte [Administración de la configuración de acceso a dispositivos en Movilidad y seguridad básicas](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Control de acceso para Microsoft 365 correo electrónico y documentos

Las aplicaciones admitidas para los distintos tipos de dispositivos móviles de la tabla siguiente solicitan a los usuarios que se inscriban en Basic Mobility and Security, donde hay una nueva directiva de administración de dispositivos móviles que se aplica al dispositivo de un usuario y el usuario no ha inscrito previamente el dispositivo. Si el dispositivo de un usuario no cumple con una directiva, en función de cómo configure la directiva, es posible que se bloquee a un usuario el acceso a Microsoft 365 recursos en estas aplicaciones o que tenga acceso, pero Microsoft 365 informe de una infracción de directiva.

|Producto|iOS|Android|
|---|---|---|
|**Exchange** Exchange ActiveSync incluye aplicaciones integradas de correo electrónico y de terceros, como TouchDown, que usan Exchange ActiveSync versión 14.1 o posterior.|Correo|Correo electrónico|
|**Office** y **OneDrive para la Empresa**|Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**En teléfonos y tabletas**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Solamente en teléfonos:** <br/> Office Mobile|

> [!NOTE]
>
> - La compatibilidad con iOS 10.0 y versiones posteriores incluye dispositivos iPhone y iPad.
> - La administración de dispositivos BlackBerry OS no es compatible con basic security and mobility. Use BlackBerry Business Cloud Services (BBCS) de BlackBerry para administrar dispositivos BlackBerry OS. Los dispositivos Blackberry que ejecutan el sistema operativo Android se admiten como dispositivos Android estándar.
> - No se pedirá a los usuarios que se inscriban y no se les bloqueará ni se notificará por infracción de directiva si usan el explorador móvil para acceder a Microsoft 365 SharePoint sitios, documentos en Office Online o correo electrónico en Outlook Web App.

En el diagrama siguiente se muestra lo que sucede cuando un usuario con un nuevo dispositivo inicia sesión en una aplicación que admite el control de acceso con Basic Mobility and Security. Se impide que el usuario acceda a Microsoft 365 recursos de la aplicación hasta que inscriba su dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Control de acceso básico de movilidad y seguridad.":::

> [!NOTE]
> Las directivas y las reglas de acceso creadas en Basic Mobility and Security for Microsoft 365 Empresa Estándar invalidarán Exchange ActiveSync directivas de buzón de dispositivo móvil y reglas de acceso a dispositivos creadas en el centro de administración de Exchange. Después de inscribir un dispositivo en Basic Mobility and Security for Microsoft 365 Empresa Estándar, se omitirá cualquier Exchange ActiveSync directiva de buzón de dispositivo móvil o regla de acceso de dispositivo aplicada al dispositivo. Para más información sobre Exchange ActiveSync, consulte [Exchange ActiveSync en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="policy-settings-for-mobile-devices"></a>Configuración de directivas para dispositivos móviles

Si crea una directiva para bloquear el acceso con cierta configuración activada, los usuarios no podrán acceder a Microsoft 365 recursos al usar una aplicación compatible que aparece en [Control de acceso para Microsoft 365 correo electrónico y documentos](capabilities.md).

La configuración que puede impedir que los usuarios accedan a Microsoft 365 recursos se encuentra en estas secciones:

- Seguridad

- Cifrado

- Descodificar

- Perfil de correo electrónico administrado

Por ejemplo, el siguiente diagrama muestra lo que sucede cuando un usuario con un dispositivo inscrito no cumple una opción de seguridad de una directiva de administración de dispositivos móviles que se aplica a su dispositivo. El usuario inicia sesión en una aplicación que admite el control de acceso con Basic Mobility and Security. Se les impide acceder a Microsoft 365 recursos de la aplicación hasta que el dispositivo cumpla con la configuración de seguridad.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Mensaje de cumplimiento básico de movilidad y seguridad.":::

En las secciones siguientes se muestra la configuración de directiva que puede usar para ayudar a proteger y administrar dispositivos móviles que se conectan a los recursos de la organización Microsoft 365.

## <a name="security-settings"></a>Configuración de seguridad

|Nombre de la opción de configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|Requerir contraseña|Sí|Sí|Sí|
|Evitar contraseña simple|Sí|No|No|
|Requerir una contraseña alfanumérica|Sí|No|No|
|Longitud mínima de la contraseña|Sí|Sí|Sí|
|Número de errores de inicio de sesión antes borrar el dispositivo|Sí|Sí|Sí|
|Minutos de inactividad antes de bloquear el dispositivo|Sí|Sí|Sí|
|Expiración de contraseña (días)|Sí|Sí|Sí|
|Recordar el historial de contraseñas y evitar la reutilización|Sí|Sí|Sí|

## <a name="encryption-settings"></a>Configuración de cifrado

|Nombre de la configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|Requerir cifrado de datos en <sup>dispositivos1</sup>|No|Sí|Sí|

<sup>1</sup> Con Samsung Knox, también puede requerir cifrado en tarjetas de almacenamiento.

## <a name="jail-broken-setting"></a>Configuración de descodificación

|Nombre de la configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|El dispositivo no se puede descodificar ni descifrar|Sí|Sí|Sí|

## <a name="managed-email-profile-option"></a>Opción de perfil de correo electrónico administrado

La siguiente opción puede impedir que los usuarios accedan a su correo electrónico Microsoft 365 si usan un perfil de correo electrónico creado manualmente. Los usuarios de dispositivos iOS deben eliminar su perfil de correo electrónico creado manualmente para que puedan tener acceso a su correo electrónico. Después de eliminar el perfil, se crea automáticamente un nuevo perfil en el dispositivo. Para obtener instrucciones sobre cómo los usuarios finales pueden ser compatibles, consulte [Se encontró una cuenta de correo electrónico existente](/intune-user-help/existing-company-email-account-found).

|Nombre de valor de configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|El perfil de correo electrónico es administrado|Sí|No|No|

## <a name="cloud-settings"></a>Configuración de nube

|Nombre de la configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|Requerir copia de seguridad cifrada|Sí|No|No|
|Bloquear copia de seguridad de la nube|Sí|No|No|
|Bloquear sincronización de documentos|Sí|No|No|
|Bloquear sincronización de fotos|Sí|No|No|
|Permitir copia de seguridad de Google|N/D|No|Sí|
|Permitir la sincronización automática de la cuenta de Google|N/D|No|Sí|

## <a name="system-settings"></a>Configuración del sistema

|Nombre de la configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|Bloquear captura de pantalla|Sí|No|Sí|
|Bloquear el envío de datos de diagnóstico de dispositivos|Sí|No|Sí|

## <a name="application-settings"></a>Configuración de aplicaciones

|Nombre de la configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|Bloquear las videoconferencias en el dispositivo|Sí|No|No|
|Bloquear el acceso a la tienda de aplicaciones|Sí|No|Sí|
|Requerir contraseña al acceder a la tienda de aplicaciones|No|Sí|Sí|

## <a name="device-capabilities-settings"></a>Configuración de las funcionalidades del dispositivo

|Nombre de la configuración|iOS|Android|Samsung Knox|
|---|---|---|---|
|Bloquear conexión con almacenamiento extraíble|Sí|Sí|No|
|Bloquear conexión Bluetooth|Sí|Sí|No|

## <a name="additional-settings"></a>Otras configuraciones

Puede establecer la siguiente configuración de directiva adicional mediante cmdlets de PowerShell de Security & Compliance Center. Para obtener más información, consulte [PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/scc-powershell).

|Nombre de valor de configuración|iOS|Android|
|---|---|---|
|CameraEnabled|Sí|Sí|
|RegionRatings|Sí|No|
|MoviesRatings|Sí|No|
|TVShowsRating|Sí|No|
|AppsRatings|Sí|No|
|AllowVoiceDialing|Sí|No|
|AllowVoiceAssistant|Sí|No|
|AllowAssistantWhileLocked|Sí|No|
|AllowPassbookWhileLocked|Sí|No|
|MaxPasswordGracePeriod|Sí|No|
|PasswordQuality|No|Sí|
|SystemSecurityTLS|Sí|No|
|WLANEnabled|No|No|

## <a name="settings-supported-by-windows"></a>Configuración admite Windows

Puede administrar Windows 10 dispositivos inscribiéndolos como dispositivos móviles. Una vez implementada una directiva aplicable, los usuarios con dispositivos Windows 10 deberán inscribirse en Basic Mobility and Security la primera vez que usen la aplicación de correo electrónico integrada para acceder a su correo electrónico Microsoft 365 (requiere Azure AD suscripción Premium).

La siguiente configuración es compatible con los dispositivos Windows 10 inscritos como dispositivos móviles. Esta configuración no impedirá que los usuarios accedan a Microsoft 365 recursos.

### <a name="security-settings"></a>Configuración de seguridad

- Requerir una contraseña alfanumérica

- Longitud mínima de la contraseña

- Número de errores de inicio de sesión antes borrar el dispositivo

- Minutos de inactividad antes de bloquear el dispositivo

- Expiración de contraseña (días)

- Recordar el historial de contraseñas y evitar la reutilización

> [!NOTE]
> La siguiente configuración que regula las contraseñas solo controla las cuentas de Windows locales. Windows cuentas proporcionadas mediante la unión a un dominio o Azure Active Directory no se ven afectadas por esta configuración.

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

Si se pierde o se roba un dispositivo, puede quitar datos confidenciales de la organización y ayudar a evitar el acceso a los recursos de la organización Microsoft 365 realizando un borrado del portal  >  de **cumplimiento de Microsoft PurviewAdministración** de dispositivos de **pérdida** >  de **datos.** Puede realizar un borrado selectivo para quitar solo los datos de la organización o un borrado completo para eliminar toda la información de un dispositivo y restaurar la configuración original.

Para obtener más información, consulte [Borrado de un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-content"></a>Contenido relacionado

[Información general sobre la movilidad y la seguridad básicas para Microsoft 365](overview.md) (artículo)\
[Creación de directivas de seguridad de dispositivos en Basic Mobility and Security](create-device-security-policies.md) (artículo)
