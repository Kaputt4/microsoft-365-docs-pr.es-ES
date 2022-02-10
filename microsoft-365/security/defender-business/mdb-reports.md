---
title: Informes en Microsoft Defender para empresas (versión preliminar)
description: Obtener información general sobre los informes que están disponibles en Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 85e1958c9577b68737aa2803dc115c83f757654e
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520576"
---
# <a name="reports-in-microsoft-defender-for-business-preview"></a>Informes en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. Microsoft Defender para empresas (versión preliminar) incluye varios informes como se describe en la tabla siguiente:<br/><br/>

Hay varios informes disponibles en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En este artículo se describen estos informes, cómo puede usarlos y cómo encontrarlos.

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

<br/><br/>

## <a name="reports-in-defender-for-business"></a>Informes en Defender para empresas

|Informe  |Descripción  |
|---------|---------|
| **Informe de seguridad**  | El informe de seguridad proporciona información sobre las identidades, dispositivos y aplicaciones de la organización. Para obtener acceso a este informe, en el panel de navegación, elija **InformesGeneralSecurity** >  >  **report**. <br/><br/>**SUGERENCIA** Puede ver información similar en la página principal del portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). |
| **Protección contra amenazas**  | El informe de protección contra amenazas proporciona información sobre alertas y tendencias de alertas. Use la **columna Tendencias de** alertas para ver información sobre las alertas que se desencadenaron en los últimos 30 días. Use la **columna Estado de alerta** para ver la información de instantáneas actual sobre las alertas, como las categorías de alertas sin resolver y su clasificación. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsThreat** >  >  **protection**. <br/><br/>**SUGERENCIA**: También puede usar la lista **Incidentes** para ver información sobre alertas. En el panel de navegación, elija **Incidentes para** ver y administrar incidentes actuales. Para obtener más información, [consulta Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar).](mdb-view-manage-incidents.md) |
| **Cumplimiento y mantenimiento del dispositivo** | El informe de cumplimiento y estado del dispositivo proporciona información sobre el estado y las tendencias del dispositivo. Puedes usar este informe para determinar si los sensores de Defender para empresas (versión preliminar) funcionan correctamente en dispositivos y el estado actual de Antivirus de Microsoft Defender. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsDevice** >  >  **health and compliance**. <br/><br/>**SUGERENCIA**: Puede usar **la lista Inventario** de dispositivos para ver información sobre los dispositivos de su organización. En el panel de navegación, elija **Inventario de dispositivos**. Para obtener más información, consulta [Administrar dispositivos en Microsoft Defender para empresas (versión preliminar).](mdb-manage-devices.md) |
| **Dispositivos vulnerables** | El informe de dispositivos vulnerables proporciona información sobre dispositivos y tendencias. Usa la **columna Tendencias** para ver información sobre dispositivos que han tenido alertas en los últimos 30 días. Use la **columna Estado** para ver la información de instantáneas actual sobre los dispositivos que tienen alertas. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsVulnerable** >  >  **devices**.<br/><br/>**SUGERENCIA**: Puede usar **la lista Inventario** de dispositivos para ver información sobre los dispositivos de su organización. En el panel de navegación, elija **Inventario de dispositivos**. Para obtener más información, consulta [Administrar dispositivos en Microsoft Defender para empresas (versión preliminar).](mdb-manage-devices.md) |
| **Protección web** | El informe de protección web muestra los intentos de acceder a sitios de phishing, vectores de malware, sitios de vulnerabilidad, sitios que no son de confianza o de baja reputación y sitios que se bloquean explícitamente. Las categorías de sitios bloqueados incluyen contenido para adultos, sitios de ocio, sitios de responsabilidad legal y mucho más. Para obtener acceso a este informe, en el panel de navegación, elija **ReportsEndpointsWeb** >  >  **protection**.<br/><br/>**SUGERENCIA**: Si aún no ha configurado la protección web para su organización, elija el **Configuración** en una vista de informe. A continuación, **en Reglas**, elija **Filtrado de contenido web**. Para obtener más información sobre el filtrado de contenido web, consulte [Filtrado de contenido web](../defender-endpoint/web-content-filtering.md). |

## <a name="see-also"></a>Vea también

- [Introducción al uso de Microsoft Defender para empresas (versión preliminar)](mdb-get-started.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Administrar dispositivos en Microsoft Defender para empresas (versión preliminar)](mdb-manage-devices.md)
