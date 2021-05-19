---
title: Supervisar la conectividad de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: En este artículo, aprenderá sobre las herramientas y técnicas que puede usar para supervisar y mantener Microsoft 365 conectividad.
ms.openlocfilehash: dfba158085e6642856049d7894b4156f42353236
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538812"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="5d4d3-103">Supervisar la conectividad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5d4d3-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="5d4d3-104">Una vez que haya implementado Microsoft 365, puede mantener la conectividad Microsoft 365 mediante algunas de las herramientas y técnicas siguientes.</span><span class="sxs-lookup"><span data-stu-id="5d4d3-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="5d4d3-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span><span class="sxs-lookup"><span data-stu-id="5d4d3-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="5d4d3-106">También querrás tomar la [](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) aplicación de administración Microsoft 365 y marcar nuestra [Microsoft 365 para empresas: Ayuda para administradores.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="5d4d3-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="5d4d3-107">Supervisión Microsoft 365 conectividad</span><span class="sxs-lookup"><span data-stu-id="5d4d3-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5d4d3-108">**Recibir notificaciones de nuevos Microsoft 365 de conexión**</span><span class="sxs-lookup"><span data-stu-id="5d4d3-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="5d4d3-109">Si está administrando puntos de conexión Microsoft 365, querrá recibir notificaciones cuando publiquemos nuevos puntos de conexión, puede suscribirse [a](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)nuestra fuente RSS con su lector RSS favorito.</span><span class="sxs-lookup"><span data-stu-id="5d4d3-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="5d4d3-110">Aquí le explicamos cómo [suscribirse Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) o puede enviar por correo electrónico las actualizaciones de fuentes [RSS.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="5d4d3-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="5d4d3-111">**Use System Center para supervisar Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5d4d3-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="5d4d3-112">Si usa Microsoft System Center, puede descargar el módulo de administración de [System Center](https://www.microsoft.com/download/details.aspx?id=43708) para Office 365 para empezar a supervisar Microsoft 365 hoy.</span><span class="sxs-lookup"><span data-stu-id="5d4d3-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="5d4d3-113">Para obtener instrucciones más detalladas, consulte la guía de operaciones del módulo de administración.</span><span class="sxs-lookup"><span data-stu-id="5d4d3-113">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="5d4d3-114">**Supervisar el estado de Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="5d4d3-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="5d4d3-115">Si se está conectando a Microsoft 365 con Azure ExpressRoute para Microsoft 365, querrá asegurarse de que está usando tanto el Panel de mantenimiento del servicio de Microsoft 365 como el tiempo de solución de problemas de Azure [Reducing](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) con el estado de Azure Resource</span><span class="sxs-lookup"><span data-stu-id="5d4d3-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="5d4d3-116">**Usar Azure AD Connect Health con AD FS**</span><span class="sxs-lookup"><span data-stu-id="5d4d3-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="5d4d3-117">Si usa AD FS para single Sign-On con Microsoft 365, querrá empezar a usar Azure AD Conectar Health para supervisar la infraestructura de [AD FS](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span><span class="sxs-lookup"><span data-stu-id="5d4d3-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="5d4d3-118">**Supervisar mediante programación Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5d4d3-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="5d4d3-119">Consulte nuestra guía sobre la API [Microsoft 365 administración](/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="5d4d3-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="5d4d3-120">Este es un vínculo breve que se puede usar para volver: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="5d4d3-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5d4d3-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5d4d3-121">Related topics</span></span>

[<span data-ttu-id="5d4d3-122">Configurar Microsoft 365 Enterprise servicios y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5d4d3-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="5d4d3-123">Prepare su organización para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5d4d3-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="5d4d3-124">Planeamiento de red y ajuste del rendimiento para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5d4d3-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="5d4d3-125">Microsoft 365 integración con entornos locales</span><span class="sxs-lookup"><span data-stu-id="5d4d3-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="5d4d3-126">Administración de Microsoft 365 de conexión</span><span class="sxs-lookup"><span data-stu-id="5d4d3-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
