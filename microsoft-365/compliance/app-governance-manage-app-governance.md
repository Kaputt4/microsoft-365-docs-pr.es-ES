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
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Implemente funcionalidades de gobernanza de aplicaciones de Microsoft para controlar sus aplicaciones.
ms.openlocfilehash: ca1a77c4f5a1543a000b563dde98238136b3115d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189554"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Complemento de gobernanza de aplicaciones para Microsoft Cloud App Security (en versión preliminar)

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

> [!NOTE]
> Para suscribirse a la gobernanza de aplicaciones, consulte [Introducción a la gobernanza de aplicaciones (en versión preliminar)](app-governance-get-started.md).

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

Para ver el panel de control de la aplicación, diríjase a [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance). Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de los [roles de administrador](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobierno de la aplicación.

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

![La Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security.](..\media\manage-app-protection-governance\mapg-integration.png)

La gobernanza de aplicaciones envía sus alertas como señales a Microsoft Cloud App Security y Microsoft 365 Defender, y recibe alertas de Microsoft Cloud App Security para permitir un análisis más detallado de los incidentes de seguridad basados en aplicaciones.
- Las alertas de la gobernanza de aplicaciones se muestran en la lista de alertas de Microsoft 365 Defender como alertas con el campo Origen de detección establecido en "Gobernanza de aplicaciones"
- Las alertas de la gobernanza de aplicaciones se muestran en la lista de alertas de MCAS como alertas con el campo Directiva establecido en alguna de las siguientes opciones:
  - Gobernanza de aplicaciones de OAuth de Microsoft 365
  - Detección de suplantación de identidad (phishing) de OAuth de Microsoft 365
  - Reputación de las aplicaciones de OAuth de Microsoft 365
- Las alertas MCAS aparecen en la lista de alertas de la gobernanza de aplicaciones como alertas con el Origen establecido en MCAS

> [!NOTE]
> El estado de las alertas no se está sincronizando actualmente entre la gobernanza de aplicaciones y Microsoft Cloud App Security.
