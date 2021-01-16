---
title: Elegir entre movilidad básica y seguridad e Intune
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
description: La movilidad y la seguridad básicas forman parte de los planes de Microsoft 365.
ms.openlocfilehash: cfd1a68c313d1a1335490e2b8d6938de192fe3f3
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877097"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Elegir entre movilidad y seguridad básicas o Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) es un producto independiente que se incluye con determinados planes de Microsoft 365, mientras que Movilidad y seguridad básica forma parte de los planes de Microsoft 365. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilidad de movilidad y seguridad básicas e Intune
 
La movilidad básica y la seguridad y Intune se incluyen en una variedad de planes, que se describen en la tabla siguiente.

| Plan | Movilidad y seguridad básicas | Microsoft Intune |
|:-----|:-----|:-----|
|Aplicaciones de Microsoft 365|Sí|No|
|Microsoft 365 Empresa Básico|Sí|No|
|Microsoft 365 Empresa Estándar|Sí|No|
|Office 365 E1 |Sí|No|
|Office 365 E3 |Sí|No|
|Office 365 E5 |Sí|No|
|Microsoft 365 Empresa Premium |Sí|Sí|
|Primera línea 3 de Microsoft 365 |Sí|Sí|
|Microsoft 365 Enterprise E3 |Sí|Sí|
|Microsoft 365 Enterprise E5 |Sí|Sí|
|Microsoft 365 Educación A1 |Sí|Sí|
|Microsoft 365 Educación A3 |Sí|Sí|
|Microsoft 365 Educación A5 |Sí|Sí|
|Microsoft Intune |No|Sí|
|Enterprise Mobility & Security E3 |No|Sí|
|Enterprise Mobility & Security E5 |No|Sí|

>[!NOTE]
>No puedes empezar a usar movilidad y seguridad básicas si ya estás usando Microsoft Intune.

 Para obtener más información, vea las descripciones del servicio de la plataforma de [Microsoft 365 y Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Diferencias en las capacidades

Microsoft Intune y la movilidad básica y la seguridad integradas le dan la capacidad de administrar dispositivos móviles en su organización, pero existen diferencias clave en la funcionalidad, que se describen en la tabla siguiente.

>[!NOTE]
>Puede administrar usuarios y sus dispositivos móviles con Intune y movilidad y seguridad básicas en la misma organización de Microsoft 365 Empresa Standard configurando primero movilidad básica y seguridad *y,* a continuación, agregando Microsoft Intune . Esto te permite elegir movilidad y seguridad básicas o la solución intune más completa de características. Asignar una licencia de Intune para habilitar las características de Intune.

| Área de característica | Resaltados de características | Movilidad y seguridad básicas | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Administración de distintas plataformas del sistema operativo y variantes principales del modo de administración. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Cumplimiento de dispositivos|Establecer y administrar directivas de seguridad, como el bloqueo de PIN de nivel de dispositivo y la detección de jailbreak. |Limitaciones en dispositivos Android 9 y posteriores. Vea [los detalles.](capabilities.md) |Sí|
|Acceso condicional basado en el cumplimiento del dispositivo |Impedir que los dispositivos no compatibles accedan al correo electrónico corporativo y a los datos desde la nube. |No se admite en Windows 10.<br/>Limitado a controlar el acceso a Exchange Online, SharePoint Online y Outlook. |Sí |
|Configuración de dispositivos  |Configurar las opciones del dispositivo (por ejemplo, deshabilitar la cámara)|Conjunto limitado de opciones de configuración.|Sí|
|Cumplimiento de dispositivos  |Establecer y administrar directivas de seguridad, como el bloqueo de PIN de nivel de dispositivo y la detección de jailbreak. |Limitaciones en dispositivos Android 9 y posteriores. Vea [los detalles.](capabilities.md) |Sí|
|Perfiles de correo electrónico  |Aprovisionar un perfil de correo electrónico nativo en el dispositivo. |Sí|Sí|
|Perfiles wi-fi |Aprovisionar un perfil WiFi nativo en el dispositivo. |No|Sí|
|Perfiles de VPN |Aprovisionar un perfil de VPN nativo en el dispositivo. |No|Sí|
|Administración de aplicaciones básicas de movilidad y seguridad  |Implemente las aplicaciones de línea de negocio internas y desde las tiendas de aplicaciones a los usuarios. |No|Sí|
|Protección de aplicaciones móviles  |Permitir que los usuarios accedan de forma segura a la información corporativa con las aplicaciones móviles y de línea de negocio de Office que conocen, al tiempo que garantizan la seguridad de los datos al ayudar a restringir acciones como copiar, cortar, pegar y guardar como, solo a aquellas aplicaciones administradas aprobadas para datos corporativos. Funciona incluso si los dispositivos no están inscritos en movilidad y seguridad básicas. Consulta Proteger los datos de la aplicación mediante directivas mam. |No|Sí|
|Explorador administrado  |Habilitar una exploración web más segura con la aplicación perimetral. |No|Sí|
|Programa de inscripción táctil cero Autopilot) |Inscríbete un gran número de dispositivos corporativos, a la vez que simplificas la configuración del usuario. |No|Sí|
|||

Además de las características enumeradas en la tabla anterior, Movilidad y seguridad básica e Intune incluyen un conjunto de acciones remotas que envían comandos a dispositivos a través de Internet. Por ejemplo, puede quitar datos de Office del dispositivo de un empleado mientras deja datos personales en su lugar (retirar), quitar aplicaciones de Office del dispositivo de un empleado (borrar) o restablecer un dispositivo a su configuración de fábrica (borrado completo). 

Las acciones remotas básicas de movilidad y seguridad incluyen retirar, borrar y borrar completamente. Para obtener más información sobre las acciones básicas de movilidad y seguridad, vea [las funciones de Movilidad y seguridad básicas.](capabilities.md)

Con Intune tiene el siguiente conjunto de acciones:

-   Restablecimiento de Autopilot (solo Windows)
-  [Rotación de claves de](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   BitLocker (Solo Windows)
-  [Usar borrar, retirar o deshacer manualmente la inscripción del dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Deshabilitar loc de activación](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (solo iOS)
-  [Comienzo nuevo](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Solo Windows)
- [Examen completo](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Solo Windows 10)
- [Buscar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (solo iOS)
- [Modo perdido](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (Solo iOS)- [Examen rápido](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)
- [Control remoto para Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Bloqueo remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Cambiar el nombre del dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Restablecer reinicio del código](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [de](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   acceso (solo Windows)
-  Actualización Windows Defender inteligencia de seguridad (solo Windows)
-  Restablecimiento del PIN de Windows 10 (solo Windows)
-  [Enviar notificaciones personalizadas](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Sincronizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Para obtener más información sobre las acciones de Intune, consulte [la documentación de Microsoft Intune.](https://docs.microsoft.com/mem/intune/)
