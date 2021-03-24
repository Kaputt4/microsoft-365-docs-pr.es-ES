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
description: Obtenga información general sobre la integración del servidor de administración de eventos y información de seguridad (SIEM) con sus aplicaciones y servicios en la nube de Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee164000d9a8dc9469097917658a88efe5cdc08c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072499"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="205e2-103">Integración de servidores de administración de eventos y información de seguridad (SIEM) con aplicaciones y servicios de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="205e2-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="205e2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="205e2-104">**Applies to**</span></span>
- [<span data-ttu-id="205e2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="205e2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="205e2-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="205e2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="205e2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="205e2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="205e2-108">Resumen</span><span class="sxs-lookup"><span data-stu-id="205e2-108">Summary</span></span>

<span data-ttu-id="205e2-109">¿Su organización está usando o planeando obtener un servidor de administración de eventos y información de seguridad (SIEM)</span><span class="sxs-lookup"><span data-stu-id="205e2-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="205e2-110">Es posible que se pregunte cómo se integra con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="205e2-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="205e2-111">En este artículo se proporciona una lista de recursos que puede usar para integrar el servidor SIEM con aplicaciones y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="205e2-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="205e2-112">Si aún no tiene un servidor SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="205e2-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="205e2-113">¿Necesito un servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="205e2-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="205e2-114">Si necesita un servidor SIEM depende de muchos factores, como los requisitos de seguridad de su organización y dónde residen los datos.</span><span class="sxs-lookup"><span data-stu-id="205e2-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="205e2-115">Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones sin servidores adicionales, como un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="205e2-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="205e2-116">Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="205e2-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="205e2-117">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="205e2-117">Here are some examples:</span></span>

- <span data-ttu-id="205e2-118">*Fabrikam* tiene contenido y aplicaciones locales y otras en la nube (tienen una implementación de nube híbrida).</span><span class="sxs-lookup"><span data-stu-id="205e2-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="205e2-119">Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="205e2-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="205e2-120">*Contoso* es una organización de servicios financieros que tiene requisitos de seguridad especialmente estrictos.</span><span class="sxs-lookup"><span data-stu-id="205e2-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="205e2-121">Han agregado un servidor SIEM a su entorno para aprovechar la protección de seguridad adicional que requieren.</span><span class="sxs-lookup"><span data-stu-id="205e2-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="205e2-122">Integración del servidor SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="205e2-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="205e2-123">Un servidor SIEM puede recibir datos de una amplia variedad de servicios y aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="205e2-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="205e2-124">En la tabla siguiente se enumeran varios servicios y aplicaciones de Microsoft 365, junto con entradas y recursos del servidor SIEM para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="205e2-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="205e2-125">Servicio o aplicación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="205e2-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="205e2-126">Métodos y entradas de servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="205e2-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="205e2-127">Recursos para obtener más información</span><span class="sxs-lookup"><span data-stu-id="205e2-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="205e2-128">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="205e2-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="205e2-129">Registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="205e2-129">Audit logs</span></span>|[<span data-ttu-id="205e2-130">Integración de SIEM con Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="205e2-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="205e2-131">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="205e2-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="205e2-132">Punto de conexión HTTPS hospedado en Azure</span><span class="sxs-lookup"><span data-stu-id="205e2-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="205e2-133">API REST</span><span class="sxs-lookup"><span data-stu-id="205e2-133">REST API</span></span>|[<span data-ttu-id="205e2-134">Extraer alertas a las herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="205e2-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="205e2-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="205e2-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="205e2-136">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="205e2-136">Log integration</span></span>|[<span data-ttu-id="205e2-137">Integración de SIEM con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="205e2-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="205e2-138">Echa un vistazo a [Azure Sentinel](/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="205e2-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="205e2-139">Azure Sentinel viene con conectores para soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="205e2-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="205e2-140">Estos conectores están disponibles "de forma completa" y proporcionan una integración en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="205e2-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="205e2-141">Puede usar Azure Sentinel con sus soluciones de Microsoft 365 Defender y los servicios de Microsoft 365, incluidos Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security y mucho más.</span><span class="sxs-lookup"><span data-stu-id="205e2-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="205e2-142">El registro de auditoría debe estar activado</span><span class="sxs-lookup"><span data-stu-id="205e2-142">Audit logging must be turned on</span></span>

<span data-ttu-id="205e2-143">Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="205e2-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="205e2-144">Para SharePoint Online, OneDrive para la Empresa y Azure Active Directory, el registro de auditoría está activado en el Centro de [seguridad & cumplimiento](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="205e2-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="205e2-145">Para Exchange Online, vea [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="205e2-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="205e2-146">Más recursos</span><span class="sxs-lookup"><span data-stu-id="205e2-146">More resources</span></span>

[<span data-ttu-id="205e2-147">Integrar soluciones de seguridad en Azure Defender</span><span class="sxs-lookup"><span data-stu-id="205e2-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="205e2-148">Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="205e2-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)