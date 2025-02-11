---
title: Elija entre Basic Mobility and Security y Intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: Basic Mobility and Security forma parte de los planes de Microsoft 365, mientras que Microsoft Intune es un producto independiente incluido con determinados planes de Microsoft 365.
ms.openlocfilehash: 191fdefdb4ae1af9ca4873c404a78ca6635b9958
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68721194"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Elija entre Basic Mobility and Security o Intune

[Microsoft Intune](/mem/intune/) es un producto independiente incluido con determinados planes de Microsoft 365, mientras que Basic Mobility and Security forma parte de los planes de Microsoft 365.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilidad de movilidad básica y seguridad y Intune

La movilidad básica y la seguridad y Intune se incluyen en varios planes, que se describen en la tabla siguiente.

| Plan | Movilidad y seguridad básicas | Microsoft Intune |
|:-----|:-----|:-----|
|Aplicaciones de Microsoft 365|Yes|No|
|Microsoft 365 Empresa Básico|Yes|No|
|Microsoft 365 Empresa Estándar|Yes|No|
|Office 365 E1 |Yes|No|
|Office 365 E3 |Sí|No|
|Office 365 E5 |Yes|No|
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

> [!NOTE]
> No puede empezar a usar Basic Mobility and Security si ya usa Microsoft Intune.

 Para obtener más información, consulte [Descripciones del servicio de plataforma de Microsoft 365 y Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description).

## <a name="differences-in-capabilities"></a>Diferencias en las capacidades

Microsoft Intune y basic mobility and security integrados le ofrecen la capacidad de administrar dispositivos móviles en su organización, pero hay diferencias clave en la funcionalidad, que se describen en la tabla siguiente.

> [!NOTE]
> Puede administrar los usuarios y sus dispositivos móviles mediante Intune y Basic Mobility and Security en la misma organización Microsoft 365 Empresa Estándar *configurando primero Basic Mobility and Security y, a continuación, agregando Microsoft Intune*. Esto le permite elegir Basic Mobility and Security o la solución de Intune con más características. Asigne una licencia de Intune para habilitar las características de Intune.

| Área de característica | Resaltados de características | Movilidad y seguridad básicas | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Administración de distintas plataformas del sistema operativo y variantes principales del modo de administración. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Cumplimiento de dispositivos|Establezca y administre directivas de seguridad, como el bloqueo de PIN de nivel de dispositivo y la detección de jailbreak. |Limitaciones en dispositivos Android. Consulte [los detalles](capabilities.md). |Yes|
|Acceso condicional basado en el cumplimiento del dispositivo |Impedir que los dispositivos no conformes accedan al correo electrónico corporativo y a los datos desde la nube. |No se admite en Windows 10.<br/>Limitado a controlar el acceso a Exchange Online, SharePoint Online y Outlook. |Yes |
|Configuración de dispositivos  |Configurar la configuración del dispositivo (por ejemplo, deshabilitar la cámara)|Conjunto limitado de configuraciones.|Yes|
|Perfiles de correo electrónico  |Aprovisione un perfil de correo electrónico nativo en el dispositivo. |Sí|Sí|
|Perfiles de WiFi |Aprovisione un perfil de WiFi nativo en el dispositivo. |No|Sí|
|Perfiles de VPN |Aprovisione un perfil de VPN nativo en el dispositivo. |No|Sí|
|Administración de aplicaciones móviles  |Implemente las aplicaciones de línea de negocio internas y desde las tiendas de aplicaciones a los usuarios. |No|Sí|
|Protección de aplicaciones móviles  |Permitir que los usuarios accedan de forma segura a la información corporativa mediante las aplicaciones móviles y de línea de negocio de Office que conocen, a la vez que garantizan la seguridad de los datos al ayudar a restringir acciones como copiar, cortar, pegar y guardar como solo aquellas aplicaciones administradas aprobadas para datos corporativos. Funciona incluso si los dispositivos no están inscritos en Basic Mobility and Security. Consulte Protección de datos de aplicaciones mediante directivas MAM. |No|Sí|
|Explorador administrado  |Habilite la exploración web más segura mediante la aplicación Edge. |No|Sí|
|Programas de inscripción táctil cero (AutoPilot) |Inscriba un gran número de dispositivos corporativos, a la vez que simplifica la configuración del usuario. |No|Sí|

Además de las características enumeradas en la tabla anterior, Basic Mobility and Security y Intune incluyen un conjunto de acciones remotas que envían comandos a dispositivos a través de Internet. Por ejemplo, puede quitar datos de Office del dispositivo de un empleado mientras deja los datos personales en su lugar (retirar), quitar aplicaciones de Office del dispositivo de un empleado (borrar) o restablecer un dispositivo a su configuración de fábrica (borrado completo).

Las acciones remotas básicas de movilidad y seguridad incluyen retirar, borrar y borrar completamente. Para obtener más información sobre las acciones básicas de movilidad y seguridad, consulte [Funcionalidades de movilidad y seguridad básicas](capabilities.md).

Con Intune tiene el siguiente conjunto de acciones:

- [Restablecimiento de Autopilot](/mem/autopilot/windows-autopilot-reset) (solo Windows)
- [Recuperación de claves de Bitlocker](https://support.microsoft.com/windows/finding-your-bitlocker-recovery-key-in-windows-6b71ad27-0b89-ea08-f143-056f5ab347d6) (solo Windows)
- [Usar borrado, retirada o anulación manual de la inscripción del dispositivo](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
- [Deshabilitar el bloqueo de activación](/mem/intune/remote-actions/device-activation-lock-disable) (solo iOS)
- [Inicio nuevo](/mem/intune/remote-actions/device-fresh-start) (solo Windows)
- [Examen completo](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) (solo Windows 10)
- [Buscar dispositivo](/mem/intune/remote-actions/device-locate) (solo para iOS)
- [Modo perdido](/mem/intune/remote-actions/device-lost-mode) (solo iOS): [examen rápido](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) (solo Windows 10)
- [Control remoto en Android](/mem/intune/remote-actions/teamviewer-support)
- [Bloqueo remoto](/mem/intune/remote-actions/device-remote-lock)
- [Cambiar el nombre del dispositivo](/mem/intune/remote-actions/device-rename)
- Restablecer [reinicio](/mem/intune/remote-actions/device-restart) [del código de acceso](/mem/intune/remote-actions/device-passcode-reset) (solo Windows)
- [Actualizar Windows Defender Security Intelligence](https://www.microsoft.com/en-us/wdsi/defenderupdates) (solo Windows)
- [Windows 10 restablecimiento del PIN](/windows/security/identity-protection/hello-for-business/hello-feature-pin-reset) (solo Windows)
- [Envío de notificaciones personalizadas](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device) (Android, iOS, sistema operativo iPad)
- [Sincronizar dispositivo](/mem/intune/remote-actions/device-sync)

Para obtener más información sobre las acciones de Intune, consulte [Microsoft Intune documentación](/mem/intune/).
