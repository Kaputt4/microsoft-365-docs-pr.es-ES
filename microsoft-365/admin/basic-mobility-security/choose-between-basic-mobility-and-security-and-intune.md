---
title: Elegir entre la movilidad básica y la seguridad y Intune
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
description: La movilidad y la seguridad básica forman parte de los planes de Microsoft 365.
ms.openlocfilehash: df52d500c945275b62170ab16260f0c019340f73
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429931"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>Elegir entre la movilidad básica y la seguridad y Intune

Microsoft Intune es un producto independiente incluido en determinados planes de Microsoft 365, mientras que la movilidad básica & seguridad forma parte de los planes de Microsoft 365. Ambos se incluyen en diversos planes, que se describen en la tabla siguiente.

|**Planear**|**Movilidad y seguridad básica**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Aplicaciones de Microsoft 365|Sí|No|
|Microsoft 365 Empresa Básico|Sí|No|
|Microsoft 365 Empresa Estándar|Sí|No|
|Office 365 E1 |Sí|No|
|Office 365 E3 |Sí|No|
|Office 365 E5 |Sí|No|
|Microsoft 365 Empresa Premium |Sí|Sí|
|Microsoft 365 Firstline 3 |Sí|Sí|
|Microsoft 365 Enterprise E3 |Sí|Sí|
|Microsoft 365 Enterprise E5 |Sí|Sí|
|Microsoft 365 Eductation a1 |Sí|Sí|
|Microsoft 365 Educación A3 |Sí|Sí|
|Microsoft 365 Educación A5 |Sí|Sí|
|Microsoft Intune |No|Sí|
|Enterprise Mobility & Security E3 |No|Sí|
|Enterprise Mobility & Security E5 |No|Sí|

>[!NOTE]
>No puede empezar a usar la movilidad y la seguridad básicas si ya está usando Microsoft Intune.

## <a name="differences-in-capabilities"></a>Diferencias en las capacidades

Microsoft Intune y la movilidad y la seguridad básicas integradas ofrecen la posibilidad de administrar dispositivos móviles en su organización, pero hay diferencias clave en la funcionalidad que se describen en la tabla siguiente.

>[!NOTE]
>Puede administrar los usuarios y sus dispositivos móviles con la tecnología de Intune y la movilidad básica y la seguridad en la misma organización de Microsoft 365 Business Standard al configurar la movilidad y la seguridad básicas en primer lugar y, a continuación, agregar Microsoft Intune. Esto le permite elegir si desea administrar los dispositivos de un usuario con la movilidad y la seguridad básicas o la solución de Intune con mayor número de características. En el modo, la asignación de licencia determina el servicio con el que se inscribe el dispositivo. Asigne una licencia de Intune para habilitar las características solo de Intune.

|**Área de característica**|**Características destacadas**|**Movilidad y seguridad básica**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Distintas plataformas de sistema operativo y variantes del modo de administración principales. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS<br/>iPad OS|
|Cumplimiento de dispositivos|Establecer y administrar directivas de seguridad, como el bloqueo de PIN de nivel de dispositivo y la detección de jailbreak. |Limitaciones de los dispositivos Android 9 y versiones posteriores. Para obtener más información, consulte [capacidades básicas de movilidad y seguridad](capabilities.md).|Sí|
|Acceso condicional según el cumplimiento del dispositivo |Evite que los dispositivos que no cumplen el acceso al correo electrónico y a los datos corporativos desde la nube. |-No es compatible con Windows 10.<br/>-Limitado a controlar el acceso a los servicios de Outlook, SharePoint Online y Exchange Online. |No|
|Configuración de dispositivos  |Configure las opciones del dispositivo (por ejemplo, deshabilitar la cámara). |Conjunto limitado de opciones de configuración.Para obtener más información, consulte [capacidades básicas de movilidad y seguridad](capabilities.md). |Sí|
|Acciones remotas  |Enviar comandos a dispositivos a través de Internet. Por ejemplo, quitar datos de Office del dispositivo de un empleado y dejar los datos personales en su ubicación (retirar). |Retirar<br/>Barrido<br/>Eliminar|-Restablecimiento del piloto automático (solo Windows)<br/>- Rotación de clave de [BitLocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Solo Windows)<br/>- [Eliminar](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [Deshabilitar el Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   de activación (solo iOS)<br/>- [Comienzo fresco](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Solo Windows)<br/>- [Examen completo](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Solo Windows 10)<br/>- [Buscar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (solo iOS)<br/>- [Modo perdido](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (solo iOS)<br/>- [Examen rápido](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)<br/>- [Control remoto para Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [Bloqueo remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [Cambiar el nombre del dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [Restablecer código de acceso](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [Reiniciar](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Solo Windows)<br/>- [Dar](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-Actualizar la inteligencia de seguridad de Windows Defender (solo Windows)<br/>-Restablecimiento del PIN para Windows 10 (solo Windows)<br/>- [Borra](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [Enviar notificaciones personalizadas](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, so iPad)<br/>- [Sincronizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|Perfiles de correo electrónico  |Aprovisione un perfil de correo electrónico nativo en el dispositivo. |Sí|Sí|
|Perfiles de WIFI |Aprovisione un perfil WIFI nativo en el dispositivo. |No|Sí|
|Perfiles de VPN |Aprovisione un perfil de VPN nativo en el dispositivo. |No|Sí|
|Administración de aplicaciones de MDM  |Implemente las aplicaciones de línea de negocio internas y de las tiendas de aplicaciones a los usuarios. |No|Sí|
|Protección de aplicaciones móviles  |Habilite a los usuarios para que tengan acceso seguro a la información de la empresa con las aplicaciones móviles de Office y de línea de negocio que sepan, a la vez que garantizan la seguridad de los datos al ayudar a restringir acciones como copiar, cortar, pegar y guardar como solo para las aplicaciones que se han administrado para los datos corporativos. Funciona incluso si los dispositivos no están inscritos en MDM. Consulte proteger datos de aplicaciones mediante directivas de MAM. |No|Sí|
|Managed Browser  |Habilitar la exploración Web más segura con la aplicación perimetral. |No|Sí|
|Programas de inscripción sin interacción |Inscriba gran cantidad de dispositivos de propiedad corporativa, a la vez que simplifica la configuración del usuario. |No|Sí|
