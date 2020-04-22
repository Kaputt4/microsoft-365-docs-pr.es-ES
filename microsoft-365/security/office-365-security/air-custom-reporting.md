---
title: Uso de soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
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
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo integrar la investigación y la respuesta automatizadas con una solución de informes personalizada o de terceros.
ms.openlocfilehash: 4bd53de9a880fc774814588ed84dce2284535922
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634723"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="a61c9-104">Usar la API de actividad de administración para soluciones de informes personalizadas o de terceros</span><span class="sxs-lookup"><span data-stu-id="a61c9-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="a61c9-105">Con [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), puede obtener [información detallada acerca de las investigaciones automatizadas](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="a61c9-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="a61c9-106">Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros.</span><span class="sxs-lookup"><span data-stu-id="a61c9-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="a61c9-107">Si su organización desea integrar la información sobre las investigaciones automatizadas con una solución de este tipo, puede usar la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a61c9-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="a61c9-108">Use los siguientes recursos para configurar esto:</span><span class="sxs-lookup"><span data-stu-id="a61c9-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="a61c9-109">Resource</span><span class="sxs-lookup"><span data-stu-id="a61c9-109">Resource</span></span>  |<span data-ttu-id="a61c9-110">Description</span><span class="sxs-lookup"><span data-stu-id="a61c9-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="a61c9-111">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a61c9-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="a61c9-112">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a61c9-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="a61c9-113">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a61c9-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="a61c9-114">La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a61c9-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="a61c9-115">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="a61c9-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="a61c9-116">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a61c9-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="a61c9-117">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a61c9-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="a61c9-118">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="a61c9-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="a61c9-119">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a61c9-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="a61c9-120">Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a61c9-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="a61c9-121">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a61c9-121">Related articles</span></span>

- [<span data-ttu-id="a61c9-122">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="a61c9-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="a61c9-123">Obtenga información sobre la investigación y la respuesta automatizadas en la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a61c9-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)