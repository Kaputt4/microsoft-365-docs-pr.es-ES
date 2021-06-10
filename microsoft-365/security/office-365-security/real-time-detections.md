---
title: Conceptos básicos del Explorador de amenazas y detecciones en tiempo real en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use detecciones en tiempo real o explorador para investigar y responder a las amenazas de forma eficaz.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300220"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>Conceptos básicos del Explorador de amenazas y detección en tiempo real

En este artículo:

- [Diferencias entre el Explorador de amenazas y las detecciones en tiempo real](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [Permisos y licencias necesarios](#required-licenses-and-permissions)

> [!NOTE]
> Esto forma parte de una serie de **3** artículos sobre explorador de amenazas **(Explorer),** seguridad de correo electrónico y **conceptos** básicos de detecciones de Explorador y tiempo real (como diferencias entre las herramientas y los permisos necesarios para operarlas). Los otros dos artículos de esta serie son Búsqueda de [amenazas en](threat-hunting-in-threat-explorer.md) el Explorador de amenazas y Seguridad de correo electrónico con el Explorador [de amenazas.](email-security-in-microsoft-defender.md)

En este artículo se explica la diferencia entre la exploración de amenazas y los informes de detecciones en tiempo real, y las licencias y permisos necesarios.

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si su organización tiene [Microsoft Defender](defender-for-office-365.md)para Office 365 y tiene los [permisos,](#required-licenses-and-permissions)puede usar el Explorador de amenazas **(denominado** **Explorador)** o detecciones en tiempo **real** para detectar y corregir amenazas.

En el **Centro de & seguridad,** vaya a **Administración** de amenazas y, a continuación, elija **Explorador**  o **Detecciones en tiempo real.**

<br>

****

|Con Microsoft Defender para Office 365 plan 2, verá:|Con Microsoft Defender para Office 365 plan 1, verá:|
|---|---|
|![Explorador de amenazas](../../media/threatmgmt-explorer.png)|![Detecciones en tiempo real](../../media/threatmgmt-realtimedetections.png)|
|

Con estas herramientas, puede:

- Vea malware detectado por Microsoft 365 de seguridad.
- Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en datos de veredicto.
- Inicie un proceso automatizado de investigación y respuesta desde una vista en el Explorador.
- Investigar correo electrónico malintencionado y mucho más.

Para obtener más información, vea [Email security with Threat Explorer](email-security-in-microsoft-defender.md).

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Diferencias entre el Explorador de amenazas y las detecciones en tiempo real

- *Las detecciones en* tiempo real son una herramienta de informes disponible en Defender para Office 365 Plan 1. *El Explorador de* amenazas es una herramienta de búsqueda y corrección de amenazas disponible en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real permite ver las detecciones en tiempo real. El Explorador de amenazas también lo hace, pero proporciona detalles adicionales para un ataque determinado, como resaltar las campañas de ataque, y ofrece a los equipos de operaciones de seguridad la capacidad de corregir amenazas (incluida la activación de una investigación automatizada de investigación y [respuesta).](automated-investigation-response-office.md)
- Una *vista De todo* el correo electrónico está disponible en el Explorador de amenazas, pero no se incluye en el informe de detecciones en tiempo real.
- Las funciones de filtrado enriquecido y las acciones de corrección se incluyen en el Explorador de amenazas. Para obtener más información, vea [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) usar cualquiera de las detecciones en tiempo real o explorer:

- Pero el Explorador solo se incluye en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real se incluye en Defender for Office 365 Plan 1.

Los equipos de operaciones de seguridad deben asignar licencias para todos los usuarios que deberán estar protegidos por Defender para Office 365 y tener en cuenta que las detecciones en tiempo real y explorador muestran datos de detección para usuarios con licencia.

Para ver y usar *detecciones* en tiempo real o explorador, debe tener lo siguiente:

- Para el Centro de & seguridad:

  - Administración de la organización
  - Administrador de seguridad (se puede asignar en el centro Azure Active Directory de administración ( <https://aad.portal.azure.com> )
  - Lector de seguridad

- Para Exchange Online:

  - Administración de la organización
  - Administración de la organización de solo visualización
  - Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información sobre roles y permisos, consulte los siguientes recursos:

- [Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)
- [Permisos de características de Exchange Online](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>Más información
- [El Explorador de amenazas recopila detalles de correo electrónico en la página de entidad de correo electrónico](mdo-email-entity-page.md)
- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](automated-investigation-response-office.md)