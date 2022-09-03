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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Obtenga información general sobre la integración del servidor de Administración de eventos e información de seguridad (SIEM) con sus aplicaciones y servicios en la nube de Microsoft 365
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 9f76a4d80844b491a5896db489a23b58db9bb153
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67595969"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integración del servidor de administración de eventos e información de seguridad (SIEM) con aplicaciones y servicios de Microsoft 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

## <a name="summary"></a>Resumen

¿Su organización usa o planea obtener un servidor de administración de eventos e información de seguridad (SIEM)? Es posible que se pregunte cómo se integra con Microsoft 365 o Office 365. En este artículo se proporciona una lista de recursos que puede usar para integrar el servidor SIEM con aplicaciones y servicios de Microsoft 365.

> [!TIP]
> Si aún no tiene un servidor SIEM y está explorando sus opciones, considere la posibilidad de **[usar Microsoft Sentinel](/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>¿Necesito un servidor SIEM?

Si necesita un servidor SIEM depende de muchos factores, como los requisitos de seguridad de su organización y dónde residen los datos. Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones sin servidores adicionales, como un servidor SIEM. Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor SIEM. Estos son algunos ejemplos:

- *Fabrikam* tiene contenido y aplicaciones locales, y otras en la nube (tienen una implementación de nube híbrida). Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.
- *Contoso* es una organización de servicios financieros que tiene requisitos de seguridad particularmente estrictos. Han agregado un servidor SIEM a su entorno para aprovechar la protección de seguridad adicional que necesitan.

## <a name="siem-server-integration-with-microsoft-365"></a>Integración del servidor SIEM con Microsoft 365

Un servidor SIEM puede recibir datos de una amplia variedad de servicios y aplicaciones de Microsoft 365. En la tabla siguiente se enumeran varios servicios y aplicaciones de Microsoft 365, junto con entradas y recursos del servidor SIEM para obtener más información.

<br/><br/>

|Servicio o aplicación de Microsoft 365|Métodos o entradas del servidor SIEM|Recursos para obtener más información|
|---|---|---|
|[Microsoft Defender para Office 365](defender-for-office-365.md)|Registros de auditoría|[Integración de SIEM con Microsoft Defender para Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender para punto de conexión](/windows/security/threat-protection/)|Punto de conexión HTTPS hospedado en Azure <p> API REST|[Extracción de alertas en las herramientas SIEM](../defender-endpoint/configure-siem.md)|
|[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)|Integración de registros|[Integración de SIEM con Microsoft Defender for Cloud Apps](/cloud-app-security/siem)|

> [!TIP]
> Eche un vistazo a [Microsoft Sentinel](/azure/sentinel/overview). Microsoft Sentinel incluye conectores para soluciones de Microsoft. Estos conectores están disponibles "de forma inmediata" y proporcionan integración en tiempo real. Puede usar Microsoft Sentinel con sus soluciones de Microsoft 365 Defender y servicios de Microsoft 365, incluidos Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Defender for Cloud Apps, etc. .

### <a name="audit-logging-must-be-turned-on"></a>El registro de auditoría debe estar activado

Asegúrese de que el registro de auditoría está activado antes de configurar la integración del servidor SIEM.

- Para SharePoint Online, OneDrive para la Empresa y Azure Active Directory, consulte [Activar o desactivar la auditoría](../../compliance/turn-audit-log-search-on-or-off.md).
- Para obtener Exchange Online, consulte [Administración de la auditoría de buzones](../../compliance/enable-mailbox-auditing.md).

## <a name="integration-steps-if-your-siem-is-microsoft-sentinel"></a>Pasos de integración si siem es Microsoft Sentinel

Asegúrese de que el plan actual permite la integración de Microsoft Sentinel (por ejemplo, tiene Microsoft Defender para Office 365 plan 2 o superior) y que su cuenta de Microsoft Defender para Office 365 o Microsoft 365 Defender es una *Administrador de seguridad*. Por último, asegúrese de que tiene *permisos de escritura en Microsoft Sentinel*.

1. Vaya a Microsoft Sentinel.
1. En la navegación a la izquierda de la pantalla **Conectores de datos** de **configuración** > .
1. **Busque** Microsoft 365 Defender y seleccione el **conector Microsoft 365 Defender (versión preliminar).**
1. A la derecha de la pantalla, seleccione **Abrir página del conector**.
1. En **Configuración** > seleccione **Conectar incidentes & alertas**
    1. Desactive todas las reglas de creación de incidentes de Microsoft para los productos seleccionados actualmente.
1. Desplácese hasta **Microsoft Defender para Office 365** en la sección **Conectar eventos** de la página.

Tenga en cuenta que puede elegir tablas de *cualquier otro producto de Microsoft Defender* que le resulte útil y aplicable al completar el paso final (a continuación).

7. Seleccione **EmailEvents**, **EmailUrlInfo**, **EmailAttachmentInfo** y **EmailPostDeliveryEvents** > y **Aplicar cambios**.

## <a name="more-resources"></a>Más recursos

[Integración de soluciones de seguridad en Microsoft Defender for Cloud](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM](/graph/security-integration)
