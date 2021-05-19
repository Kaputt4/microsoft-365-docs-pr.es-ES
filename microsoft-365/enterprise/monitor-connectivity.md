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
# <a name="monitor-microsoft-365-connectivity"></a>Supervisar la conectividad de Microsoft 365

Una vez que haya implementado Microsoft 365, puede mantener la conectividad Microsoft 365 mediante algunas de las herramientas y técnicas siguientes. You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166). También querrás tomar la [](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) aplicación de administración Microsoft 365 y marcar nuestra [Microsoft 365 para empresas: Ayuda para administradores.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Supervisión Microsoft 365 conectividad

|||
|:-----|:-----|
|**Recibir notificaciones de nuevos Microsoft 365 de conexión** <br/> |Si está administrando puntos de conexión Microsoft 365, querrá recibir notificaciones cuando publiquemos nuevos puntos de conexión, puede suscribirse [a](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)nuestra fuente RSS con su lector RSS favorito. Aquí le explicamos cómo [suscribirse Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) o puede enviar por correo electrónico las actualizaciones de fuentes [RSS.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Use System Center para supervisar Microsoft 365** <br/> |Si usa Microsoft System Center, puede descargar el módulo de administración de [System Center](https://www.microsoft.com/download/details.aspx?id=43708) para Office 365 para empezar a supervisar Microsoft 365 hoy. Para obtener instrucciones más detalladas, consulte la guía de operaciones del módulo de administración. <br/> |
|**Supervisar el estado de Azure ExpressRoute** <br/> |Si se está conectando a Microsoft 365 con Azure ExpressRoute para Microsoft 365, querrá asegurarse de que está usando tanto el Panel de mantenimiento del servicio de Microsoft 365 como el tiempo de solución de problemas de Azure [Reducing](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) con el estado de Azure Resource <br/> |
|**Usar Azure AD Connect Health con AD FS** <br/> |Si usa AD FS para single Sign-On con Microsoft 365, querrá empezar a usar Azure AD Conectar Health para supervisar la infraestructura de [AD FS](/azure/active-directory/hybrid/how-to-connect-health-adfs).  <br/> |
|**Supervisar mediante programación Microsoft 365** <br/> |Consulte nuestra guía sobre la API [Microsoft 365 administración](/office/office-365-management-api/office-365-management-apis-overview).  <br/> |

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Microsoft 365 Enterprise servicios y aplicaciones](configure-services-and-applications.md)
  
[Prepare su organización para Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Planeamiento de red y ajuste del rendimiento para Microsoft 365](network-planning-and-performance.md)
  
[Microsoft 365 integración con entornos locales](microsoft-365-integration.md)
  
[Administración de Microsoft 365 de conexión](managing-office-365-endpoints.md)
