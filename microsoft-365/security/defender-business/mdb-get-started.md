---
title: Introducción al uso del portal Microsoft 365 Defender web
description: Vea cómo empezar a usar el portal Microsoft 365 Defender web. Obtenga información sobre cómo navegar por el portal y ver el estado y las recomendaciones de seguridad actuales
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 3e46ee70c1c745c336d049f039de04282c5848d8
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525394"
---
# <a name="get-started-using-the-microsoft-365-defender-portal"></a>Introducción al uso del portal Microsoft 365 Defender web

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando [para Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Después de que te hayas registrado en Microsoft Defender para empresas, querrás familiarizarte con el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En este artículo se incluyen las siguientes secciones:

- [Cómo navegar por el portal Microsoft 365 Defender web](#navigate-the-microsoft-365-defender-portal)

- [Learning sobre incidentes y acciones de respuesta](#complete-a-learning-module-about-incidents-and-response-actions) 

- [Pasos siguientes](#next-steps)

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="navigate-the-microsoft-365-defender-portal"></a>Navegar por el Microsoft 365 Defender web

El Microsoft 365 Defender web ([https://security.microsoft.com](https://security.microsoft.com)) es su tienda única para usar y administrar Microsoft Defender para empresas. Incluye un banner de bienvenida y llamadas para ayudarte a empezar, tarjetas que incluyen información relevante y una barra de navegación para facilitar el acceso a las distintas características y funcionalidades.
 
Tómese un momento para familiarizarse con su Microsoft 365 Defender portal.

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Portal de Microsoft 365 Defender":::

### <a name="use-the-navigation-bar"></a>Usar la barra de navegación

Use la barra de navegación de la parte izquierda de la pantalla para obtener acceso a los incidentes, ver informes y administrar las directivas de seguridad. En la tabla siguiente se describen los elementos que verá en la barra de navegación.

| Elemento | Descripción |
|:---|:---|
| **Inicio** | Te lleva a la página principal en Microsoft 365 Defender. La página principal incluye tarjetas que resaltan las amenazas activas que se detectaron, junto con recomendaciones para ayudar a proteger los datos y dispositivos de la empresa. <br/><br/>Recomendaciones se incluyen en Defender para empresas puede ahorrarle tiempo y esfuerzo al equipo de seguridad. Recomendaciones se basan en los procedimientos recomendados del sector. Para obtener más información acerca de las recomendaciones, consulte [Security recommendations - Administración de amenazas y vulnerabilidades](../defender-endpoint/tvm-security-recommendation.md). |
| **Incidentes** | Le lleva a la lista de incidentes recientes. A medida que se desencadenan las alertas, se crean incidentes. Un incidente puede incluir varias alertas. Asegúrese de revisar los incidentes con regularidad. <br/><br/>Para obtener más información acerca de los incidentes, vea [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md).|
| **Centro de actividades** | Le lleva a la lista de acciones de respuesta, incluidas las acciones completadas o pendientes. <br/>- Seleccione la **pestaña** Historial para ver las acciones realizadas. Algunas acciones se toman automáticamente; otros se toman manualmente o se completan después de su aprobación. <br/>- Seleccione la **pestaña** Pendiente para ver las acciones que requieren aprobación para continuar. <br/><br/>Para obtener más información sobre el Centro de acciones, vea [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md). |
| **Análisis de amenazas** | Le lleva a una vista de las amenazas actuales y le proporciona una vista de un vistazo del panorama de amenazas. El análisis de amenazas también incluye informes e información de investigadores de seguridad de Microsoft. <br/><br/>Para obtener más información sobre el análisis de amenazas, consulte [Seguimiento y respuesta a amenazas emergentes a través del análisis de amenazas](../defender-endpoint/threat-analytics.md). |
| **Puntuación de seguridad** | Le proporciona una representación de la posición de seguridad de su empresa y ofrece sugerencias para mejorarla.<br/><br/>Para obtener más información sobre puntuación segura, consulta [Puntuación segura de Microsoft para dispositivos](../defender-endpoint/tvm-microsoft-secure-score-devices.md). |
| **Learning hub** | Proporciona acceso a la formación de seguridad y otros recursos a través de rutas de aprendizaje que se incluyen con la suscripción. Puedes filtrar por producto, nivel de habilidad, rol y mucho más. El centro de Learning puede ayudar a su equipo de seguridad a mejorar las características de seguridad & en Defender para empresas y más ofertas de Microsoft, como [Microsoft Defender para](../defender-endpoint/microsoft-defender-endpoint.md) endpoint y [Microsoft Defender para Office 365](../office-365-security/defender-for-office-365.md).  |
| **Puntos de conexión** >  **Búsqueda** | Permite buscar uno o varios dispositivos que se incorporaron a Microsoft Defender para empresas. |
| **Puntos de conexión** >  **Inventario de dispositivos** | Permite buscar uno o varios dispositivos que se incorporaron a Microsoft Defender para empresas. |
| **Puntos de conexión** >  **Administración de vulnerabilidades** | Le proporciona un panel, recomendaciones, actividades de corrección, un inventario de software y una lista de posibles debilidades dentro de su empresa. |
| **Puntos de conexión** >  **Tutoriales** | Proporciona acceso a tutoriales y simulaciones para ayudarle a obtener más información sobre cómo funcionan las características de protección contra amenazas. <br/><br/>Seleccione el **vínculo Leer el tutorial** antes de intentar obtener el archivo de simulación para cada tutorial. Algunas simulaciones requieren Office aplicaciones, como Microsoft Word, para leer el tutorial. |
| **Puntos de conexión** >  **Configuración del dispositivo** | Enumera las directivas de seguridad por sistema operativo y por tipo. <br/><br/>Para obtener más información sobre las directivas de seguridad, consulta [Ver o editar directivas en Microsoft Defender para empresas](mdb-view-edit-policies.md). |
| **Informes** | Enumera los informes de seguridad disponibles. Estos informes le permiten ver las tendencias de seguridad, ver detalles sobre detecciones y alertas de amenazas y obtener más información sobre los dispositivos vulnerables de su empresa. |
| **Estado** | Permite ver el estado del servicio y planear los próximos cambios. <br/>- Seleccione **Estado del servicio** para ver el estado de mantenimiento de los servicios Microsoft 365 que se incluyen en la suscripción de su empresa. <br/>- Seleccione **Centro de mensajes** para obtener información sobre los cambios planeados y qué esperar.  |
| **Permisos & roles** | Le permite asignar permisos a las personas de su empresa que administrarán su seguridad y verán incidentes e informes en el portal de Microsoft 365 Defender web. También te permite configurar y administrar grupos de dispositivos para incorporar los dispositivos de tu empresa y asignar tus directivas de protección contra amenazas.  |
| **Configuración** | Permite editar la configuración del portal de Microsoft 365 Defender y Microsoft Defender para empresas. Por ejemplo, puede incorporar (o fuera de la pantalla) y los dispositivos de su empresa (también denominados puntos de conexión). También puede definir reglas, como las reglas de supresión de alertas, y configurar indicadores para bloquear o permitir determinados archivos o procesos.  |
| **Más recursos** | Navegue a otros portales, como Azure Active Directory. Tenga en cuenta que el portal Microsoft 365 Defender debe satisfacer sus necesidades sin necesidad de navegar a otros portales. |

## <a name="complete-a-learning-module-about-incidents-and-response-actions"></a>Completar un módulo de aprendizaje sobre incidentes y acciones de respuesta

Consulte el módulo de aprendizaje, [Detectar y responder a problemas de seguridad](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/) para obtener información general sobre incidentes y acciones de respuesta. Aprenderá sobre la cola de incidentes, las alertas y las acciones de respuesta que puede realizar. Este curso te ayudará a empezar a trabajar con incidentes en Defender para empresas.

> [!NOTE]
> Aunque el módulo de [aprendizaje (Detectar](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/) y responder a problemas de seguridad) es realmente para Microsoft Defender para Endpoint, los conceptos básicos y el flujo general son similares a lo que verá en Defender para empresas.

## <a name="next-steps"></a>Siguientes pasos

Ahora que tienes una introducción a Defender para empresas, prueba una o varias de las siguientes tareas:

- [Pruebe tutoriales y simulaciones en Microsoft Defender para empresas](mdb-tutorials.md)

- [Administrar dispositivos en Microsoft Defender para empresas](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)

- [Ver o editar directivas en Microsoft Defender para empresas](mdb-view-edit-policies.md)