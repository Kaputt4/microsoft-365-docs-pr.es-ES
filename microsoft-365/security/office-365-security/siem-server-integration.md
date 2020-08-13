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
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="023f3-103">Integración del servidor de información de seguridad y administración de eventos (SIEM) con los servicios y aplicaciones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="023f3-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="023f3-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="023f3-104">Summary</span></span>

<span data-ttu-id="023f3-105">¿Su organización usa o planea obtener un servidor de administración de eventos e información de seguridad (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="023f3-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="023f3-106">Es posible que se pregunte cómo se integra con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="023f3-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="023f3-107">En este artículo se proporciona una lista de los recursos que puede usar para integrar el servidor de SIEM con los servicios y aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="023f3-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="023f3-108">Si aún no tiene un servidor de SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="023f3-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="023f3-109">¿Necesito un servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="023f3-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="023f3-110">Si necesita un servidor de SIEM depende de muchos factores, como los requisitos de seguridad de la organización y dónde residen los datos.</span><span class="sxs-lookup"><span data-stu-id="023f3-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="023f3-111">Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones, sin servidores adicionales, como un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="023f3-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="023f3-112">Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="023f3-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="023f3-113">Aquí le mostramos otros ejemplos:</span><span class="sxs-lookup"><span data-stu-id="023f3-113">Here are some examples:</span></span>

- <span data-ttu-id="023f3-114">*Fabrikam* tiene algunos contenidos y aplicaciones locales, y algunos en la nube (tienen una implementación de nube híbrida).</span><span class="sxs-lookup"><span data-stu-id="023f3-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="023f3-115">Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="023f3-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="023f3-116">*Contoso* es una organización de servicios financieros que tiene requisitos de seguridad muy estrictos.</span><span class="sxs-lookup"><span data-stu-id="023f3-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="023f3-117">Han agregado un servidor de SIEM a su entorno para aprovechar la protección adicional de seguridad que necesitan.</span><span class="sxs-lookup"><span data-stu-id="023f3-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="023f3-118">Integración del servidor SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="023f3-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="023f3-119">Un servidor de SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="023f3-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="023f3-120">En la siguiente tabla se enumeran varios servicios y aplicaciones de Microsoft 365, junto con entradas y recursos del servidor SIEM para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="023f3-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="023f3-121">Servicio o aplicación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="023f3-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="023f3-122">Entradas y métodos del servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="023f3-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="023f3-123">Recursos para obtener más información</span><span class="sxs-lookup"><span data-stu-id="023f3-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="023f3-124">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="023f3-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="023f3-125">Registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="023f3-125">Audit logs</span></span>|[<span data-ttu-id="023f3-126">Integración de SIEM con Office 365 protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="023f3-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="023f3-127">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="023f3-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="023f3-128">Punto de conexión HTTPS hospedado en Azure</span><span class="sxs-lookup"><span data-stu-id="023f3-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="023f3-129">API REST</span><span class="sxs-lookup"><span data-stu-id="023f3-129">REST API</span></span>|[<span data-ttu-id="023f3-130">Extraer alertas a las herramientas de SIEM</span><span class="sxs-lookup"><span data-stu-id="023f3-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="023f3-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="023f3-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="023f3-132">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="023f3-132">Log integration</span></span>|[<span data-ttu-id="023f3-133">Integración de SIEM con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="023f3-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="023f3-134">Eche un vistazo a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="023f3-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="023f3-135">Azure Sentinel incluye conectores para soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="023f3-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="023f3-136">Estos conectores están disponibles "de la caja" y proporcionan la integración en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="023f3-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="023f3-137">Puede usar Azure Sentinel con sus soluciones de Microsoft Threat Protection y los servicios de Microsoft 365, incluidos Office 365, Azure AD, ATP de Azure, seguridad de aplicaciones en la nube de Microsoft y mucho más.</span><span class="sxs-lookup"><span data-stu-id="023f3-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="023f3-138">El registro de auditoría debe estar activado</span><span class="sxs-lookup"><span data-stu-id="023f3-138">Audit logging must be turned on</span></span>

<span data-ttu-id="023f3-139">Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="023f3-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="023f3-140">En SharePoint Online, OneDrive para la empresa y Azure Active Directory, [el registro de auditoría está activado en el centro de seguridad & cumplimiento](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="023f3-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="023f3-141">Para Exchange Online, consulte [Manage Mailbox Auditing](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="023f3-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="023f3-142">Más recursos</span><span class="sxs-lookup"><span data-stu-id="023f3-142">More resources</span></span>

[<span data-ttu-id="023f3-143">Integración de soluciones de seguridad en el centro de seguridad de Azure</span><span class="sxs-lookup"><span data-stu-id="023f3-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="023f3-144">Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="023f3-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
