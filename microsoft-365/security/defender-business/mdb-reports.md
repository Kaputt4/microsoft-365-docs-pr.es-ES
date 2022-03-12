---
title: Informes en Microsoft Defender para empresas
description: Obtenga información general sobre los informes que están disponibles en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/10/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 55b49393e2b9115e4617b617d14ba495a95d983c
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449952"
---
# <a name="reports-in-microsoft-defender-for-business"></a>Informes en Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando [para Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Hay varios informes disponibles en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En este artículo se describen estos informes, cómo puede usarlos y cómo encontrarlos.

<br/><br/>

## <a name="reports-in-defender-for-business"></a>Informes en Defender para empresas

|Informe  |Descripción  |
|---------|---------|
| **Informe de seguridad**  | El informe de seguridad proporciona información sobre las identidades, dispositivos y aplicaciones de la organización. Para obtener acceso a este informe, en el panel de navegación, elija **InformesGeneralSecurity** >  >  **report**. <br/><br/>**SUGERENCIA** Puede ver información similar en la página principal del portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). |
| **Protección contra amenazas**  | El informe de protección contra amenazas proporciona información sobre alertas y tendencias de alertas. Use la **columna Tendencias de** alertas para ver información sobre las alertas que se desencadenaron en los últimos 30 días. Use la **columna Estado de alerta** para ver la información de instantáneas actual sobre las alertas, como las categorías de alertas sin resolver y su clasificación. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsThreat** >  >  **protection**. <br/><br/>**SUGERENCIA**: También puede usar la lista **Incidentes** para ver información sobre alertas. En el panel de navegación, elija **Incidentes para** ver y administrar incidentes actuales. Para obtener más información, consulta [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md). |
| **Cumplimiento y mantenimiento del dispositivo** | El informe de cumplimiento y estado del dispositivo proporciona información sobre el estado y las tendencias del dispositivo. Puedes usar este informe para determinar si los sensores de Defender para empresas funcionan correctamente en dispositivos y el estado actual de Antivirus de Microsoft Defender. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsDevice** >  >  **health and compliance**. <br/><br/>**SUGERENCIA**: Puede usar **la lista Inventario** de dispositivos para ver información sobre los dispositivos de su organización. En el panel de navegación, elija **Inventario de dispositivos**. Para obtener más información, consulta [Administrar dispositivos en Microsoft Defender para empresas](mdb-manage-devices.md). |
| **Dispositivos vulnerables** | El informe de dispositivos vulnerables proporciona información sobre dispositivos y tendencias. Usa la **columna Tendencias** para ver información sobre dispositivos que han tenido alertas en los últimos 30 días. Use la **columna Estado** para ver la información de instantáneas actual sobre los dispositivos que tienen alertas. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsVulnerable** >  >  **devices**.<br/><br/>**SUGERENCIA**: Puede usar **la lista Inventario** de dispositivos para ver información sobre los dispositivos de su organización. En el panel de navegación, elija **Inventario de dispositivos**. Para obtener más información, consulta [Administrar dispositivos en Microsoft Defender para empresas](mdb-manage-devices.md). |
| **Protección web** | El informe de protección web muestra los intentos de acceder a sitios de phishing, vectores de malware, sitios de vulnerabilidad, sitios que no son de confianza o de baja reputación y sitios que se bloquean explícitamente. Las categorías de sitios bloqueados incluyen contenido para adultos, sitios de ocio, sitios de responsabilidad legal y mucho más. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsWeb** >  >  **protection**.<br/><br/>**SUGERENCIA**: Si aún no ha configurado la protección web para su organización, elija el **Configuración** en una vista de informe. A continuación, **en Reglas**, elija **Filtrado de contenido web**. Para obtener más información sobre el filtrado de contenido web, consulte [Filtrado de contenido web](../defender-endpoint/web-content-filtering.md). |

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="see-also"></a>Vea también

- [Introducción al uso de Microsoft Defender para empresas](mdb-get-started.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Administrar dispositivos en Microsoft Defender para empresas](mdb-manage-devices.md)