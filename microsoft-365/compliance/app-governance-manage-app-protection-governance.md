---
title: Gobernanza de aplicaciones en Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: bc8c739132de52abb69c15479cd851462e9f6ce7
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420310"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="ff0d7-103">Complemento de gobernanza de aplicaciones para Microsoft Cloud App Security (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ff0d7-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="ff0d7-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="ff0d7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ff0d7-105">Los ciberataques se han vuelto cada vez más sofisticados en las formas en que aprovechan las aplicaciones que ha implementado en sus infraestructuras locales y en la nube, estableciendo un punto de partida para la elevación de privilegios, el movimiento lateral y la filtración de los datos.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="ff0d7-106">Para comprender los posibles riesgos y detener estos tipos de ataques, debe obtener una visibilidad clara de la posición de cumplimiento de aplicaciones de su organización para identificar rápidamente cuándo una aplicación muestra comportamientos anómalos y responder cuando estos comportamientos presentan riesgos para su entorno, datos y usuarios.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="ff0d7-107">La característica de complemento de gobernanza de aplicaciones para Microsoft Cloud App Security es una funcionalidad de administración de directivas y seguridad diseñada para aplicaciones habilitadas para OAuth que acceden a datos de Microsoft 365 a través de Microsoft Graph APIs.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="ff0d7-108">La gobernanza de aplicaciones ofrece visibilidad, corrección y gobernanza completas sobre cómo estas aplicaciones y sus usuarios acceden, usan y comparten sus datos confidenciales almacenados en Microsoft 365 a través de información útil, y alertas y acciones de directivas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="ff0d7-109">La gobernanza de aplicaciones le proporciona una solución completa:</span><span class="sxs-lookup"><span data-stu-id="ff0d7-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="ff0d7-110">**Información**: consulte una vista de todas las aplicaciones de terceros para la plataforma de Microsoft 365 en su usuario en un único panel.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="ff0d7-111">Puede ver todos los estados de las aplicaciones y las actividades de alerta, y reaccionar o responder a ellas.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="ff0d7-112">**Gobernanza**: cree directivas proactivas o reactivas para patrones y comportamientos de aplicaciones y usuarios, y proteja a los usuarios contra el uso de aplicaciones no compatibles o malintencionadas limitando el acceso de aplicaciones de riesgo a sus datos.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="ff0d7-113">**Detección**: reciba alertas y notificaciones cuando haya anomalías en la actividad de la aplicación y cuando se usen aplicaciones no compatibles, malintencionadas o de riesgo.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="ff0d7-114">**Corrección**: junto con las capacidades de corrección automática, use controles de corrección de manera oportuna para responder a las detecciones de actividad anómala en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="ff0d7-115">La gobernanza de aplicaciones es una solución basada en una plataforma que forma parte integral del ecosistema de aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="ff0d7-116">La gobernanza de aplicaciones supervisa y controla las aplicaciones habilitadas para OAuth que están registradas con Azure Active Directory (Azure AD) y acceden a los datos a través de la API de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="ff0d7-117">La gobernanza de aplicaciones proporciona controles de comportamiento de la aplicación para ayudar a reforzar la posición de seguridad y cumplimiento de su infraestructura de TI.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="ff0d7-118">Primer vistazo a la gobernanza de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ff0d7-118">A first glimpse at app governance</span></span>

<span data-ttu-id="ff0d7-119">Para ver el panel de gobernanza de aplicaciones, diríjase a [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="ff0d7-119">To see the app governance dashboard, go to [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="ff0d7-120">Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de los [roles de administrador](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="ff0d7-121">Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ff0d7-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="ff0d7-122">La gobernanza de aplicaciones, Azure AD y Microsoft Cloud App Security recopilan y proporcionan diferentes conjuntos de datos:</span><span class="sxs-lookup"><span data-stu-id="ff0d7-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="ff0d7-123">La gobernanza de aplicaciones proporciona información detallada sobre la actividad de una aplicación en el nivel de API.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="ff0d7-124">Azure AD proporciona metadatos de aplicaciones fundamentales e información detallada sobre los inicios de sesión en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="ff0d7-125">Microsoft Cloud App Security proporciona información de riesgo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="ff0d7-126">Al compartir información entre la gobernanza de aplicaciones, Azure AD y Microsoft Cloud App Security, puede mostrar información agregada en un portal y vincular fácilmente a otro portal para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-126">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information.</span></span> <span data-ttu-id="ff0d7-127">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="ff0d7-127">Here are some examples:</span></span>

- <span data-ttu-id="ff0d7-128">Información de inicio de sesión de la aplicación en la gobernanza de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="ff0d7-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="ff0d7-129">Desde el portal de gobernanza de aplicaciones, puede ver la actividad de inicio de sesión agregada de cada aplicación y volver a vincularla al centro de administración de Azure Active Directory para obtener los detalles de los eventos de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="ff0d7-130">Información del uso de la API en el portal de Microsoft Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="ff0d7-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="ff0d7-131">Desde el portal de Microsoft Cloud App Security, puede visualizar el nivel de uso de la API, la transferencia de datos agregados y el vínculo al portal de gobernanza de aplicaciones para obtener los detalles.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="ff0d7-132">Este es un resumen de la integración.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-132">Here's a summary of the integration.</span></span>

![La Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="ff0d7-134">Además, la gobernanza de aplicaciones envía sus alertas como señales a Microsoft Cloud App Security y Microsoft 365 Defender, y la gobernanza de aplicaciones recibe alertas de Microsoft Cloud App Security para permitir un análisis más detallado de los incidentes de seguridad basados en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

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

## <a name="using-app-governance"></a><span data-ttu-id="ff0d7-135">Uso de la gobernanza de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ff0d7-135">Using app governance</span></span>

<span data-ttu-id="ff0d7-136">El uso de la gobernanza de aplicaciones para proteger su usuario y sus datos de aplicaciones potencialmente malignas o malintencionadas se divide en estas tres funcionalidades principales:</span><span class="sxs-lookup"><span data-stu-id="ff0d7-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="ff0d7-137">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="ff0d7-137">Capability</span></span> | <span data-ttu-id="ff0d7-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff0d7-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="ff0d7-139">Visibilidad e información de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ff0d7-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="ff0d7-140">Obtenga una vista de 360° sobre el tráfico y la actividad de las aplicaciones de Microsoft 365 en su usuario.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="ff0d7-141">Directivas de aplicación para una gobernanza sólida</span><span class="sxs-lookup"><span data-stu-id="ff0d7-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="ff0d7-142">Cree directivas de aplicaciones proactivas o reactivas, lo cual le permitirá aplicar la gobernanza para sus aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="ff0d7-143">Detección y correcciones</span><span class="sxs-lookup"><span data-stu-id="ff0d7-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="ff0d7-144">En función de las alertas de detección de plataforma o las alertas de detección generadas por directivas, supervise sus aplicaciones en busca de comportamientos anómalos de aplicaciones y corríjalas, ya sea automáticamente en función de la configuración de la directiva de la aplicación o manualmente.</span><span class="sxs-lookup"><span data-stu-id="ff0d7-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
