---
title: Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender
description: Configurar la investigación y respuesta automatizadas con recuperación automática en Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 123b3b5f8514e9b3914b98178191d60e78280991
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930323"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender incluye potentes capacidades automatizadas de investigación y respuesta [que](mtp-autoir.md) pueden ahorrarle mucho tiempo y esfuerzo al equipo de operaciones de seguridad. Con la recuperación automática, estas capacidades imitan los pasos que un analista de seguridad seguiría para investigar y responder a las amenazas, solo más rápido y con más capacidad de escala. En este artículo se describe cómo configurar la investigación y respuesta automatizadas en Microsoft 365 Defender.

Para configurar las capacidades automatizadas de investigación y respuesta, siga estos pasos:

1. [Revise los requisitos previos.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Revise o cambie el nivel de automatización de los grupos de dispositivos.](#review-or-change-the-automation-level-for-device-groups)
3. [Revise las directivas de seguridad y alerta en Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Asegúrese de que Microsoft 365 Defender está activado.](#make-sure-microsoft-365-defender-is-turned-on)

A continuación, una vez que haya configurado todo, revise las acciones pendientes y [completadas en el Centro de actividades.](#review-pending-and-completed-actions-in-the-action-center)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Requisitos previos para la investigación automatizada y la respuesta en Microsoft 365 Defender

|Requisito |Detalles |
|--|--|
|Requisitos de suscripción |Una de las suscripciones: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Seguridad de Microsoft 365 E5</li><li>Microsoft 365 A5 Security</li><li>Office 365 E5 más Enterprise Mobility + Security E5 más Windows E5</li></ul><p> Vea los [requisitos de licencia de Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)|
|Requisitos de red |<ul><li>[Microsoft Defender para identidad habilitado](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)</li><li>[Microsoft Cloud App Security configurado](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</li><li>[Microsoft Defender para la integración de identidades](https://docs.microsoft.com/cloud-app-security/mdi-integration)</li></ul>|
|Requisitos de Windows del equipo |Windows 10, versión 1709 o posterior instalado (consulta la información de la versión de [Windows 10)](https://docs.microsoft.com/windows/release-information/)con los siguientes servicios de protección contra amenazas configurados:<ul><li>[Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</li><li>[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul>|
|Protección de contenido de correo electrónico y archivos de Office |[Microsoft Defender para Office 365 configurado](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|Permisos |<ul><li>Para configurar las capacidades automatizadas de investigación y respuesta, debe tener asignado el rol administrador global o administrador de seguridad en Azure Active Directory ( ) o en el Centro de administración de [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).</li><p><li>Para obtener los permisos necesarios para trabajar con capacidades automatizadas de investigación y respuesta, como revisar, aprobar o rechazar acciones [pendientes,](mtp-action-center.md#required-permissions-for-action-center-tasks)vea Permisos necesarios para las tareas del Centro de actividades.</li></ul>|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisar o cambiar el nivel de automatización de los grupos de dispositivos

Si se ejecutan investigaciones automatizadas y si las acciones de corrección se toman automáticamente o solo tras la aprobación de los dispositivos dependen de determinadas opciones de configuración, como las directivas de grupo de dispositivos de la organización. Revisa el nivel de automatización establecido para las directivas de grupo de dispositivos.

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e inicie sesión.

2. Vaya a **Grupos**  >  **de dispositivos de permisos** de  >  **configuración.**

3. Revisa las directivas de grupo de dispositivos. En particular, mire la columna **nivel de corrección.** Se recomienda usar **Full: corregir las amenazas automáticamente.**  Es posible que deba crear o editar los grupos de dispositivos para obtener el nivel de automatización que desee. Para obtener ayuda con esta tarea, consulte los artículos siguientes:

   - [Cómo se corrigen las amenazas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Crear y administrar grupos de dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revisar las directivas de seguridad y alertas en Office 365

Microsoft proporciona directivas de [alerta integradas que](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) ayudan a identificar ciertos riesgos. Estos riesgos incluyen el abuso de permisos de administrador de Exchange, la actividad de malware, las posibles amenazas internas y externas, y los riesgos de gobierno de la información. Algunas alertas pueden desencadenar [una investigación y respuesta automatizadas en Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Asegúrese de que [las características de Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) están configuradas correctamente.

Aunque ciertas alertas y directivas de seguridad pueden desencadenar investigaciones automatizadas, no se toman medidas correctivas automáticamente para el correo electrónico y el contenido. En su lugar, todas las acciones de corrección para el contenido de correo electrónico y correo electrónico esperan la aprobación del equipo de operaciones de seguridad en el [Centro de actividades.](mtp-action-center.md)

La configuración de seguridad de Office 365 ayuda a proteger el correo electrónico y el contenido. Para ver o cambiar esta configuración, siga las instrucciones de [Protección contra amenazas.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

1. En el Centro de seguridad de Microsoft 365 ( [https://security.microsoft.com/](https://security.microsoft.com/) ), vaya a Protección **contra** amenazas  >  **de directivas.**

2. Asegúrese de que estén configuradas todas las directivas siguientes. Para obtener ayuda y recomendaciones, vea [Proteger contra amenazas.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

   - [Antimalware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-phishing en Defender para Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Datos adjuntos seguros (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Vínculos seguros (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Correo no deseado (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)

3. Asegúrese de [que Microsoft Defender para Office 365 para SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) y Microsoft Teams está activado.

4. Asegúrese de [que la purga automática de cero](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) horas para la protección de correo electrónico esté en vigor.

5. (Esto es opcional). Revise las directivas [de alerta de Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) en el Centro de cumplimiento de Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Hay varias directivas de alerta predeterminadas en la categoría administración de amenazas. Algunas de estas alertas pueden desencadenar una investigación y respuesta automatizadas. Para obtener más información, consulta [Directivas de alerta predeterminadas.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Asegúrese de que Microsoft 365 Defender está activado

1. Vaya al Centro de seguridad de Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, busque **Incidentes,** Centro **de** actividades y **Búsqueda,** como se muestra en la siguiente imagen:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

   - Si ve Incidentes, **Centro de** **actividades** y **Búsqueda,** Microsoft 365 Defender está activado. Consulta el procedimiento, [revisar o cambiar el nivel de automatización de los grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups) (en este artículo).

   - Si no ve *Incidentes,* Centro de **actividades** o **Búsqueda,** es posible que Microsoft 365 Defender no esté activado.  En este caso, continúe con el paso siguiente (Revise las acciones[pendientes](#review-pending-and-completed-actions-in-the-action-center)y completadas, en este artículo).

3. En el panel de navegación, elija  >  **Configuración de Microsoft 365 Defender.** Confirme que Microsoft 365 Defender está activado.

   ¿Necesita ayuda? Vea [Activar Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Revisar las acciones pendientes y completadas en el Centro de actividades

Después de configurar la investigación y respuesta automatizadas en Microsoft 365 Defender, el siguiente paso es visitar el Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Allí, puede revisar y aprobar las acciones pendientes y ver las acciones de corrección que se realizaron de forma automática o manual.

[Visite el Centro de acciones.](mtp-action-center.md)
