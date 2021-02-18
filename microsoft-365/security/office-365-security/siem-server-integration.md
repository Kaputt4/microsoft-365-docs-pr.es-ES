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
description: Obtener información general sobre la integración del servidor de administración de eventos e información de seguridad (SIEM) con las aplicaciones y servicios en la nube de Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290386"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="d1e00-103">Integración del servidor de administración de eventos e información de seguridad (SIEM) con servicios y aplicaciones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1e00-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="d1e00-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="d1e00-104">**Applies to**</span></span>
- [<span data-ttu-id="d1e00-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d1e00-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d1e00-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d1e00-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d1e00-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1e00-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="d1e00-108">Resumen</span><span class="sxs-lookup"><span data-stu-id="d1e00-108">Summary</span></span>

<span data-ttu-id="d1e00-109">¿Su organización está usando o planeando obtener un servidor de administración de eventos e información de seguridad (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="d1e00-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="d1e00-110">Es posible que se pregunte cómo se integra con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1e00-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d1e00-111">En este artículo se proporciona una lista de recursos que puede usar para integrar el servidor SIEM con aplicaciones y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1e00-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="d1e00-112">Si todavía no tiene un servidor SIEM y está explorando sus opciones, considere **[Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="d1e00-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="d1e00-113">¿Necesito un servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="d1e00-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="d1e00-114">Si necesita un servidor SIEM depende de muchos factores, como los requisitos de seguridad de su organización y dónde residen los datos.</span><span class="sxs-lookup"><span data-stu-id="d1e00-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="d1e00-115">Microsoft 365 incluye una amplia variedad de características de seguridad que satisfacen las necesidades de seguridad de muchas organizaciones sin servidores adicionales, como un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="d1e00-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="d1e00-116">Algunas organizaciones tienen circunstancias especiales que requieren el uso de un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="d1e00-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="d1e00-117">Aquí le mostramos otros ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1e00-117">Here are some examples:</span></span>

- <span data-ttu-id="d1e00-118">*Fabrikam* tiene contenido y aplicaciones locales y otras en la nube (tienen una implementación en la nube híbrida).</span><span class="sxs-lookup"><span data-stu-id="d1e00-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="d1e00-119">Para obtener informes de seguridad en todo su contenido y aplicaciones, Fabrikam ha implementado un servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="d1e00-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="d1e00-120">*Contoso* es una organización de servicios financieros que tiene requisitos de seguridad especialmente estrictos.</span><span class="sxs-lookup"><span data-stu-id="d1e00-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="d1e00-121">Han agregado un servidor SIEM a su entorno para aprovechar la protección de seguridad adicional que necesitan.</span><span class="sxs-lookup"><span data-stu-id="d1e00-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="d1e00-122">Integración de servidores SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1e00-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="d1e00-123">Un servidor SIEM puede recibir datos de una amplia variedad de servicios y aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1e00-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="d1e00-124">En la tabla siguiente se enumeran varios servicios y aplicaciones de Microsoft 365, junto con los recursos y las entradas del servidor SIEM para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d1e00-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="d1e00-125">Servicio o aplicación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1e00-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="d1e00-126">Métodos o entradas de servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="d1e00-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="d1e00-127">Recursos para obtener más información</span><span class="sxs-lookup"><span data-stu-id="d1e00-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="d1e00-128">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d1e00-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="d1e00-129">Registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="d1e00-129">Audit logs</span></span>|[<span data-ttu-id="d1e00-130">Integración de SIEM con Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d1e00-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="d1e00-131">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d1e00-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="d1e00-132">Punto de conexión HTTPS hospedado en Azure</span><span class="sxs-lookup"><span data-stu-id="d1e00-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="d1e00-133">API REST</span><span class="sxs-lookup"><span data-stu-id="d1e00-133">REST API</span></span>|[<span data-ttu-id="d1e00-134">Extraer alertas a las herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="d1e00-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="d1e00-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d1e00-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="d1e00-136">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="d1e00-136">Log integration</span></span>|[<span data-ttu-id="d1e00-137">Integración de SIEM con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d1e00-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="d1e00-138">Echa un vistazo a [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="d1e00-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="d1e00-139">Azure Sentinel incluye conectores para soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1e00-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="d1e00-140">Estos conectores están disponibles "de forma personalizada" y proporcionan integración en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d1e00-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="d1e00-141">Puede usar Azure Sentinel con las soluciones de Microsoft 365 Defender y los servicios de Microsoft 365, incluidos Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security y mucho más.</span><span class="sxs-lookup"><span data-stu-id="d1e00-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="d1e00-142">El registro de auditoría debe estar activado</span><span class="sxs-lookup"><span data-stu-id="d1e00-142">Audit logging must be turned on</span></span>

<span data-ttu-id="d1e00-143">Asegúrese de que el registro de auditoría está activado antes de configurar la integración del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="d1e00-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="d1e00-144">Para SharePoint Online, OneDrive para la Empresa y Azure Active Directory, el registro de auditoría está activado en el Centro de [seguridad & cumplimiento.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="d1e00-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="d1e00-145">Para Exchange Online, consulte [Administrar la auditoría de buzones](../../compliance/enable-mailbox-auditing.md)de correo.</span><span class="sxs-lookup"><span data-stu-id="d1e00-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="d1e00-146">Más recursos</span><span class="sxs-lookup"><span data-stu-id="d1e00-146">More resources</span></span>

[<span data-ttu-id="d1e00-147">Integrar soluciones de seguridad en Azure Defender</span><span class="sxs-lookup"><span data-stu-id="d1e00-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="d1e00-148">Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="d1e00-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
