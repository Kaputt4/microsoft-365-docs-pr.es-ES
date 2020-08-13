---
title: Integración del servidor de SIEM con los servicios y aplicaciones de Microsoft 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Obtenga información general sobre la integración de la información de seguridad y la administración de eventos (SIEM) con sus aplicaciones y servicios en la nube de Microsoft 365
ms.openlocfilehash: d2be5e0127adf25b3884e3717caccf60d4db1d28
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653582"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integración del servidor de información de seguridad y administración de eventos (SIEM) con los servicios y aplicaciones de Microsoft 365

## <a name="summary"></a>Resumen

¿Su organización usa o planea obtener un servidor de administración de eventos e información de seguridad (SIEM)? Es posible que se pregunte cómo se integra con Microsoft 365 u Office 365. En este artículo se proporciona una lista de los recursos que puede usar para integrar el servidor de SIEM con los servicios y aplicaciones de Microsoft 365.

> [!TIP]
> Si aún no tiene un servidor de SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>¿Necesito un servidor SIEM?

Si necesita un servidor de SIEM depende de muchos factores, como los requisitos de seguridad de la organización y dónde residen los datos. Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones, sin servidores adicionales, como un servidor SIEM. Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor de SIEM. Aquí le mostramos otros ejemplos:

- *Fabrikam* tiene algunos contenidos y aplicaciones locales, y algunos en la nube (tienen una implementación de nube híbrida). Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.

- *Contoso* es una organización de servicios financieros que tiene requisitos de seguridad muy estrictos. Han agregado un servidor de SIEM a su entorno para aprovechar la protección adicional de seguridad que necesitan.

## <a name="siem-server-integration-with-microsoft-365"></a>Integración del servidor SIEM con Microsoft 365

Un servidor de SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365. En la siguiente tabla se enumeran varios servicios y aplicaciones de Microsoft 365, junto con entradas y recursos del servidor SIEM para obtener más información.

****

|Servicio o aplicación de Microsoft 365|Entradas y métodos del servidor SIEM|Recursos para obtener más información|
|---|---|---|
|[Protección contra amenazas avanzada de Office 365](office-365-atp.md)|Registros de auditoría|[Integración de SIEM con Office 365 protección contra amenazas avanzada](siem-integration-with-office-365-ti.md)|
|[Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)|Punto de conexión HTTPS hospedado en Azure <br/>API REST|[Extraer alertas a las herramientas de SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Integración de registros|[Integración de SIEM con Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Eche un vistazo a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview). Azure Sentinel incluye conectores para soluciones de Microsoft. Estos conectores están disponibles "de la caja" y proporcionan la integración en tiempo real. Puede usar Azure Sentinel con sus soluciones de Microsoft Threat Protection y los servicios de Microsoft 365, incluidos Office 365, Azure AD, ATP de Azure, seguridad de aplicaciones en la nube de Microsoft y mucho más.

### <a name="audit-logging-must-be-turned-on"></a>El registro de auditoría debe estar activado

Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM.

- En SharePoint Online, OneDrive para la empresa y Azure Active Directory, [el registro de auditoría está activado en el centro de seguridad & cumplimiento](../../compliance/turn-audit-log-search-on-or-off.md).

- Para Exchange Online, consulte [Manage Mailbox Auditing](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Más recursos

[Integración de soluciones de seguridad en el centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM](https://docs.microsoft.com/graph/security-integration)
