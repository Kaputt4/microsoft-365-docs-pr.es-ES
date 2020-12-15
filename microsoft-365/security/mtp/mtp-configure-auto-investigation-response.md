---
title: Configuración de capacidades de investigación y respuesta automatizadas en Microsoft 365 defender
description: Configurar la investigación y la respuesta automatizadas con la recuperación automática en Microsoft 365 defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 12f71011e28d5c8c8287146670282a86a77781ff
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682986"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configuración de capacidades de investigación y respuesta automatizadas en Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 defender incluye eficaces [capacidades automatizadas de investigación y respuesta](mtp-autoir.md) que pueden guardar el equipo de operaciones de seguridad con mucho tiempo y esfuerzo. Con la recuperación automática, estas capacidades imitan los pasos que un analista de seguridad tardaría en investigar y responder a las amenazas, solo más rápido y con más capacidad para escalar. En este artículo se describe cómo configurar la investigación y la respuesta automatizadas en Microsoft 365 defender.

Para configurar las capacidades de investigación y respuesta automatizadas, siga estos pasos:

1. [Revise los requisitos previos](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Revise o cambie el nivel de automatización de los grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups).
3. [Revise sus directivas de seguridad y alertas en Office 365](#review-your-security-and-alert-policies-in-office-365).
4. Asegúrese [de que Microsoft 365 defender está activado](#make-sure-microsoft-365-defender-is-turned-on).

A continuación, una vez que esté todo configurado, [Revise las acciones pendientes y completadas en el centro de actividades](#review-pending-and-completed-actions-in-the-action-center). 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Requisitos previos para la investigación y la respuesta automatizadas en Microsoft 365 defender

|Requisito |Detalles |
|--|--|
|Requisitos de suscripción |Una de las suscripciones: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Seguridad de Microsoft 365 E5<br/>-Seguridad de Microsoft 365 A5<br/>-Office 365 E5 más Enterprise Mobility + Security E5 más Windows E5<br/><br/>Consulte [los requisitos de licencia de Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Requisitos de red |- [Microsoft defender para la identidad](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) habilitada<br/>- Configuración de [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)<br/>- [Microsoft Cloud App Security integrado con Microsoft defender para identidad](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisitos de Windows del equipo |-Windows 10, versión 1709 o posterior instalada (consulte la información de la [versión Windows 10](https://docs.microsoft.com/windows/release-information/)) con los siguientes servicios de protección contra amenazas configurados:<br/>- [Microsoft defender para extremo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Antivirus de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Protección para el contenido de correo electrónico y los archivos de Office |[Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurado |
|Permisos |-Para configurar las capacidades automatizadas de investigación y respuesta, debe tener asignado el rol de administrador global o administrador de seguridad en Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) o en el centro de administración de 365 de Microsoft ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>-Para obtener los permisos necesarios para trabajar con las capacidades de investigación y respuesta automatizadas, como revisar, aprobar o rechazar acciones pendientes, consulte [permisos necesarios para las tareas del centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisar o cambiar el nivel de automatización de los grupos de dispositivos

Si se ejecutan las investigaciones automáticas y si las acciones de corrección se realizan automáticamente o solo cuando la aprobación de los dispositivos depende de determinadas configuraciones, como las directivas de grupo de dispositivos de la organización. Revise el nivel de automatización establecido para las directivas de grupo de dispositivos.

1. Vaya al centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e inicie sesión.

2. Vaya a **configuración**  >    >  **grupos de dispositivos** de permisos. 

3. Revise las directivas de grupo de dispositivos. En particular, mire en la columna **nivel de corrección** . Se recomienda usar las **amenazas de corrección completa de forma automática**.  Es posible que necesite crear o editar los grupos de dispositivos para obtener el nivel de automatización que desea. Para obtener ayuda con esta tarea, vea los siguientes artículos:

   - [Cómo se corrigen las amenazas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Crear y administrar grupos de dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revise sus directivas de seguridad y alertas en Office 365

Microsoft proporciona [directivas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) integradas que ayudan a identificar determinados riesgos. Estos riesgos incluyen los permisos de administrador de Exchange abuso, actividad de malware, posibles amenazas externas e internas y riesgos del gobierno de la información. Algunas alertas pueden desencadenar [investigación y respuesta automatizadas en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Asegúrese de que las características [de Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) estén configuradas correctamente.

Aunque ciertas alertas y directivas de seguridad pueden desencadenar investigaciones automatizadas, no se realizan automáticamente acciones de corrección para el correo electrónico y el contenido. En su lugar, todas las acciones de corrección del contenido de correo electrónico y correo electrónico esperan la aprobación del equipo de operaciones de seguridad en el [centro de actividades](mtp-action-center.md).

Configuración de seguridad en Office 365 ayudar a proteger el correo electrónico y el contenido. Para ver o cambiar esta configuración, siga las instrucciones de [proteger contra amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

1. En el centro de seguridad 365 de Microsoft ( [https://security.microsoft.com/](https://security.microsoft.com/) ), vaya a **directivas**  >  **protección contra amenazas**.

2. Asegúrese de que todas las directivas siguientes están configuradas. Para obtener ayuda y recomendaciones, consulte [proteger contra amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

   - [Anti-malware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-phishing en defender para Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Datos adjuntos seguros (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Vínculos seguros (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Protección contra correo no deseado (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Asegúrese de que [Microsoft defender para Office 365 para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) está activado.

5. Asegúrese de que está activada [la purga automática de cero horas para la protección de correo electrónico](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) . 

8. (Es opcional). Revise sus [directivas de alertas de Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) en el centro de cumplimiento de Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Hay varias directivas de alertas predeterminadas en la categoría administración de amenazas. Algunas de estas alertas pueden desencadenar investigación y respuesta automatizadas. Para obtener más información, consulte [default Alert Policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies).
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Asegurarse de que Microsoft 365 defender está activado

1. Vaya al centro de seguridad 365 de Microsoft ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, busque **incidentes**, **centro de actividades** y **búsqueda**, como se muestra en la siguiente imagen:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP activado":::

   - Si ve **incidentes**, **centro de actividades** y **caza**, Microsoft 365 defender está activado. Vea el procedimiento, [revisión o cambio del nivel de automatización para grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups) (en este artículo).

   - Si *no* ve **incidentes**, el **centro de actividades** o la **caza**, es posible que Microsoft 365 defender no esté activado. En este caso, continúe con el paso siguiente ([Revise las acciones pendientes y completadas](#review-pending-and-completed-actions-in-the-action-center), en este artículo).

3. En el panel de navegación, elija **configuración** de  >  **Microsoft 365 defender**. Confirme que Microsoft 365 defender está activado. 

   ¿Necesita ayuda? Consulte [Activar Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Revisar las acciones pendientes y completadas en el centro de actividades

Una vez que haya configurado la investigación y la respuesta automatizadas en Microsoft 365 defender, el siguiente paso consiste en visitar el centro de actividades ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Allí, puede revisar y aprobar acciones pendientes y ver las acciones de corrección que se realizaron de forma automática o manual. 

[Visite el centro de actividades](mtp-action-center.md).
