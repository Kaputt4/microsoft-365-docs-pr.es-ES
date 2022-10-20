---
title: Preguntas más frecuentes sobre la protección contra alteraciones
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Preguntas más frecuentes sobre la configuración de la protección contra alteraciones.
keywords: malware, defender, antivirus, protección contra alteraciones
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.date: 10/17/2022
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
ms.openlocfilehash: 7446892236a4b6976c67d8332e618b8089f8869d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68641521"
---
# <a name="frequently-asked-questions-on-tamper-protection"></a>Preguntas más frecuentes sobre la protección contra alteraciones

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

## <a name="on-which-versions-of-windows-can-i-configure-tamper-protection"></a>¿En qué versiones de Windows puedo configurar la "protección contra alteraciones"?

- Windows 11
- Sesión múltiple de Windows 11 Enterprise
- Windows 10 sistema operativo [1709](/lifecycle/announcements/revised-end-of-service-windows-10-1709), [1803](/lifecycle/announcements/windows-server-1803-end-of-servicing), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) o posterior junto con [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint).
- Sesión múltiple de Windows 10 Enterprise
  
Si usa Configuration Manager, versión 2006, con asociación de inquilinos, la protección contra alteraciones se puede ampliar a Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 y Windows Server 2022. Consulte [Asociación de inquilinos: Creación e implementación de la directiva antivirus de seguridad de puntos de conexión desde el Centro de administración (versión preliminar).](/mem/configmgr/tenant-attach/deploy-antivirus-policy)

## <a name="will-tamper-protection-affect-non-microsoft-antivirus-registration-in-the-windows-security-app"></a>¿Afectará la protección contra alteraciones al registro de antivirus que no sea de Microsoft en la aplicación Seguridad de Windows?

No. Las ofertas de antivirus que no son de Microsoft seguirán registrándose con la aplicación Seguridad de Windows.

## <a name="what-happens-if-microsoft-defender-antivirus-isnt-active-on-a-device"></a>¿Qué ocurre si Microsoft Defender Antivirus no está activo en un dispositivo?

Los dispositivos incorporados a Microsoft Defender para punto de conexión tendrán Microsoft Defender Antivirus en ejecución en modo pasivo. En estos casos, la protección contra alteraciones seguirá protegiendo el servicio y sus características.

## <a name="how-do-i-turn-tamper-protection-on-or-off"></a>मैले कसरी activar o desactivar la protección contra alteraciones?

Si es un usuario principal, consulte Administración de [la protección contra alteraciones en un dispositivo individual](manage-tamper-protection-individual-device.md).

Si es una organización que usa [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint), debería poder administrar la "protección contra alteraciones" en Intune similar a cómo administra otras características de Endpoint Protection. Consulte las secciones siguientes de este artículo:

- [Administración de la protección contra alteraciones mediante Microsoft Endpoint Manager](manage-tamper-protection-microsoft-endpoint-manager.md)
- [Administración de la protección contra alteraciones mediante Microsoft 365 Defender](manage-tamper-protection-microsoft-365-defender.md)

## <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-with-group-policy"></a>¿Cómo afecta la configuración de la protección contra alteraciones en Intune cómo administro Microsoft Defender Antivirus con समूह नीति?

Si actualmente usa Intune para configurar y administrar la protección contra alteraciones, debe seguir usando Intune. 

Cuando se activa la protección contra alteraciones y se usa समूह नीति para realizar cambios en Microsoft Defender configuración del Antivirus, se omitirá la configuración protegida contra alteraciones. 

## <a name="if-we-use-microsoft-intune-to-configure-tamper-protection-does-it-apply-only-to-the-entire-organization"></a>Si usamos Microsoft Intune para configurar la protección contra alteraciones, ¿se aplica solo a toda la organización?

Tiene flexibilidad para configurar la protección contra alteraciones con Intune. Puede dirigirse a toda la organización o seleccionar dispositivos y grupos de usuarios específicos.

## <a name="can-i-configure-tamper-protection-with-microsoft-endpoint-configuration-manager"></a>¿Puedo configurar la protección contra alteraciones con Microsoft Endpoint Configuration Manager?

Si usa la asociación de inquilinos, puede usar Microsoft Endpoint Configuration Manager. Vea los siguientes recursos:

- [Administración de la protección contra alteraciones mediante la asociación de inquilinos con Configuration Manager, versión 2006](manage-tamper-protection-configuration-manager.md)
- [Blog de tech community: Anuncio de la protección contra alteraciones para clientes de asociación de inquilinos de Configuration Manager](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Tengo la inscripción de Windows E3. ¿Puedo usar la configuración de la protección contra alteraciones en Intune?

Actualmente, la configuración de la protección contra alteraciones en Intune solo está disponible para los clientes que tienen [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint).

## <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Soy un cliente empresarial. ¿Pueden los administradores locales cambiar la protección contra alteraciones en sus dispositivos?

No. Los administradores locales no pueden cambiar ni modificar la configuración de protección contra alteraciones.

## <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>¿Qué ocurre si mi dispositivo se incorpora con Microsoft Defender para punto de conexión y, a continuación, entra en un estado sin abordar?

Si un dispositivo está desconectado de Microsoft Defender para punto de conexión, se activa la protección contra alteraciones, que es el estado predeterminado para los dispositivos no administrados.

## <a name="if-the-status-of-tamper-protection-changes-are-alerts-shown-in-the-microsoft-365-defender-portal"></a>Si cambia el estado de la protección contra alteraciones, ¿se muestran alertas en el portal de Microsoft 365 Defender?

Sí. La alerta se muestra en [https://security.microsoft.com](https://security.microsoft.com) **Alertas**.

El equipo de operaciones de seguridad también puede usar consultas de búsqueda, como el ejemplo siguiente:

`AlertInfo|where Title == "Tamper Protection bypass"`

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
