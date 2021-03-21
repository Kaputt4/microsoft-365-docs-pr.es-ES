---
title: Integración de SIEM con Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre el servidor SIEM de su organización con Microsoft Defender para Office 365 y eventos de amenazas relacionados en la API de administración de actividades de Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86a716499a25af2a2907d9c502d31474b27ef7bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916603"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="93095-103">Integración de SIEM con Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="93095-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="93095-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="93095-104">**Applies to**</span></span>
- [<span data-ttu-id="93095-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="93095-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="93095-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="93095-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="93095-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93095-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="93095-108">Si su organización usa un servidor de administración de eventos y información de seguridad (SIEM), puede integrar Microsoft Defender para Office 365 con el servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="93095-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="93095-109">Puede configurar esta integración mediante la API de administración de actividades [de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="93095-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="93095-110">La integración de SIEM permite ver información, como malware o phish detectado por Microsoft Defender para Office 365, en los informes del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="93095-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="93095-111">Para ver un ejemplo de integración de SIEM con Microsoft Defender para Office 365, vea [tech community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="93095-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="93095-112">Para obtener más información sobre las API de administración de Office 365, vea [Office 365 Management API overview](/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="93095-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="93095-113">Cómo funciona la integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="93095-113">How SIEM integration works</span></span>

<span data-ttu-id="93095-114">La API de administración de actividades de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de su organización.</span><span class="sxs-lookup"><span data-stu-id="93095-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="93095-115">Si su organización tiene Microsoft Defender para Office 365 Plan 1 o 2 u Office 365 E5, puede usar el esquema de [Microsoft Defender para Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="93095-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="93095-116">Recientemente, los eventos de las capacidades automatizadas de investigación y respuesta en [Microsoft Defender para Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) se agregaron a la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="93095-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="93095-117">Además de incluir datos sobre los detalles principales de la investigación, como el identificador, el nombre y el estado, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.</span><span class="sxs-lookup"><span data-stu-id="93095-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="93095-118">El servidor SIEM u otro sistema similar sondea la carga de **trabajo audit.general** para obtener acceso a eventos de detección.</span><span class="sxs-lookup"><span data-stu-id="93095-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="93095-119">Para obtener más información, vea Introducción a las API de administración [de Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="93095-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="93095-120">Enum: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="93095-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="93095-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="93095-121">AuditLogRecordType</span></span>

<span data-ttu-id="93095-122">En la tabla siguiente se resumen los valores **de AuditLogRecordType** relevantes para eventos de Microsoft Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="93095-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="93095-123">Valor</span><span class="sxs-lookup"><span data-stu-id="93095-123">Value</span></span>|<span data-ttu-id="93095-124">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="93095-124">Member name</span></span>|<span data-ttu-id="93095-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="93095-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="93095-126">28</span><span class="sxs-lookup"><span data-stu-id="93095-126">28</span></span>|<span data-ttu-id="93095-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="93095-127">ThreatIntelligence</span></span>|<span data-ttu-id="93095-128">Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="93095-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="93095-129">41</span><span class="sxs-lookup"><span data-stu-id="93095-129">41</span></span>|<span data-ttu-id="93095-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="93095-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="93095-131">Eventos de invalidación de bloqueo y tiempo de bloqueo de vínculos seguros de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="93095-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="93095-132">47</span><span class="sxs-lookup"><span data-stu-id="93095-132">47</span></span>|<span data-ttu-id="93095-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="93095-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="93095-134">Eventos de suplantación de identidad y malware para archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams, de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="93095-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="93095-135">64</span><span class="sxs-lookup"><span data-stu-id="93095-135">64</span></span>|<span data-ttu-id="93095-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="93095-136">AirInvestigation</span></span>|<span data-ttu-id="93095-137">Eventos automatizados de investigación y respuesta, como detalles de investigación y artefactos relevantes, de Microsoft Defender para Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="93095-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="93095-138">Debe ser un administrador global o tener asignado el rol de administrador de seguridad para el Centro de seguridad & cumplimiento para configurar la integración de SIEM con Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="93095-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="93095-139">El registro de auditoría debe estar activado para el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93095-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="93095-140">Para obtener ayuda con esto, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="93095-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93095-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="93095-141">See also</span></span>

[<span data-ttu-id="93095-142">Investigación y respuesta de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="93095-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="93095-143">Investigación y respuesta automatizadas (AIR) en Office 365</span><span class="sxs-lookup"><span data-stu-id="93095-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)