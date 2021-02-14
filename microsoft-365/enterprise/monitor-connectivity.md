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
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693642"
---
# <a name="monitor-microsoft-365-connectivity"></a>Supervisar la conectividad de Microsoft 365

Una vez que haya implementado Microsoft 365, puede mantener la conectividad de Microsoft 365 con algunas de las herramientas y técnicas siguientes. You'll want to understand the official [Service Health and Continuity](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166). You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our Microsoft [365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).
  
## <a name="monitoring-microsoft-365-connectivity"></a>Supervisión de la conectividad de Microsoft 365

|||
|:-----|:-----|
|**Recibir notificaciones de nuevos puntos de conexión de Microsoft 365** <br/> |Si está administrando puntos de conexión de [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)querrá recibir notificaciones cuando publiquemos nuevos puntos de conexión, puede suscribirse a nuestra fuente RSS con su lector RSS favorito. Aquí te explicamos cómo [suscribirte a través de Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) o puedes recibir las actualizaciones de fuentes RSS por correo [electrónico.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Usar System Center para supervisar Microsoft 365** <br/> |Si usa Microsoft System Center, puede descargar el módulo de administración de System Center para [Office 365](https://www.microsoft.com/download/details.aspx?id=43708) para empezar a supervisar Microsoft 365 hoy. Para obtener instrucciones más detalladas, consulte la guía de operaciones del módulo de administración o esta entrada de blog de supervisión de [Office365 con System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Supervisar el estado de Azure ExpressRoute** <br/> |Si se conecta a Microsoft 365 con Azure ExpressRoute para Microsoft 365, querrá asegurarse de que usa tanto el Panel de estado del servicio de Microsoft 365 como el tiempo de solución de problemas de Azure [Reducing](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) con el estado de azure Resource <br/> |
|**Usar Azure AD Connect Health con AD FS** <br/> |Si usa AD FS para el Sign-On único con Microsoft 365, querrá empezar a usar Azure AD Connect Health para supervisar la infraestructura [de AD FS.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/)  <br/> |
|**Supervisar Microsoft 365 mediante programación** <br/> |Consulte nuestras instrucciones sobre la API de administración de [Microsoft 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar aplicaciones y servicios de Microsoft 365 Enterprise](configure-services-and-applications.md)
  
[Preparar su organización para Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Planeamiento de red y ajuste del rendimiento para Microsoft 365](network-planning-and-performance.md)
  
[Integración de Microsoft 365 con entornos locales](microsoft-365-integration.md)
  
[Administración de puntos de conexión de Microsoft 365](managing-office-365-endpoints.md)
