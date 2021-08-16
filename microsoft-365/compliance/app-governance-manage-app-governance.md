---
title: Gobernanza de aplicaciones en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Implemente funcionalidades de gobernanza de aplicaciones de Microsoft para controlar sus aplicaciones.
ms.openlocfilehash: 2b11893b17c93bb92301bc07fda3422ad4c36228
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58256844"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Complemento de gobernanza de aplicaciones para Microsoft Cloud App Security (en versión preliminar)

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

> [!NOTE]
> Para suscribirse a la gobernanza de aplicaciones, consulte [Introducción a la gobernanza de aplicaciones (en versión preliminar)](app-governance-get-started.md#sign-up-for-free-trial-of-app-governance).

Los ciberataques se han vuelto cada vez más sofisticados en las formas en que aprovechan las aplicaciones que ha implementado en sus infraestructuras locales y en la nube, estableciendo un punto de partida para la elevación de privilegios, el movimiento lateral y la filtración de los datos. Para comprender los posibles riesgos y detener estos tipos de ataques, debe obtener una visibilidad clara de la posición de cumplimiento de aplicaciones de su organización para identificar rápidamente cuándo una aplicación muestra comportamientos anómalos y responder cuando estos comportamientos presentan riesgos para su entorno, datos y usuarios.

La característica de complemento de gobernanza de aplicaciones para Microsoft Cloud App Security es una funcionalidad de administración de directivas y seguridad diseñada para aplicaciones habilitadas para OAuth que acceden a datos de Microsoft 365 a través de Microsoft Graph APIs. La gobernanza de aplicaciones ofrece visibilidad, corrección y gobernanza completas sobre cómo estas aplicaciones y sus usuarios acceden, usan y comparten sus datos confidenciales almacenados en Microsoft 365 a través de información útil, y alertas y acciones de directivas automatizadas.

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

La gobernanza de aplicaciones le proporciona una solución completa:

- **Información**: consulte una vista de todas las aplicaciones de terceros para la plataforma de Microsoft 365 en su usuario en un único panel. Puede ver todos los estados de las aplicaciones y las actividades de alerta, y reaccionar o responder a ellas.
- **Gobernanza**: cree directivas proactivas o reactivas para patrones y comportamientos de aplicaciones y usuarios, y proteja a los usuarios contra el uso de aplicaciones no compatibles o malintencionadas limitando el acceso de aplicaciones de riesgo a sus datos.
- **Detección**: reciba alertas y notificaciones cuando haya anomalías en la actividad de la aplicación y cuando se usen aplicaciones no compatibles, malintencionadas o de riesgo.
- **Corrección**: junto con las capacidades de corrección automática, use controles de corrección de manera oportuna para responder a las detecciones de actividad anómala en las aplicaciones.

La gobernanza de aplicaciones es una solución basada en una plataforma que forma parte integral del ecosistema de aplicaciones de Microsoft 365. La gobernanza de aplicaciones supervisa y controla las aplicaciones habilitadas para OAuth que están registradas con Azure Active Directory (Azure AD) y acceden a los datos a través de la API de Microsoft Graph. La gobernanza de aplicaciones proporciona controles de comportamiento de la aplicación para ayudar a reforzar la posición de seguridad y cumplimiento de su infraestructura de TI.

## <a name="a-first-glimpse-at-app-governance"></a>Primer vistazo a la gobernanza de aplicaciones

Para ver el panel de gobernanza de aplicaciones, diríjase a [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance). Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de los [roles de administrador](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security

La gobernanza de aplicaciones, Azure AD y Microsoft Cloud App Security recopilan y proporcionan diferentes conjuntos de datos:

- La gobernanza de aplicaciones proporciona información detallada sobre la actividad de una aplicación en el nivel de API.
- Azure AD proporciona metadatos de aplicaciones fundamentales e información detallada sobre los inicios de sesión en las aplicaciones.
- Microsoft Cloud App Security proporciona información de riesgo de la aplicación.

Al compartir información entre el gobierno de aplicaciones, Azure AD y Microsoft Cloud App Security, puede mostrar información agregada en un portal y vincular fácilmente a otro portal para obtener más información. Aquí hay unos ejemplos:

- Información de inicio de sesión de la aplicación en la gobernanza de aplicaciones:

  Desde el portal de gobernanza de aplicaciones, puede ver la actividad de inicio de sesión agregada de cada aplicación y volver a vincularla al centro de administración de Azure Active Directory para obtener los detalles de los eventos de inicio de sesión.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Información del uso de la API en el portal de Microsoft Cloud App Security:

  Desde el portal de Microsoft Cloud App Security, puede visualizar el nivel de uso de la API, la transferencia de datos agregados y el vínculo al portal de gobernanza de aplicaciones para obtener los detalles.

Este es un resumen de la integración.

![La Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Además, la gobernanza de aplicaciones envía sus alertas como señales a Microsoft Cloud App Security y Microsoft 365 Defender, y la gobernanza de aplicaciones recibe alertas de Microsoft Cloud App Security para permitir un análisis más detallado de los incidentes de seguridad basados en aplicaciones.

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->
