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
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="0e91d-103">Integración del servidor de SIEM con los servicios y aplicaciones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e91d-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="0e91d-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="0e91d-104">Summary</span></span>

<span data-ttu-id="0e91d-105">Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), o si tiene previsto obtener un servidor de SIEM en breve, es posible que se pregunte cómo se integrará con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e91d-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0e91d-106">En este artículo se proporciona una lista de recursos que puede usar para configurar la integración del servidor de SIEM con sus aplicaciones y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0e91d-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="0e91d-107">Si aún no tiene un servidor de SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="0e91d-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="0e91d-108">¿Necesito un servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="0e91d-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="0e91d-109">Si necesita un servidor de SIEM depende de muchos factores, como los requisitos de seguridad de la organización y dónde residen los datos.</span><span class="sxs-lookup"><span data-stu-id="0e91d-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="0e91d-110">Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones, sin servidores adicionales, como un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="0e91d-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="0e91d-111">Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="0e91d-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="0e91d-112">Aquí le mostramos otros ejemplos:</span><span class="sxs-lookup"><span data-stu-id="0e91d-112">Here are some examples:</span></span>

- <span data-ttu-id="0e91d-113">*Fabrikam* tiene algunos contenidos y aplicaciones locales, y algunos en la nube (tienen una implementación de nube híbrida).</span><span class="sxs-lookup"><span data-stu-id="0e91d-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="0e91d-114">Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="0e91d-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="0e91d-115">*Contoso* es una organización de servicios financieros que tiene requisitos de seguridad muy estrictos.</span><span class="sxs-lookup"><span data-stu-id="0e91d-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="0e91d-116">Han agregado un servidor de SIEM a su entorno para aprovechar la protección adicional de seguridad que necesitan.</span><span class="sxs-lookup"><span data-stu-id="0e91d-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="0e91d-117">Integración del servidor SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e91d-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="0e91d-118">Un servidor de SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0e91d-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="0e91d-119">En la siguiente tabla se enumeran varios servicios y aplicaciones de Microsoft 365 junto con entradas del servidor SIEM y recursos para obtener más información sobre la integración del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="0e91d-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="0e91d-120">Servicio o aplicación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e91d-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="0e91d-121">Entradas del servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="0e91d-121">SIEM server inputs</span></span> | <span data-ttu-id="0e91d-122">Recursos para obtener más información</span><span class="sxs-lookup"><span data-stu-id="0e91d-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="0e91d-123">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="0e91d-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="0e91d-124">Registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="0e91d-124">Audit logs</span></span> | [<span data-ttu-id="0e91d-125">Integración de SIEM con Office 365 protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="0e91d-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="0e91d-126">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0e91d-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="0e91d-127">Punto de conexión HTTPS hospedado en Azure</span><span class="sxs-lookup"><span data-stu-id="0e91d-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="0e91d-128">API REST</span><span class="sxs-lookup"><span data-stu-id="0e91d-128">REST API</span></span>| [<span data-ttu-id="0e91d-129">Extraer alertas a las herramientas de SIEM</span><span class="sxs-lookup"><span data-stu-id="0e91d-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="0e91d-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e91d-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="0e91d-131">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="0e91d-131">Log integration</span></span> | [<span data-ttu-id="0e91d-132">Integración de SIEM con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e91d-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="0e91d-133">Eche un vistazo a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), que incluye varios conectores para las soluciones de Microsoft, disponibles de forma integrada en tiempo real, incluidas las soluciones de protección contra amenazas de Microsoft y orígenes de 365 de Microsoft, incluidos Office 365, Azure ad, ATP de Azure y Microsoft Cloud App Security, entre otros.</span><span class="sxs-lookup"><span data-stu-id="0e91d-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="0e91d-134">El registro de auditoría debe estar activado</span><span class="sxs-lookup"><span data-stu-id="0e91d-134">Audit logging must be turned on</span></span>

<span data-ttu-id="0e91d-135">Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="0e91d-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="0e91d-136">En SharePoint Online, OneDrive para la empresa y Azure Active Directory, [el registro de auditoría está activado en el centro de seguridad & cumplimiento](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="0e91d-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="0e91d-137">Para Exchange Online, el [registro de auditoría está activado con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="0e91d-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="0e91d-138">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="0e91d-138">Additional resources</span></span>

[<span data-ttu-id="0e91d-139">Integración de soluciones de seguridad en el centro de seguridad de Azure</span><span class="sxs-lookup"><span data-stu-id="0e91d-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="0e91d-140">Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="0e91d-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)