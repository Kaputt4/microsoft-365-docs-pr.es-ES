---
title: Soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigación automatizada, integración, informe personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Obtenga información sobre cómo integrar la investigación automatizada y la respuesta con una solución de informes personalizada o de terceros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a66a89a13182570259bcb8be4134c21d13e22391
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175816"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="7652c-104">Soluciones de informes personalizadas o de terceros para Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7652c-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="7652c-105">Con [Microsoft Defender para Office 365,](office-365-atp.md)obtiene información detallada sobre las [investigaciones automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="7652c-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="7652c-106">Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros.</span><span class="sxs-lookup"><span data-stu-id="7652c-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="7652c-107">Si su organización desea integrar información sobre investigaciones [automatizadas](office-365-air.md) con dicha solución, puede usar la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7652c-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="7652c-108">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="7652c-108">**Applies to**</span></span>
- [<span data-ttu-id="7652c-109">Microsoft Defender para Office 365 plan 2</span><span class="sxs-lookup"><span data-stu-id="7652c-109">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="7652c-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7652c-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7652c-111">Con [Microsoft Defender para Office 365,](office-365-atp.md)obtiene información detallada sobre las [investigaciones automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="7652c-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="7652c-112">Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros.</span><span class="sxs-lookup"><span data-stu-id="7652c-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="7652c-113">Si su organización desea integrar información sobre investigaciones automatizadas con dicha solución, puede usar la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7652c-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="7652c-114">Recurso</span><span class="sxs-lookup"><span data-stu-id="7652c-114">Resource</span></span>|<span data-ttu-id="7652c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7652c-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="7652c-116">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="7652c-116">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="7652c-117">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7652c-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="7652c-118">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="7652c-118">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="7652c-119">La API de administración de Office 365 usa Azure AD para proporcionar servicios de autenticación para que la aplicación acceda a los datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7652c-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="7652c-120">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="7652c-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="7652c-121">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="7652c-121">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="7652c-122">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7652c-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="7652c-123">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="7652c-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="7652c-124">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="7652c-124">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="7652c-125">Obtenga información general [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) sobre el esquema común y Defender para [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) y el esquema de investigación y respuesta de amenazas para obtener información sobre tipos específicos de datos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7652c-125">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="7652c-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7652c-126">See also</span></span>

- [<span data-ttu-id="7652c-127">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7652c-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="7652c-128">Investigación y respuesta automatizadas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7652c-128">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
