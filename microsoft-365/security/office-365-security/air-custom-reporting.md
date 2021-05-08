---
title: Soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: SIEM, API, AIR, autoIR, Microsoft Defender para endpoint, investigación automatizada, integración, informe personalizado
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre cómo integrar la investigación y la respuesta automatizadas con una solución de informes personalizada o de terceros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275017"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="1c27b-104">Soluciones de informes personalizadas o de terceros para Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c27b-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="1c27b-105">Con [Microsoft Defender para Office 365,](defender-for-office-365.md)obtiene información detallada acerca de las [investigaciones automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="1c27b-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="1c27b-106">Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros.</span><span class="sxs-lookup"><span data-stu-id="1c27b-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="1c27b-107">Si su organización desea integrar información sobre [investigaciones automatizadas](office-365-air.md) con dicha solución, puede usar la API de actividad Office 365 administración.</span><span class="sxs-lookup"><span data-stu-id="1c27b-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="1c27b-108">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="1c27b-108">**Applies to**</span></span>
- [<span data-ttu-id="1c27b-109">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c27b-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1c27b-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c27b-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1c27b-111">Con [Microsoft Defender para Office 365,](defender-for-office-365.md)obtiene información detallada acerca de las [investigaciones automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="1c27b-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="1c27b-112">Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros.</span><span class="sxs-lookup"><span data-stu-id="1c27b-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="1c27b-113">Si su organización desea integrar información acerca de las investigaciones automatizadas con dicha solución, puede usar la API de Office 365 actividad de administración.</span><span class="sxs-lookup"><span data-stu-id="1c27b-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="1c27b-114">Recurso</span><span class="sxs-lookup"><span data-stu-id="1c27b-114">Resource</span></span>|<span data-ttu-id="1c27b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c27b-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="1c27b-116">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="1c27b-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="1c27b-117">La API Office 365 actividad de administración proporciona información sobre diversos eventos y acciones de usuario, administrador, sistema y directiva de Microsoft 365 y Azure Active Directory de actividad.</span><span class="sxs-lookup"><span data-stu-id="1c27b-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="1c27b-118">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="1c27b-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="1c27b-119">La API Office 365 management usa Azure AD para proporcionar servicios de autenticación para que la aplicación obtenga acceso a Microsoft 365 datos.</span><span class="sxs-lookup"><span data-stu-id="1c27b-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="1c27b-120">Siga los pasos de este artículo para configurar esto.</span><span class="sxs-lookup"><span data-stu-id="1c27b-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="1c27b-121">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="1c27b-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="1c27b-122">Puede usar la API de Office 365 actividad de administración para recuperar información sobre acciones y eventos de usuario, administrador, sistema y directiva de Microsoft 365 y registros de actividad de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c27b-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="1c27b-123">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="1c27b-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="1c27b-124">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="1c27b-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="1c27b-125">Obtenga información general sobre el [esquema común](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el esquema de investigación y respuesta de defender para [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) y amenazas para obtener información sobre tipos específicos de datos disponibles a través de la API de actividad de administración Office 365 administración.</span><span class="sxs-lookup"><span data-stu-id="1c27b-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="1c27b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c27b-126">See also</span></span>

- [<span data-ttu-id="1c27b-127">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c27b-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1c27b-128">Investigación y respuesta automatizadas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c27b-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
