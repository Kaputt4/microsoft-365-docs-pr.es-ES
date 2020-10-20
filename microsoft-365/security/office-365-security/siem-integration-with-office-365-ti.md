---
title: Integración de SIEM con la protección contra amenazas avanzada
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
description: Integre el servidor de SIEM de su organización con la protección contra amenazas avanzada de Office 365 y eventos de amenazas relacionados en la API de administración de actividad de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4c92fc45546d3d8022a3925baa9c10f9bd0090b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600558"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="6b8fe-103">Integración de SIEM con la protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="6b8fe-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6b8fe-104">Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), puede integrar Office 365 Advanced Threat Protection (Office 365 ATP) con su servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-104">If your organization is using a security information and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="6b8fe-105">Puede configurar esta integración mediante la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="6b8fe-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="6b8fe-106">La integración de SIEM permite ver información, como malware o phish detectada por Office 365 ATP, en los informes del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="6b8fe-107">Para ver un ejemplo de la integración de SIEM con Office 365 ATP, vea [blog de la comunidad tecnológica: mejorar la efectividad de su SOC con office 365 ATP y la API de administración de O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="6b8fe-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="6b8fe-108">Para obtener más información acerca de las API de administración de Office 365, vea [información general sobre las API de administración de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="6b8fe-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="6b8fe-109">Cómo funciona la integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="6b8fe-109">How SIEM integration works</span></span>

<span data-ttu-id="6b8fe-110">La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de su organización.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="6b8fe-111">Si su organización tiene Office 365 ATP plan 1 o 2, o Office 365 E5, puede usar el [esquema ATP de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="6b8fe-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="6b8fe-112">Recientemente, los eventos de las capacidades automatizadas de investigación y respuesta en [office 365 ATP plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) se agregaron a la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="6b8fe-113">Además de incluir datos sobre los detalles de la investigación principal, como ID, Name y status, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="6b8fe-114">El servidor de SIEM o un sistema similar sondea la **auditoría.** carga de trabajo general para obtener acceso a los eventos de detección.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="6b8fe-115">Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="6b8fe-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="6b8fe-116">Enum: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="6b8fe-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="6b8fe-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="6b8fe-117">AuditLogRecordType</span></span>

<span data-ttu-id="6b8fe-118">En la siguiente tabla se resumen los valores de **AuditLogRecordType** relevantes para los eventos de ATP de Office 365:</span><span class="sxs-lookup"><span data-stu-id="6b8fe-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="6b8fe-119">Valor</span><span class="sxs-lookup"><span data-stu-id="6b8fe-119">Value</span></span>|<span data-ttu-id="6b8fe-120">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="6b8fe-120">Member name</span></span>|<span data-ttu-id="6b8fe-121">Description</span><span class="sxs-lookup"><span data-stu-id="6b8fe-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="6b8fe-122">28</span><span class="sxs-lookup"><span data-stu-id="6b8fe-122">28</span></span>|<span data-ttu-id="6b8fe-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="6b8fe-123">ThreatIntelligence</span></span>|<span data-ttu-id="6b8fe-124">Eventos de suplantación de identidad y malware de Exchange Online Protection y Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="6b8fe-125">41</span><span class="sxs-lookup"><span data-stu-id="6b8fe-125">41</span></span>|<span data-ttu-id="6b8fe-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="6b8fe-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="6b8fe-127">Vínculos seguros eventos de invalidación de tiempo de bloqueo y bloqueo de la ATP de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="6b8fe-128">47</span><span class="sxs-lookup"><span data-stu-id="6b8fe-128">47</span></span>|<span data-ttu-id="6b8fe-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="6b8fe-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="6b8fe-130">Eventos de suplantación de identidad y malware para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams desde Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="6b8fe-131">64</span><span class="sxs-lookup"><span data-stu-id="6b8fe-131">64</span></span>|<span data-ttu-id="6b8fe-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="6b8fe-132">AirInvestigation</span></span>|<span data-ttu-id="6b8fe-133">Investigación automatizada y eventos de respuesta, como detalles de investigación y artefactos relevantes, de Office 365 ATP plan 2.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="6b8fe-134">Debe ser administrador global o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con la protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="6b8fe-135">El registro de auditoría debe estar activado para su entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b8fe-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="6b8fe-136">Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="6b8fe-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b8fe-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b8fe-137">See also</span></span>

[<span data-ttu-id="6b8fe-138">Investigación y respuesta de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="6b8fe-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="6b8fe-139">Investigación y respuesta automatizadas (AIR) en Office 365</span><span class="sxs-lookup"><span data-stu-id="6b8fe-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

