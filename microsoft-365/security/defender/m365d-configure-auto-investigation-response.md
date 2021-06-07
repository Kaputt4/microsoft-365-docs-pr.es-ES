---
title: Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender
description: Configurar la investigación automatizada y la respuesta con recuperación automática en Microsoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 48d299f2318b0a1be251132a4b50a333a1a0c7a8
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782962"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender incluye potentes [capacidades automatizadas](m365d-autoir.md) de investigación y respuesta que pueden ahorrar mucho tiempo y esfuerzo al equipo de operaciones de seguridad. Con [la recuperación automática,](m365d-autoir.md#how-automated-investigation-and-self-healing-works)estas capacidades imitan los pasos que un analista de seguridad tomaría para investigar y responder a las amenazas, solo más rápido y con más capacidad para escalar.

En este artículo se describe cómo configurar la investigación automatizada y la respuesta en Microsoft 365 Defender con estos pasos:

1. [Revise los requisitos previos](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Revisar o cambiar el nivel de automatización de los grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups).
3. [Revise las directivas de seguridad y alertas en Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Asegúrese de que Microsoft 365 Defender esté activado](#make-sure-microsoft-365-defender-is-turned-on).

A continuación, una vez configurado todo, puede ver y administrar acciones de corrección [en el Centro de acciones](m365d-autoir-actions.md).

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Requisitos previos para la investigación automatizada y la respuesta en Microsoft 365 Defender

<br>

****

|Requisito|Detalles|
|---|---|
|Requisitos de suscripción|Una de estas suscripciones: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 con el Seguridad de Microsoft 365 E5 complemento</li><li>Microsoft 365 A3 con el Microsoft 365 de seguridad A5</li><li>Office 365 E5 más Enterprise Mobility + Security E5 más Windows E5</li></ul> <p> Consulte [Microsoft 365 de licencias de Defender.](./prerequisites.md#licensing-requirements)|
|Requisitos de red|<ul><li>[Microsoft Defender para identidad habilitado](/azure-advanced-threat-protection/what-is-atp)</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) configurado</li><li>[Integración de Microsoft Defender para identidades](/cloud-app-security/mdi-integration)</li></ul>|
|Requisitos de Windows del equipo|<ul><li>Windows 10, versión 1709 o posterior instalada (vea [Windows 10 de la versión )](/windows/release-information/)</li><li>Los siguientes servicios de protección contra amenazas configurados:<ul><li>[Microsoft Defender para punto de conexión](../defender-endpoint/configure-endpoints.md)</li><li>[Antivirus de Microsoft Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Protección del contenido de correo electrónico y Office archivos|[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) configurado|
|Permisos|Para configurar las capacidades automatizadas de investigación y respuesta, debe tener asignado el rol Administrador global o Administrador de seguridad en Azure Active Directory ( ) o en el centro de administración de <https://portal.azure.com> Microsoft 365 ( <https://admin.microsoft.com> ). <p> Para obtener los permisos necesarios para trabajar con capacidades automatizadas de investigación y respuesta, como revisar, aprobar o rechazar acciones [pendientes,](m365d-action-center.md#required-permissions-for-action-center-tasks)vea Permisos necesarios para las tareas del Centro de acciones .|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisar o cambiar el nivel de automatización de los grupos de dispositivos

Si las investigaciones automatizadas se ejecutan y si las acciones de corrección se toman automáticamente o solo tras la aprobación de los dispositivos dependen de determinadas configuraciones, como las directivas de grupo de dispositivos de la organización. Revisa el nivel de automatización configurado para las directivas de grupo de dispositivos.

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e inicie sesión.
2. Vaya a **Configuración**  >  **permisos grupos** de  >  **dispositivos**.
3. Revisa las directivas de grupo de dispositivos. En concreto, vea la columna **Nivel de corrección.** Se recomienda usar **Full- remediar las amenazas automáticamente**.  Es posible que deba crear o editar los grupos de dispositivos para obtener el nivel de automatización que desee. Para obtener ayuda con esta tarea, consulte los artículos siguientes:
   - [Cómo se corrigen las amenazas](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Crear y administrar grupos de dispositivos](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revise las directivas de seguridad y alertas en Office 365

Microsoft proporciona directivas de [alerta integradas](../../compliance/alert-policies.md) que ayudan a identificar ciertos riesgos. Estos riesgos incluyen el Exchange de permisos de administrador, la actividad de malware, las posibles amenazas externas e internas y los riesgos de gobierno de la información. Algunas alertas pueden desencadenar [la investigación automatizada y la respuesta en Office 365](../office-365-security/office-365-air.md). Asegúrate de que [tu Defender para Office 365](../office-365-security/defender-for-office-365.md) características estén configuradas correctamente.

Aunque ciertas alertas y directivas de seguridad pueden desencadenar investigaciones automatizadas, no se realiza ninguna acción de corrección automáticamente para el correo electrónico *y el contenido*. En su lugar, todas las acciones de corrección del contenido de correo electrónico y correo electrónico esperan la aprobación del equipo de operaciones de seguridad en el [Centro de acciones](m365d-action-center.md).

La configuración de seguridad Office 365 ayuda a proteger el correo electrónico y el contenido. Para ver o cambiar esta configuración, siga las instrucciones de [Proteger contra amenazas](../office-365-security/protect-against-threats.md).

1. En el centro Microsoft 365 seguridad ( [https://security.microsoft.com](https://security.microsoft.com) ), vaya a Directivas & reglas **de** \> **amenazas**.
2. Asegúrese de que todas las directivas siguientes están configuradas. Para obtener ayuda y recomendaciones, vea [Protect against threats](/microsoft-365/security/office-365-security/protect-against-threats).
   - [Antimalware](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Anti-phishing](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Archivos adjuntos seguros](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Vínculos seguros](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Contra correo no deseado](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)
3. Asegúrese de [que Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) está activado.
4. Asegúrese de [que la purga automática de hora cero para la protección de correo](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) electrónico esté en vigor.
5. (Este paso es opcional). Revise las [directivas Office 365 de alerta en](../../compliance/alert-policies.md) el centro de Microsoft 365 cumplimiento ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Varias directivas de alerta predeterminadas se encuentran en la categoría Administración de amenazas. Algunas de estas alertas pueden desencadenar una investigación y respuesta automatizadas. Para obtener más información, vea [Directivas de alerta predeterminadas](../../compliance/alert-policies.md#default-alert-policies).

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Asegúrese de que Microsoft 365 Defender esté activado

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Inicie sesión en el centro Microsoft 365 de seguridad ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. En el panel de navegación, busque **Incidents**, **Action center** y **Hunting**, como se muestra en la imagen anterior.
   - Si ve Incidentes, Centro **de** acciones y **Búsqueda,** Microsoft 365 Defender está activado. Consulta la [sección Revisar o cambiar el nivel de automatización para grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups) de este artículo.
   - Si no ve *Incidentes,* **Centro** de **acciones** o **Búsqueda,** es posible que Microsoft 365 Defender no esté activado. En este caso, [visite el Centro de acciones](m365d-action-center.md)).
3. En el panel de navegación, **elija Configuración**  >  **Microsoft 365 Defender**. Confirme que Microsoft 365 Defender está activado.

> [!TIP]
> ¿Necesita ayuda? Vea [Activar Microsoft 365 Defender](m365d-enable.md).

## <a name="next-steps"></a>Pasos siguientes

- [Acciones de corrección en Microsoft 365 Defender](m365d-remediation-actions.md)
- [Visite el Centro de actividades](m365d-action-center.md)
