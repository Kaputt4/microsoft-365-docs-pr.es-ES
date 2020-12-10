---
title: Integración de SIEM con Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre el servidor SIEM de su organización con Microsoft defender para Office 365 y eventos relacionados con amenazas en la API de administración de actividad de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 93ff1606130c60ceb46087d28bb26f9a6d27d330
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615665"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="13ce2-103">Integración de SIEM con Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="13ce2-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="13ce2-104">Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), puede integrar Microsoft defender para Office 365 con su servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="13ce2-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="13ce2-105">Puede configurar esta integración mediante la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="13ce2-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="13ce2-106">La integración de SIEM permite ver información, como malware o phish detectada por Microsoft defender para Office 365, en los informes del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="13ce2-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="13ce2-107">Para ver un ejemplo de la integración de SIEM con Microsoft defender para Office 365, vea [blog de la comunidad tecnológica: mejorar la efectividad de su SOC con defender para office 365 y la API de administración de O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="13ce2-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="13ce2-108">Para obtener más información acerca de las API de administración de Office 365, vea [información general sobre las API de administración de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="13ce2-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="13ce2-109">Cómo funciona la integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="13ce2-109">How SIEM integration works</span></span>

<span data-ttu-id="13ce2-110">La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de su organización.</span><span class="sxs-lookup"><span data-stu-id="13ce2-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="13ce2-111">Si su organización tiene Microsoft defender para Office 365 plan 1 o 2, o Office 365 E5, puede usar el [esquema de Microsoft defender para office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="13ce2-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="13ce2-112">Recientemente, se agregaron eventos de investigación automatizada y capacidades de respuesta en [Microsoft defender para office 365 plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) a la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="13ce2-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="13ce2-113">Además de incluir datos sobre los detalles de la investigación principal, como ID, Name y status, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.</span><span class="sxs-lookup"><span data-stu-id="13ce2-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="13ce2-114">El servidor de SIEM o un sistema similar sondea la **auditoría.** carga de trabajo general para obtener acceso a los eventos de detección.</span><span class="sxs-lookup"><span data-stu-id="13ce2-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="13ce2-115">Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="13ce2-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="13ce2-116">Enum: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="13ce2-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="13ce2-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="13ce2-117">AuditLogRecordType</span></span>

<span data-ttu-id="13ce2-118">En la tabla siguiente se resumen los valores de **AuditLogRecordType** relevantes para los eventos 365 de Microsoft defender para Office:</span><span class="sxs-lookup"><span data-stu-id="13ce2-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="13ce2-119">Valor</span><span class="sxs-lookup"><span data-stu-id="13ce2-119">Value</span></span>|<span data-ttu-id="13ce2-120">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="13ce2-120">Member name</span></span>|<span data-ttu-id="13ce2-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="13ce2-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="13ce2-122">28</span><span class="sxs-lookup"><span data-stu-id="13ce2-122">28</span></span>|<span data-ttu-id="13ce2-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="13ce2-123">ThreatIntelligence</span></span>|<span data-ttu-id="13ce2-124">Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="13ce2-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="13ce2-125">41</span><span class="sxs-lookup"><span data-stu-id="13ce2-125">41</span></span>|<span data-ttu-id="13ce2-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="13ce2-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="13ce2-127">Vínculos seguros eventos de invalidación de tiempo de bloqueo y bloqueo de Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="13ce2-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="13ce2-128">47</span><span class="sxs-lookup"><span data-stu-id="13ce2-128">47</span></span>|<span data-ttu-id="13ce2-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="13ce2-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="13ce2-130">Eventos de suplantación de identidad y malware para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams, de Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="13ce2-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="13ce2-131">64</span><span class="sxs-lookup"><span data-stu-id="13ce2-131">64</span></span>|<span data-ttu-id="13ce2-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="13ce2-132">AirInvestigation</span></span>|<span data-ttu-id="13ce2-133">Eventos de investigación y respuesta automatizados, como detalles de investigación y artefactos relevantes, de Microsoft defender para Office 365 plan 2.</span><span class="sxs-lookup"><span data-stu-id="13ce2-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="13ce2-134">Debe ser administrador global o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="13ce2-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="13ce2-135">El registro de auditoría debe estar activado para su entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13ce2-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="13ce2-136">Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="13ce2-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="13ce2-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="13ce2-137">See also</span></span>

[<span data-ttu-id="13ce2-138">Investigación y respuesta de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="13ce2-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="13ce2-139">Investigación y respuesta automatizadas (AIR) en Office 365</span><span class="sxs-lookup"><span data-stu-id="13ce2-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

