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
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142980"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="27148-104">Soluciones de informes personalizadas o de terceros para Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="27148-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="27148-105">Con [Microsoft Defender para Office 365,](office-365-atp.md)obtiene información detallada sobre las [investigaciones automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="27148-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="27148-106">Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros.</span><span class="sxs-lookup"><span data-stu-id="27148-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="27148-107">Si su organización desea integrar información sobre investigaciones [automatizadas](office-365-air.md) con dicha solución, puede usar la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="27148-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="27148-108">Recursos para configurar la integración</span><span class="sxs-lookup"><span data-stu-id="27148-108">Resources to configure integration</span></span>

|<span data-ttu-id="27148-109">Recurso</span><span class="sxs-lookup"><span data-stu-id="27148-109">Resource</span></span>|<span data-ttu-id="27148-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="27148-110">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="27148-111">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="27148-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="27148-112">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27148-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="27148-113">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="27148-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="27148-114">La API de administración de Office 365 usa Azure AD para proporcionar servicios de autenticación para que la aplicación acceda a los datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27148-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="27148-115">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="27148-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="27148-116">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="27148-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="27148-117">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="27148-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="27148-118">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="27148-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="27148-119">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="27148-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="27148-120">Obtenga información general [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) sobre el esquema común y Defender para [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) y la investigación de amenazas y el esquema de respuesta para obtener información sobre tipos específicos de datos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="27148-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="27148-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="27148-121">See also</span></span>

- [<span data-ttu-id="27148-122">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="27148-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="27148-123">Investigación y respuesta automatizadas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27148-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
