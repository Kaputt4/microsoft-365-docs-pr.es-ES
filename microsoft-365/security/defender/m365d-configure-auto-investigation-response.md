---
title: Configurar las funcionalidades automatizadas de investigación y respuesta en Microsoft 365 Defender
description: Configuración de la investigación y la respuesta automatizadas con recuperación automática en Microsoft 365 Defender
search.appverid: MET150
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: m365d
ms.localizationpriority: medium
ms.collection:
- m365-security
- tier2
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: ed6437e990ca62934e1647bbfa113f3b163d8aef
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68051330"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurar las funcionalidades automatizadas de investigación y respuesta en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender incluye [eficaces funcionalidades automatizadas de investigación y respuesta](m365d-autoir.md) que pueden ahorrar mucho tiempo y esfuerzo al equipo de operaciones de seguridad. Con la [recuperación automática](m365d-autoir.md#how-automated-investigation-and-self-healing-works), estas funcionalidades imitan los pasos que tomaría un analista de seguridad para investigar y responder a las amenazas, solo más rápido y con más capacidad de escala.

En este artículo se describe cómo configurar la investigación y la respuesta automatizadas en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con estos pasos:

1. [Revise los requisitos previos](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Revise o cambie el nivel de automatización de los grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups).
3. [Revise las directivas de seguridad y alertas en Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Asegúrese de que Microsoft 365 Defender esté activado](#make-sure-microsoft-365-defender-is-turned-on).

Después, una vez configurado, puede [ver y administrar las acciones de corrección en el Centro de acciones](m365d-autoir-actions.md).

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Requisitos previos para la investigación y respuesta automatizadas en Microsoft 365 Defender

<br>

****

|Requisito|Detalles|
|---|---|
|Requisitos de suscripción|Una de estas suscripciones: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5</li><li>Microsoft 365 A3 con el complemento seguridad de Microsoft 365 A5</li><li>Office 365 E5 más Enterprise Mobility + Security E5 y Windows E5</li></ul> <p> Consulte [Microsoft 365 Defender requisitos de licencia](./prerequisites.md#licensing-requirements).|
|Requisitos de red|<ul><li>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) habilitado</li><li>[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) configurado</li><li>[integración Microsoft Defender for Identity](/cloud-app-security/mdi-integration)</li></ul>|
|Requisitos del dispositivo Windows|<ul><li>Windows 11</li><li>Windows 10, versión 1709 o posterior instalada (consulte [la información de la versión de Windows](/windows/release-information/))</li><li>Los siguientes servicios de protección contra amenazas configurados:<ul><li>[Microsoft Defender para punto de conexión](../defender-endpoint/configure-endpoints.md)</li><li>[Antivirus de Microsoft Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Protección de contenido de correo electrónico y archivos de Office|[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) configurado|
|Permisos|Para configurar funcionalidades automatizadas de investigación y respuesta, debe tener asignado el rol Administrador global o Administrador de seguridad en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>). <p> Para obtener los permisos necesarios para trabajar con funcionalidades automatizadas de investigación y respuesta, como revisar, aprobar o rechazar acciones pendientes, consulte [Permisos necesarios para las tareas del Centro de acciones](m365d-action-center.md#required-permissions-for-action-center-tasks).|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisión o cambio del nivel de automatización de los grupos de dispositivos

Si se ejecutan investigaciones automatizadas y si las acciones de corrección se realizan automáticamente o solo tras la aprobación de los dispositivos dependen de ciertas configuraciones, como las directivas de grupo de dispositivos de la organización. Revise el nivel de automatización configurado para las directivas de grupo de dispositivos.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración** > **Puntos de conexión** > **Grupos de dispositivos** en **Permisos**.

3. Revise las directivas de grupo de dispositivos. En concreto, examine la columna **Nivel de automatización** . Se recomienda usar **Full: corregir las amenazas automáticamente**.  Es posible que tenga que crear o editar los grupos de dispositivos para obtener el nivel de automatización que desee. Para obtener ayuda con esta tarea, consulte los artículos siguientes:
   - [Cómo se corrigen las amenazas](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Crear y administrar grupos de dispositivos](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revise las directivas de seguridad y alertas en Office 365

Microsoft proporciona [directivas de alertas](../../compliance/alert-policies.md) integradas que ayudan a identificar ciertos riesgos. Estos riesgos incluyen abuso de permisos de administrador de Exchange, actividad de malware, posibles amenazas externas e internas, y riesgos de gobernanza de la información. Algunas alertas pueden desencadenar [una investigación y una respuesta automatizadas en Office 365](../office-365-security/office-365-air.md). Asegúrese de que [las características de Defender para Office 365](../office-365-security/defender-for-office-365.md) están configuradas correctamente.

Aunque ciertas alertas y directivas de seguridad pueden desencadenar investigaciones automatizadas, *no se realizan acciones de corrección automáticamente para el correo electrónico y el contenido*. En su lugar, todas las acciones de corrección del contenido de correo electrónico y correo electrónico esperan la aprobación del equipo de operaciones de seguridad en el [Centro de acciones](m365d-action-center.md).

La configuración de seguridad de Office 365 ayudar a proteger el correo electrónico y el contenido. Para ver o cambiar esta configuración, siga las instrucciones de [Protección contra amenazas](../office-365-security/protect-against-threats.md).

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, vaya a **Directivas & reglas** \> **Directivas de amenazas**.

2. Asegúrese de que están configuradas todas las directivas siguientes. Para obtener ayuda y recomendaciones, consulte [Protección contra amenazas](/microsoft-365/security/office-365-security/protect-against-threats).
   - [Antimalware](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Anti-phishing](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [Archivos adjuntos seguros](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Vínculos seguros](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Antispam](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)

3. Asegúrese de que [los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](../office-365-security/mdo-for-spo-odb-and-teams.md) estén activados.

4. Asegúrese de que la [purga automática de cero horas (ZAP) en Exchange Online](../office-365-security/zero-hour-auto-purge.md) esté en vigor.

5. (Este paso es opcional). Revise las [directivas de alertas de Office 365](../../compliance/alert-policies.md) en el portal de cumplimiento Microsoft Purview ([https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies)). Hay varias directivas de alerta predeterminadas en la categoría Administración de amenazas. Algunas de estas alertas pueden desencadenar una investigación y una respuesta automatizadas. Para obtener más información, consulte [Directivas de alerta predeterminadas](../../compliance/alert-policies.md#default-alert-policies).

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Asegúrese de que Microsoft 365 Defender está activado

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="Panel de navegación izquierdo del portal de Microsoft 365 Defender cuando se activa Microsoft 365 Defender" lightbox="../../media/mtp-enable/mtp-on.png":::

1. Inicio de sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>

2. En el panel de navegación, busque **Incidentes & Alertas**, **Búsqueda** y **Centro de acciones** , como se muestra en la imagen anterior.
   - Si ve **Incidentes & Alertas**, **Búsqueda** y **Centro de acción**, Microsoft 365 Defender está activado. Consulte la sección [Revisión o cambio del nivel de automatización de los grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups) de este artículo.
   - Si *no* ve **Incidentes**, **Centro de acciones** o **Búsqueda**, es posible que Microsoft 365 Defender no esté activado. En este caso, [visite el Centro de acciones](m365d-action-center.md).

> [!TIP]
> ¿Necesita ayuda? Consulte [Activar Microsoft 365 Defender](m365d-enable.md).

## <a name="next-steps"></a>Pasos siguientes

- [Acciones de corrección en Microsoft 365 Defender](m365d-remediation-actions.md)
- [Visite el Centro de actividades](m365d-action-center.md)
