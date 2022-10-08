---
title: Supervisar la conectividad de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
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
description: En este artículo, obtendrá información sobre las herramientas y técnicas que puede usar para supervisar y mantener la conectividad de Microsoft 365.
ms.openlocfilehash: 8388e9d354a7ff87b8a585c2a22ecf7edf473bf8
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68186577"
---
# <a name="monitor-microsoft-365-connectivity"></a>Supervisar la conectividad de Microsoft 365

Una vez que haya implementado Microsoft 365, puede mantener la conectividad de Microsoft 365 mediante algunas de las herramientas y técnicas siguientes. Querrá comprender las directrices oficiales de mantenimiento [y continuidad del servicio,](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) así como nuestros [procedimientos recomendados para usar Microsoft 365 en una red lenta](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166). También querrás obtener la [aplicación de administración de Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) y marcar nuestra [Ayuda de Microsoft 365 para empresas Administración](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).
  
## <a name="monitoring-microsoft-365-connectivity"></a>Supervisión de la conectividad de Microsoft 365

|Tipo de supervisión |Descripción |
|:-----|:-----|
|**Recibir notificaciones de nuevos puntos de conexión de Microsoft 365** <br/> |Si está [administrando puntos de conexión de Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), querrá recibir notificaciones cuando publiquemos nuevos puntos de conexión, puede suscribirse a nuestra fuente RSS con su lector RSS favorito. A continuación se muestra cómo [suscribirse a través de Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) o puede [enviar por correo electrónico las actualizaciones de fuentes RSS](https://go.microsoft.com/fwlink/p/?LinkId=532417).  <br/> |
|**Uso de System Center para supervisar Microsoft 365** <br/> |Si usa Microsoft System Center, puede descargar el módulo de administración de [Microsoft System Center Operations Manager para Microsoft 365](https://www.microsoft.com/download/details.aspx?id=103379) para empezar a supervisar Microsoft 365 hoy mismo. Para obtener instrucciones más detalladas, consulte la guía de operaciones del módulo de administración. <br/> |
|**Supervisar el estado de Azure ExpressRoute** <br/> |Si se conecta a Microsoft 365 mediante Azure ExpressRoute para Microsoft 365, querrá asegurarse de que usa tanto el panel de mantenimiento del servicio de Microsoft 365 como el [tiempo de solución de problemas de Azure Reduce el tiempo de solución de problemas con Azure Resource Health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/). <br/> |
|**Usar Azure AD Connect Health con AD FS** <br/> |Si usa AD FS para una sola Sign-On con Microsoft 365, querrá empezar a [usar Azure AD Connect Health para supervisar la infraestructura de AD FS](/azure/active-directory/hybrid/how-to-connect-health-adfs).  <br/> |
|**Supervisión mediante programación de Microsoft 365** <br/> |Consulte nuestras instrucciones sobre la [API de administración de Microsoft 365](/office/office-365-management-api/office-365-management-apis-overview).  <br/> |

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Temas relacionados

[Configuración de aplicaciones y servicios de Microsoft 365 Enterprise](configure-services-and-applications.md)
  
[Preparar su organización para Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Planeamiento de red y ajuste del rendimiento para Microsoft 365](network-planning-and-performance.md)
  
[Integración de Microsoft 365 con entornos locales](microsoft-365-integration.md)
  
[Administración de puntos de conexión de Microsoft 365](managing-office-365-endpoints.md)
