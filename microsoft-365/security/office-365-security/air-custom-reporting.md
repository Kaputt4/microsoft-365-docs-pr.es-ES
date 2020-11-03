---
title: Uso de soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigación automatizada, integración, informe personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre cómo integrar la investigación y la respuesta automatizadas con una solución de informes personalizada o de terceros.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 8b08b441ca468b5efa1c4c003c636de2a43b3e7d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844553"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="3de32-104">Usar la API de actividad de administración para soluciones de informes personalizadas o de terceros</span><span class="sxs-lookup"><span data-stu-id="3de32-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3de32-105">Con [Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), obtendrá [información detallada acerca de las investigaciones automatizadas](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="3de32-105">With [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="3de32-106">Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros.</span><span class="sxs-lookup"><span data-stu-id="3de32-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="3de32-107">Si su organización desea integrar la información sobre las investigaciones automatizadas con una solución de este tipo, puede usar la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3de32-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="3de32-108">Use los siguientes recursos para configurar esto:</span><span class="sxs-lookup"><span data-stu-id="3de32-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="3de32-109">Recurso</span><span class="sxs-lookup"><span data-stu-id="3de32-109">Resource</span></span>|<span data-ttu-id="3de32-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3de32-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="3de32-111">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="3de32-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="3de32-112">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3de32-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="3de32-113">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="3de32-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="3de32-114">La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3de32-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="3de32-115">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="3de32-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="3de32-116">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="3de32-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="3de32-117">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3de32-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="3de32-118">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="3de32-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="3de32-119">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="3de32-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="3de32-120">Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de la investigación y respuesta de Defender para Office 365 y Threat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos específicos de datos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3de32-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="3de32-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3de32-121">See also</span></span>

- [<span data-ttu-id="3de32-122">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3de32-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="3de32-123">Investigación y respuesta automatizadas en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="3de32-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
