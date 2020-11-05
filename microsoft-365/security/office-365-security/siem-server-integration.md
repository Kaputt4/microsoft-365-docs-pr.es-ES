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
ms.openlocfilehash: 17e21d19463187744afe855b2304ac71956545d2
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919769"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="9ca0f-103">Integración del servidor de información de seguridad y administración de eventos (SIEM) con los servicios y aplicaciones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ca0f-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="9ca0f-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="9ca0f-104">Summary</span></span>

<span data-ttu-id="9ca0f-105">¿Su organización usa o planea obtener un servidor de administración de eventos e información de seguridad (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="9ca0f-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="9ca0f-106">Es posible que se pregunte cómo se integra con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9ca0f-107">En este artículo se proporciona una lista de los recursos que puede usar para integrar el servidor de SIEM con los servicios y aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="9ca0f-108">Si aún no tiene un servidor de SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="9ca0f-109">¿Necesito un servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="9ca0f-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="9ca0f-110">Si necesita un servidor de SIEM depende de muchos factores, como los requisitos de seguridad de la organización y dónde residen los datos.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="9ca0f-111">Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones, sin servidores adicionales, como un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="9ca0f-112">Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="9ca0f-113">Aquí le mostramos otros ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9ca0f-113">Here are some examples:</span></span>

- <span data-ttu-id="9ca0f-114">*Fabrikam* tiene algunos contenidos y aplicaciones locales, y algunos en la nube (tienen una implementación de nube híbrida).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="9ca0f-115">Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="9ca0f-116">*Contoso* es una organización de servicios financieros que tiene requisitos de seguridad muy estrictos.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="9ca0f-117">Han agregado un servidor de SIEM a su entorno para aprovechar la protección adicional de seguridad que necesitan.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="9ca0f-118">Integración del servidor SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ca0f-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="9ca0f-119">Un servidor de SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="9ca0f-120">En la siguiente tabla se enumeran varios servicios y aplicaciones de Microsoft 365, junto con entradas y recursos del servidor SIEM para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="9ca0f-121">Servicio o aplicación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ca0f-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="9ca0f-122">Entradas y métodos del servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="9ca0f-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="9ca0f-123">Recursos para obtener más información</span><span class="sxs-lookup"><span data-stu-id="9ca0f-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="9ca0f-124">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9ca0f-124">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="9ca0f-125">Registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="9ca0f-125">Audit logs</span></span>|[<span data-ttu-id="9ca0f-126">Integración de SIEM con Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9ca0f-126">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="9ca0f-127">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9ca0f-127">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="9ca0f-128">Punto de conexión HTTPS hospedado en Azure</span><span class="sxs-lookup"><span data-stu-id="9ca0f-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="9ca0f-129">API REST</span><span class="sxs-lookup"><span data-stu-id="9ca0f-129">REST API</span></span>|[<span data-ttu-id="9ca0f-130">Extraer alertas a las herramientas de SIEM</span><span class="sxs-lookup"><span data-stu-id="9ca0f-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="9ca0f-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9ca0f-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="9ca0f-132">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="9ca0f-132">Log integration</span></span>|[<span data-ttu-id="9ca0f-133">Integración de SIEM con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9ca0f-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="9ca0f-134">Eche un vistazo a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="9ca0f-135">Azure Sentinel incluye conectores para soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="9ca0f-136">Estos conectores están disponibles "de la caja" y proporcionan la integración en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="9ca0f-137">Puede usar Azure Sentinel con las soluciones de Microsoft 365 defender y los servicios de Microsoft 365, incluidos Office 365, Azure AD, Microsoft defender para identidad, seguridad de la aplicación en la nube de Microsoft y mucho más.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-137">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="9ca0f-138">El registro de auditoría debe estar activado</span><span class="sxs-lookup"><span data-stu-id="9ca0f-138">Audit logging must be turned on</span></span>

<span data-ttu-id="9ca0f-139">Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="9ca0f-140">En SharePoint Online, OneDrive para la empresa y Azure Active Directory, [el registro de auditoría está activado en el centro de seguridad & cumplimiento](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="9ca0f-141">Para Exchange Online, consulte [Manage Mailbox Auditing](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="9ca0f-142">Más recursos</span><span class="sxs-lookup"><span data-stu-id="9ca0f-142">More resources</span></span>

[<span data-ttu-id="9ca0f-143">Integración de soluciones de seguridad en Azure defender</span><span class="sxs-lookup"><span data-stu-id="9ca0f-143">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="9ca0f-144">Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="9ca0f-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
