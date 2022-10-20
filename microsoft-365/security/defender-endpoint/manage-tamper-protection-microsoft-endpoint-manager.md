---
title: Administración de la protección contra alteraciones de la organización mediante Microsoft Intune
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Active o desactive la protección contra alteraciones para su organización en Microsoft Intune.
keywords: malware, defender, antivirus, protección contra alteraciones, Microsoft Intune
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.date: 10/14/2022
audience: ITPro
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: c9e1113e20402fce066213861a4e0063f45a5e39
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623689"
---
# <a name="manage-tamper-protection-for-your-organization-using-microsoft-intune"></a>Administración de la protección contra alteraciones de la organización mediante Microsoft Intune

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Si su organización usa [Microsoft Intune](/mem/intune/fundamentals/what-is-intune), puede activar (o desactivar) la protección contra alteraciones para su organización en el Centro de [administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com). Use Intune cuando desee ajustar la configuración de protección contra alteraciones. Por ejemplo, si desea habilitar la protección contra alteraciones en algunos dispositivos, pero no en todos, use Intune.

## <a name="requirements-for-managing-tamper-protection-in-intune"></a>Requisitos para administrar la protección contra alteraciones en Intune

- Debe tener asignados [los permisos](/microsoft-365/security/defender-endpoint/assign-portal-access) adecuados, como el administrador global, el administrador de seguridad o las operaciones de seguridad.
- Su organización usa [Intune para administrar dispositivos](/mem/endpoint-manager-getting-started). (se requieren licencias Intune; Intune se incluye en Microsoft 365 E3/E5, Enterprise Mobility + Security E3/E5, Microsoft 365 Empresa Premium, Microsoft 365 F1/F3, Microsoft 365 Government G3/G5 y licencias educativas correspondientes).
- Los dispositivos Windows deben ejecutarse Windows 10 [versión 1709 o posterior](/lifecycle/announcements/revised-end-of-service-windows-10-1709) o Windows 11. (Para obtener más información sobre las versiones, consulte [Windows 10 información de la versión](/windows/release-health/release-information)).
- Debe usar la seguridad de Windows con [inteligencia de seguridad](https://www.microsoft.com/wdsi/definitions) actualizada a la versión 1.287.60.0 (o posterior).
- Los dispositivos deben usar la versión 4.18.1906.3 (o posterior) de la plataforma antimalware y la versión `1.1.15500.X` del motor antimalware (o posterior). ([Administrar Microsoft Defender actualizaciones del Antivirus y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)).
- Los inquilinos de Intune y Defender para punto de conexión deben compartir la misma infraestructura de Microsoft Entra (Azure Active Directory).
- Los dispositivos deben incorporarse a Defender para punto de conexión.

> [!NOTE]
> Si los dispositivos no están inscritos en Microsoft Defender para punto de conexión, la protección contra alteraciones se mostrará como **No aplicable** hasta que se complete el proceso de incorporación.

## <a name="turn-tamper-protection-on-or-off-in-microsoft-intune"></a>Activar (o desactivar) la protección contra alteraciones en Microsoft Intune

:::image type="content" source="images/turnontamperprotectinmem.png" alt-text="Activar la protección contra alteraciones con Intune" lightbox="images/turnontamperprotectinmem.png":::

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Antivirus** de **seguridad** \> de puntos de conexión y, a continuación, elija **+ Crear directiva**.

   - En la lista **Plataforma**, seleccione **Windows 10, Windows 11 y Windows Server**.
   - En la lista **Perfil**, seleccione **Seguridad de Windows experiencia**.

2. Cree un perfil que incluya la siguiente configuración:

    - **TamperProtection (dispositivo): habilitar**

3. Asigne el perfil a uno o varios grupos.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)