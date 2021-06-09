---
title: Elegir entre Movilidad básica y seguridad e Intune
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
description: La movilidad y la seguridad básicas forman parte de los Microsoft 365 de seguridad.
ms.openlocfilehash: b7b1d229e87a313a9567daed87f03452b1925a65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904269"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Elegir entre Movilidad básica y seguridad o Intune

[Microsoft Intune](/mem/intune/) es un producto independiente incluido con determinados planes de Microsoft 365, mientras que Basic Mobility and Security forma parte de los planes Microsoft 365 seguridad.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilidad de movilidad básica y seguridad e Intune

Tanto Movilidad básica como Seguridad e Intune se incluyen en una variedad de planes, que se describen en la tabla siguiente.

| Planear | Movilidad y seguridad básicas | Microsoft Intune |
|:-----|:-----|:-----|
|Aplicaciones de Microsoft 365|Sí|No|
|Microsoft 365 Empresa Básico|Sí|No|
|Microsoft 365 Empresa Estándar|Sí|No|
|Office 365 E1 |Sí|No|
|Office 365 E3 |Sí|No|
|Office 365 E5 |Sí|No|
|Microsoft 365 Empresa Premium |Sí|Sí|
|Microsoft 365 Primera línea 3 |Sí|Sí|
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

 Para obtener más información, [vea Microsoft 365 y Office 365 descripciones del servicio de plataforma.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Diferencias en las capacidades

Microsoft Intune y seguridad básicas integradas le dan la capacidad de administrar dispositivos móviles en su organización, pero hay diferencias clave en la funcionalidad, descrita en la tabla siguiente.

>[!NOTE]
>Puede administrar usuarios y sus dispositivos móviles con Intune y Movilidad básica y Seguridad en la misma organización de Microsoft 365 Empresa Estándar configurando primero Movilidad y seguridad básicas *y,* a continuación, agregando Microsoft Intune . Esto te permite elegir Movilidad y seguridad básicas o la solución de Intune más rica en características. Asignar una licencia de Intune para habilitar las características de Intune.

| Área de característica | Aspectos destacados de la característica | Movilidad y seguridad básicas | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Administración de diferentes plataformas del sistema operativo y variantes principales del modo de administración. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad sistema operativo|
|Cumplimiento de dispositivos|Establece y administra directivas de seguridad, como bloqueo de PIN de nivel de dispositivo y detección de jailbreak. |Limitaciones en dispositivos Android 9 y posteriores. Vea [los detalles](capabilities.md). |Sí|
|Acceso condicional basado en el cumplimiento de dispositivos |Impedir que los dispositivos que no son compatibles tengan acceso al correo electrónico corporativo y a los datos desde la nube. |No se admite en Windows 10.<br/>Limitado a controlar el acceso a Exchange Online, SharePoint Online y Outlook. |Sí |
|Configuración de dispositivos  |Configurar la configuración del dispositivo (por ejemplo, deshabilitar la cámara)|Conjunto limitado de opciones.|Sí|
|Cumplimiento de dispositivos  |Establece y administra directivas de seguridad, como bloqueo de PIN de nivel de dispositivo y detección de jailbreak. |Limitaciones en dispositivos Android 9 y posteriores. Vea [los detalles](capabilities.md). |Sí|
|Perfiles de correo electrónico  |Aprovisionar un perfil de correo electrónico nativo en el dispositivo. |Sí|Sí|
|Perfiles WiFi |Aprovisionar un perfil WiFi nativo en el dispositivo. |No|Sí|
|Perfiles vpn |Aprovisionar un perfil vpn nativo en el dispositivo. |No|Sí|
|Administración de aplicaciones móviles  |Implemente las aplicaciones de línea de negocio internas y de las tiendas de aplicaciones a los usuarios. |No|Sí|
|Protección de aplicaciones móviles  |Permitir que los usuarios accedan de forma segura a la información corporativa con las aplicaciones móviles y de línea de negocio de Office que conocen, al tiempo que garantizan la seguridad de los datos al ayudar a restringir acciones como copiar, cortar, pegar y guardar como, solo a aquellas aplicaciones administradas aprobadas para datos corporativos. Funciona incluso si los dispositivos no están inscritos en Movilidad y seguridad básicas. Consulta Proteger los datos de la aplicación mediante directivas mam. |No|Sí|
|Explorador administrado  |Habilitar una exploración web más segura con la aplicación perimetral. |No|Sí|
|Programas de inscripción táctil cero (AutoPilot) |Inscriba un gran número de dispositivos de propiedad corporativa, a la vez que simplifica la configuración del usuario. |No|Sí|
|||

Además de las características enumeradas en la tabla anterior, movilidad básica y seguridad e Intune incluyen un conjunto de acciones remotas que envían comandos a dispositivos a través de Internet. Por ejemplo, puedes quitar Office datos del dispositivo de un empleado mientras dejas los datos personales en su lugar (retirar), quitar aplicaciones Office del dispositivo de un empleado (borrar) o restablecer un dispositivo a su configuración de fábrica (borrado total). 

Las acciones remotas básicas de movilidad y seguridad incluyen retirar, borrar y borrar completamente. Para obtener más información sobre las acciones básicas de movilidad y seguridad, vea [capabilities of Basic Mobility and Security](capabilities.md).

Con Intune tiene el siguiente conjunto de acciones:

-   Restablecimiento de piloto automático (Windows solo
-  [Rotación de teclas de Bitlocker](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (solo Windows)
-  [Usar borrar, retirar o desenrollar manualmente el dispositivo](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Deshabilitar loc de activación](/mem/intune/remote-actions/device-activation-lock-disable)   (solo iOS)
-  [Inicio nuevo](/mem/intune/remote-actions/device-fresh-start)   (solo Windows)
- [Examen completo](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (solo Windows 10)
- [Localizar dispositivo](/mem/intune/remote-actions/device-locate)   (solo iOS)
- [Modo perdido](/mem/intune/remote-actions/device-lost-mode)   (solo iOS)- [Examen rápido](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)
- [Control remoto para Android](/mem/intune/remote-actions/teamviewer-support)
- [Bloqueo remoto](/mem/intune/remote-actions/device-remote-lock)
- [Cambiar nombre del dispositivo](/mem/intune/remote-actions/device-rename)
-  [Restablecer código de](/mem/intune/remote-actions/device-passcode-reset) [acceso Reiniciar](/mem/intune/remote-actions/device-restart)   (Windows solo)
-  Actualizar Windows Defender inteligencia de seguridad (Windows solo)
-  Windows 10 Restablecimiento de PIN (Windows solo)
-  [Enviar notificaciones personalizadas](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad sistema operativo)
-  [Sincronizar dispositivo](/mem/intune/remote-actions/device-sync)

Para obtener más información sobre las acciones de Intune, [consulte Microsoft Intune documentación](/mem/intune/).