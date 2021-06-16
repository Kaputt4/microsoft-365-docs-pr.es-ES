---
title: Integración de SIEM con Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre el servidor SIEM de su organización con Microsoft Defender para Office 365 eventos de amenazas relacionados en la API de administración Office 365 actividad.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3d6bbacb4a64060ecd03cbb28eee3256f41827e
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929784"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="85b86-103">Integración de SIEM con Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="85b86-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="85b86-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="85b86-104">**Applies to**</span></span>
- [<span data-ttu-id="85b86-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="85b86-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="85b86-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="85b86-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="85b86-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85b86-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="85b86-108">Si su organización usa un servidor de administración de eventos y de información de seguridad (SIEM), puede integrar Microsoft Defender para Office 365 con el servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="85b86-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="85b86-109">Puede configurar esta integración mediante la API de administración Office 365 [actividad](/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="85b86-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="85b86-110">La integración de SIEM permite ver información, como malware o phish detectado por Microsoft Defender para Office 365, en los informes del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="85b86-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="85b86-111">Para ver un ejemplo de integración de SIEM con Microsoft Defender para Office 365, consulte Tech [Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="85b86-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="85b86-112">Para obtener más información sobre las API de Office 365 administración, vea Office 365 introducción a las [API de administración.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="85b86-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="85b86-113">Cómo funciona la integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="85b86-113">How SIEM integration works</span></span>

<span data-ttu-id="85b86-114">La API Office 365 administración de actividades recupera información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad Microsoft 365 y Azure Active Directory de la organización.</span><span class="sxs-lookup"><span data-stu-id="85b86-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="85b86-115">Si su organización tiene Microsoft Defender para Office 365 plan 1 o 2 o Office 365 E5, puede usar [Microsoft Defender](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)para Office 365 esquema .</span><span class="sxs-lookup"><span data-stu-id="85b86-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="85b86-116">Recientemente, los eventos de las capacidades automatizadas de investigación y respuesta en [Microsoft Defender para Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) se agregaron a la API Office 365 actividad de administración.</span><span class="sxs-lookup"><span data-stu-id="85b86-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="85b86-117">Además de incluir datos sobre los detalles principales de la investigación, como el identificador, el nombre y el estado, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.</span><span class="sxs-lookup"><span data-stu-id="85b86-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="85b86-118">El servidor SIEM u otro sistema similar sondea la carga de **trabajo audit.general** para obtener acceso a eventos de detección.</span><span class="sxs-lookup"><span data-stu-id="85b86-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="85b86-119">Para obtener más información, vea [Introducción a Office 365 API de administración](/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="85b86-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="85b86-120">Enum: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="85b86-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="85b86-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="85b86-121">AuditLogRecordType</span></span>

<span data-ttu-id="85b86-122">En la tabla siguiente se resumen los valores **de AuditLogRecordType** que son relevantes para Microsoft Defender para Office 365 eventos:</span><span class="sxs-lookup"><span data-stu-id="85b86-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="85b86-123">Valor</span><span class="sxs-lookup"><span data-stu-id="85b86-123">Value</span></span>|<span data-ttu-id="85b86-124">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="85b86-124">Member name</span></span>|<span data-ttu-id="85b86-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="85b86-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="85b86-126">28</span><span class="sxs-lookup"><span data-stu-id="85b86-126">28</span></span>|<span data-ttu-id="85b86-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="85b86-127">ThreatIntelligence</span></span>|<span data-ttu-id="85b86-128">Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="85b86-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="85b86-129">41</span><span class="sxs-lookup"><span data-stu-id="85b86-129">41</span></span>|<span data-ttu-id="85b86-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="85b86-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="85b86-131">Caja fuerte Vincula el tiempo de bloqueo y bloquea eventos de invalidación de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="85b86-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="85b86-132">47</span><span class="sxs-lookup"><span data-stu-id="85b86-132">47</span></span>|<span data-ttu-id="85b86-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="85b86-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="85b86-134">Eventos de suplantación de identidad y malware para archivos de SharePoint Online, OneDrive para la Empresa y Microsoft Teams, desde Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="85b86-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="85b86-135">64</span><span class="sxs-lookup"><span data-stu-id="85b86-135">64</span></span>|<span data-ttu-id="85b86-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="85b86-136">AirInvestigation</span></span>|<span data-ttu-id="85b86-137">Eventos automatizados de investigación y respuesta, como detalles de investigación y artefactos relevantes, de Microsoft Defender para Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="85b86-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="85b86-138">Debe ser un administrador global o tener asignado el rol de administrador de seguridad para que el portal de Microsoft 365 Defender configure la integración de SIEM con Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="85b86-138">You must be a global administrator or have the security administrator role assigned for the Microsoft 365 Defender portal to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="85b86-139">El registro de auditoría debe estar activado para el Microsoft 365 de auditoría.</span><span class="sxs-lookup"><span data-stu-id="85b86-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="85b86-140">Para obtener ayuda con esto, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="85b86-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="85b86-141">Ver también</span><span class="sxs-lookup"><span data-stu-id="85b86-141">See also</span></span>

[<span data-ttu-id="85b86-142">Investigación y respuesta de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="85b86-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="85b86-143">Investigación y respuesta automatizadas (AIR) en Office 365</span><span class="sxs-lookup"><span data-stu-id="85b86-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)