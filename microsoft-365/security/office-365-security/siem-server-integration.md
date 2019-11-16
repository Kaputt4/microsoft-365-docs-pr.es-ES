---
title: Integración del servidor de SIEM con los servicios y aplicaciones de Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Lea este artículo para obtener información general sobre la integración del servidor SIEM con Microsoft 365.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677513"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integración del servidor de SIEM con los servicios y aplicaciones de Microsoft 365

## <a name="summary"></a>Resumen

Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), o si tiene previsto obtener un servidor de SIEM en breve, es posible que se pregunte cómo se integrará con Microsoft 365 u Office 365. En este artículo se proporciona una lista de recursos que puede usar para configurar la integración del servidor de SIEM con sus aplicaciones y servicios de Microsoft 365.

> [!TIP]
> Si aún no tiene un servidor de SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>¿Necesito un servidor SIEM?

Si necesita un servidor de SIEM depende de muchos factores, como los requisitos de seguridad de la organización y dónde residen los datos. Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones, sin servidores adicionales, como un servidor SIEM. Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor de SIEM. Aquí le mostramos otros ejemplos:

- *Fabrikam* tiene algunos contenidos y aplicaciones locales, y algunos en la nube (tienen una implementación de nube híbrida). Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM. 

- *Contoso* es una organización de servicios financieros que tiene requisitos de seguridad muy estrictos. Han agregado un servidor de SIEM a su entorno para aprovechar la protección adicional de seguridad que necesitan.

## <a name="siem-server-integration-with-microsoft-365"></a>Integración del servidor SIEM con Microsoft 365

Un servidor de SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365. En la siguiente tabla se enumeran varios servicios y aplicaciones de Microsoft 365 junto con entradas del servidor SIEM y recursos para obtener más información sobre la integración del servidor SIEM. 

| Servicio o aplicación de Microsoft 365 | Entradas del servidor SIEM | Recursos para obtener más información |
| --- | --- | --- |
| [Protección contra amenazas avanzada de Office 365](office-365-atp.md)  | Registros de auditoría | [Integración de SIEM con Office 365 protección contra amenazas avanzada](siem-integration-with-office-365-ti.md) |
| [Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) | Punto de conexión HTTPS hospedado en Azure <br/>API REST| [Extraer alertas a las herramientas de SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integración de registros | [Integración de SIEM con Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> Eche un vistazo a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), que incluye varios conectores para las soluciones de Microsoft, disponibles de forma integrada en tiempo real, incluidas las soluciones de protección contra amenazas de Microsoft y orígenes de 365 de Microsoft, incluidos Office 365, Azure ad, ATP de Azure y Microsoft Cloud App Security, entre otros.

### <a name="audit-logging-must-be-turned-on"></a>El registro de auditoría debe estar activado

Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM. 

- En SharePoint Online, OneDrive para la empresa y Azure Active Directory, [el registro de auditoría está activado en el centro de seguridad & cumplimiento](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Para Exchange Online, el [registro de auditoría está activado con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="additional-resources"></a>Otros recursos

[Integración de soluciones de seguridad en el centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM](https://docs.microsoft.com/graph/security-integration)