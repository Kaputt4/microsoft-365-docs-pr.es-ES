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
description: En este artículo, aprenderá sobre las herramientas y técnicas que puede usar para supervisar y mantener la conectividad de Microsoft 365.
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920781"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="545d2-103">Supervisar la conectividad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="545d2-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="545d2-104">Una vez que haya implementado Microsoft 365, puede mantener la conectividad de Microsoft 365 con algunas de las herramientas y técnicas siguientes.</span><span class="sxs-lookup"><span data-stu-id="545d2-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="545d2-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span><span class="sxs-lookup"><span data-stu-id="545d2-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="545d2-106">También querrás tomar la aplicación de administración de [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) y marcar nuestra [Microsoft 365 para empresas: Ayuda para administradores.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="545d2-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="545d2-107">Supervisión de la conectividad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="545d2-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="545d2-108">**Recibir notificaciones de nuevos puntos de conexión de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="545d2-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="545d2-109">Si está administrando puntos de conexión de [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)querrá recibir notificaciones cuando publiquemos nuevos puntos de conexión, puede suscribirse a nuestra fuente RSS con su lector RSS favorito.</span><span class="sxs-lookup"><span data-stu-id="545d2-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="545d2-110">Aquí se muestra cómo [suscribirse a través](https://go.microsoft.com/fwlink/p/?LinkId=532416) de Outlook o puede recibir las actualizaciones de fuentes [RSS por correo electrónico.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="545d2-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="545d2-111">**Usar System Center para supervisar Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="545d2-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="545d2-112">Si usa Microsoft System Center, puede descargar [System Center Management Pack para Office 365](https://www.microsoft.com/download/details.aspx?id=43708) para empezar a supervisar Microsoft 365 hoy.</span><span class="sxs-lookup"><span data-stu-id="545d2-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="545d2-113">Para obtener instrucciones más detalladas, consulte la guía de operaciones del módulo de administración o este blog post [Office365 Monitoring using System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="545d2-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="545d2-114">**Supervisar el estado de Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="545d2-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="545d2-115">Si se conecta a Microsoft 365 con Azure ExpressRoute para Microsoft 365, querrá asegurarse de que está usando tanto el Panel de mantenimiento del servicio de Microsoft 365 como el tiempo de solución de problemas de Azure [Reducing](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) con el estado de Azure Resource</span><span class="sxs-lookup"><span data-stu-id="545d2-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="545d2-116">**Usar Azure AD Connect Health con AD FS**</span><span class="sxs-lookup"><span data-stu-id="545d2-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="545d2-117">Si usa AD FS para single Sign-On con Microsoft 365, querrá empezar a usar Azure AD Connect Health para supervisar la infraestructura de [AD FS](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span><span class="sxs-lookup"><span data-stu-id="545d2-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="545d2-118">**Supervisar mediante programación Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="545d2-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="545d2-119">Consulte nuestras instrucciones sobre la API de administración de [Microsoft 365](/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="545d2-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="545d2-120">Este es un vínculo breve que se puede usar para volver: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="545d2-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="545d2-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="545d2-121">Related topics</span></span>

[<span data-ttu-id="545d2-122">Configurar aplicaciones y servicios de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="545d2-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="545d2-123">Preparar su organización para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="545d2-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="545d2-124">Planeamiento de red y ajuste del rendimiento para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="545d2-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="545d2-125">Integración de Microsoft 365 con entornos locales</span><span class="sxs-lookup"><span data-stu-id="545d2-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="545d2-126">Administración de puntos de conexión de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="545d2-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)