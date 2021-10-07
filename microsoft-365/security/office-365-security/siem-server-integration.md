---
title: Integración del servidor SIEM Microsoft 365 servicios y aplicaciones
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Obtenga información general sobre la integración del servidor de administración de eventos y información de seguridad (SIEM) con Microsoft 365 y aplicaciones en la nube
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71fff15b1493f6e8e15becbd87ad55947c8eddc4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169424"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integración del servidor de administración de eventos y de información de seguridad (SIEM) Microsoft 365 servicios y aplicaciones

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Resumen

¿Su organización está usando o planeando obtener un servidor de administración de eventos y información de seguridad (SIEM) Es posible que se pregunte cómo se integra con Microsoft 365 o Office 365. En este artículo se proporciona una lista de recursos que puede usar para integrar el servidor SIEM con Microsoft 365 servicios y aplicaciones.

> [!TIP]
> Si aún no tiene un servidor SIEM y está explorando sus opciones, **[considere la posibilidad de Microsoft Azure Sentinel](/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>¿Necesito un servidor SIEM?

Si necesita un servidor SIEM depende de muchos factores, como los requisitos de seguridad de su organización y dónde residen los datos. Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones sin servidores adicionales, como un servidor SIEM. Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor SIEM. Estos son algunos ejemplos:

- *Fabrikam* tiene contenido y aplicaciones locales y otras en la nube (tienen una implementación de nube híbrida). Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.
- *Contoso* es una organización de servicios financieros que tiene requisitos de seguridad especialmente estrictos. Han agregado un servidor SIEM a su entorno para aprovechar la protección de seguridad adicional que requieren.

## <a name="siem-server-integration-with-microsoft-365"></a>Integración del servidor SIEM con Microsoft 365

Un servidor SIEM puede recibir datos de una amplia variedad de Microsoft 365 y aplicaciones. En la tabla siguiente se enumeran varios Microsoft 365 y aplicaciones, junto con las entradas y recursos del servidor SIEM para obtener más información.

<br/><br/>

|Microsoft 365 Servicio o aplicación|Métodos y entradas de servidor SIEM|Recursos para obtener más información|
|---|---|---|
|[Microsoft Defender para Office 365](defender-for-office-365.md)|Registros de auditoría|[Integración de SIEM con Microsoft Defender para Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender para punto de conexión](/windows/security/threat-protection/)|Punto de conexión HTTPS hospedado en Azure <p> API de REST|[Extraer alertas a las herramientas SIEM](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Integración de registros|[Integración siem con Microsoft Cloud App Security](/cloud-app-security/siem)|

> [!TIP]
> Echa un vistazo a [Azure Sentinel](/azure/sentinel/overview). Azure Sentinel viene con conectores para soluciones de Microsoft. Estos conectores están disponibles "de forma completa" y proporcionan una integración en tiempo real. Puede usar Azure Sentinel con sus soluciones de Microsoft 365 Defender y servicios Microsoft 365, incluidos Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security y mucho más.

### <a name="audit-logging-must-be-turned-on"></a>El registro de auditoría debe estar activado

Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM.

- Para SharePoint Online, OneDrive para la Empresa y Azure Active Directory, vea Turn [auditing on or off](../../compliance/turn-audit-log-search-on-or-off.md).
- Para Exchange Online, vea [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Más recursos

[Integrar soluciones de seguridad en Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM](/graph/security-integration)
