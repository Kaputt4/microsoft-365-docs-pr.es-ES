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
ms.openlocfilehash: 75fef5bd70d7b8926d31b80f16952aa996bc625c
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580666"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Elegir entre la movilidad básica y la seguridad o Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) es un producto independiente incluido en determinados planes de Microsoft 365, mientras que la movilidad y la seguridad básicas forman parte de los planes de Microsoft 365. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilidad de movilidad y seguridad básica e Intune
 
Tanto la movilidad básica como la seguridad y la Intune se incluyen en diversos planes, que se describen en la tabla siguiente.

| Plan | Movilidad y seguridad básica | Microsoft Intune |
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
|Microsoft 365 Education a1 |Sí|Sí|
|Microsoft 365 Educación A3 |Sí|Sí|
|Microsoft 365 Educación A5 |Sí|Sí|
|Microsoft Intune |No|Sí|
|Enterprise Mobility & Security E3 |No|Sí|
|Enterprise Mobility & Security E5 |No|Sí|

>[!NOTE]
>No puede empezar a usar la movilidad y la seguridad básicas si ya está usando Microsoft Intune.

 Para obtener más información, consulte las [descripciones del servicio de la plataforma Microsoft 365 y Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). 

## <a name="differences-in-capabilities"></a>Diferencias en las capacidades

Microsoft Intune y la movilidad y la seguridad básicas integradas ofrecen la posibilidad de administrar dispositivos móviles en su organización, pero hay diferencias clave en la funcionalidad que se describen en la tabla siguiente.

>[!NOTE]
>Puede administrar los usuarios y sus dispositivos móviles con la tecnología de Intune y la movilidad básica y la seguridad en la misma organización de Microsoft 365 Business Standard *al configurar la movilidad y la seguridad básicas en primer lugar y, a continuación, agregar Microsoft Intune*. Esto le permite elegir la movilidad y la seguridad básicas o la solución de Intune con mayor número de características. Asigne una licencia de Intune para habilitar las características de Intune.

| Área de característica | Características destacadas | Movilidad y seguridad básica | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Administración de diferentes plataformas de sistemas operativos y variantes principales del modo de administración. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS, iPad OS|
|Cumplimiento de dispositivos|Establecer y administrar directivas de seguridad, como el bloqueo de PIN de nivel de dispositivo y la detección de jailbreak. |Limitaciones de los dispositivos Android 9 y versiones posteriores. Vea los [detalles](capabilities.md). |Sí|
|Acceso condicional según el cumplimiento del dispositivo |Evite que los dispositivos que no cumplen el acceso al correo electrónico y a los datos corporativos desde la nube. |No se admite en Windows 10.<br/>Se limita a controlar el acceso a Exchange Online, SharePoint Online y Outlook. |Sí |
|Configuración de dispositivos  |Configurar las opciones del dispositivo (por ejemplo, deshabilitar la cámara)|Conjunto limitado de opciones de configuración.|Sí|Cumplimiento de dispositivos|Establecer y administrar directivas de seguridad, como el bloqueo de PIN de nivel de dispositivo y la detección de jailbreak. |Limitaciones de los dispositivos Android 9 y versiones posteriores. Vea los [detalles](capabilities.md). |Sí|
|Perfiles de correo electrónico  |Aprovisione un perfil de correo electrónico nativo en el dispositivo. |Sí|Sí|
|Perfiles de WiFi |Aprovisione un perfil WiFi nativo en el dispositivo. |No|Sí|
|Perfiles de VPN |Aprovisione un perfil de VPN nativo en el dispositivo. |No|Sí|
|Administración de aplicaciones de MDM |Implemente las aplicaciones de línea de negocio internas y de las tiendas de aplicaciones a los usuarios. |No|Sí|
|MAM |Asegúrese de que los usuarios tengan acceso seguro a la información de la empresa con las aplicaciones móviles y de línea de negocio de Office, ayudando a restringir acciones como copiar, cortar, pegar y guardar como a solo aquellas aplicaciones aprobadas para los datos corporativos. |No|Sí|
|Managed Browser  |Habilitar la exploración Web más segura con la aplicación perimetral. |No|Sí|
|Programas de inscripción sin interacción automática piloto) |Inscriba un gran número de dispositivos de propiedad corporativa, a la vez que simplifica la configuración del usuario. |No|Sí|
|||

Además de las características enumeradas en la tabla anterior, la movilidad básica y la seguridad y Intune incluyen un conjunto de acciones remotas que envían comandos a los dispositivos a través de Internet. Por ejemplo, puede quitar datos de Office del dispositivo de un empleado y dejar los datos personales en su ubicación (retirar), quitar aplicaciones de Office del dispositivo de un empleado (barrido) o restablecer un dispositivo a su configuración de fábrica (borrado completo). 

Entre las acciones de seguridad y movilidad básicas se incluyen la retirada, el borrado y el borrado completo. Para obtener más información sobre las acciones básicas de seguridad y movilidad, vea [Capabilities of Basic Mobility and Security](capabilities.md).

Con Intune tiene el siguiente conjunto de acciones:

-   Restablecimiento del piloto automático (solo Windows
-  Rotación de clave de [BitLocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Solo Windows)
-  [Usar el borrado, retirar o cancelar la inscripción manual del dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Deshabilitar el Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   de activación (solo iOS)
-  [Comienzo fresco](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Solo Windows)
- [Examen completo](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Solo Windows 10)
- [Buscar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (solo iOS)
- [Modo perdido](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (solo iOS): [examen rápido](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)
- [Control remoto para Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Bloqueo remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Cambiar el nombre del dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Restablecer código](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) de acceso [reinicio](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (solo Windows)
-  Actualización de la inteligencia de seguridad de Windows Defender (solo Windows)
-  Restablecimiento de PIN de Windows 10 (solo Windows)
-  [Enviar notificaciones personalizadas](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, so iPad)
-  [Sincronizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Para obtener más información sobre las acciones de Intune, consulte la [documentación de Microsoft Intune](https://docs.microsoft.com/mem/intune/).
