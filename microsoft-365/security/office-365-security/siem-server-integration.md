---
title: Integración del servidor SIEM con aplicaciones y servicios de Microsoft 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Obtenga información general sobre la integración del servidor de administración de eventos e información de seguridad (SIEM) con las aplicaciones y servicios en la nube de Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f29da87aa6eab1852330092d93187a27b2d36eb2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167148"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integración del servidor de administración de eventos e información de seguridad (SIEM) con servicios y aplicaciones de Microsoft 365

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Resumen

¿Su organización está usando o planeando obtener un servidor de administración de eventos e información de seguridad (SIEM)? Es posible que se pregunte cómo se integra con Microsoft 365 u Office 365. En este artículo se proporciona una lista de recursos que puede usar para integrar el servidor SIEM con aplicaciones y servicios de Microsoft 365.

> [!TIP]
> Si todavía no tiene un servidor SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>¿Necesito un servidor SIEM?

Si necesita un servidor SIEM depende de muchos factores, como los requisitos de seguridad de su organización y dónde residen los datos. Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones sin servidores adicionales, como un servidor SIEM. Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor SIEM. Aquí le mostramos otros ejemplos:

- *Fabrikam* tiene contenido y aplicaciones locales y otras en la nube (tienen una implementación en la nube híbrida). Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.

- *Contoso* es una organización de servicios financieros que tiene requisitos de seguridad especialmente estrictos. Han agregado un servidor SIEM a su entorno para aprovechar la protección de seguridad adicional que necesitan.

## <a name="siem-server-integration-with-microsoft-365"></a>Integración de servidores SIEM con Microsoft 365

Un servidor SIEM puede recibir datos de una amplia variedad de servicios y aplicaciones de Microsoft 365. En la tabla siguiente se enumeran varios servicios y aplicaciones de Microsoft 365, junto con los recursos y las entradas del servidor SIEM para obtener más información.

****

|Servicio o aplicación de Microsoft 365|Métodos o entradas de servidor SIEM|Recursos para obtener más información|
|---|---|---|
|[Microsoft Defender para Office 365](office-365-atp.md)|Registros de auditoría|[Integración de SIEM con Microsoft Defender para Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/)|Punto de conexión HTTPS hospedado en Azure <p> API REST|[Extraer alertas a las herramientas SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Integración de registros|[Integración de SIEM con Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Echa un vistazo a [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview) Azure Sentinel incluye conectores para soluciones de Microsoft. Estos conectores están disponibles "de forma personalizada" y proporcionan integración en tiempo real. Puede usar Azure Sentinel con las soluciones de Microsoft 365 Defender y los servicios de Microsoft 365, incluidos Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security y mucho más.

### <a name="audit-logging-must-be-turned-on"></a>El registro de auditoría debe estar activado

Asegúrese de que el registro de auditoría está activado antes de configurar la integración del servidor SIEM.

- Para SharePoint Online, OneDrive para la Empresa y Azure Active Directory, el registro de auditoría está activado en el Centro de [seguridad & cumplimiento.](../../compliance/turn-audit-log-search-on-or-off.md)

- Para Exchange Online, consulte [Administrar la auditoría de buzones](../../compliance/enable-mailbox-auditing.md)de correo.

## <a name="more-resources"></a>Más recursos

[Integrar soluciones de seguridad en Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM](https://docs.microsoft.com/graph/security-integration)
