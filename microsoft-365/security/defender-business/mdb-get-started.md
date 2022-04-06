---
title: Comenzar mediante el portal de Microsoft 365 Defender
description: Consulte cómo empezar a usar el portal de Microsoft 365 Defender. Obtenga información sobre cómo navegar por el portal y ver el estado de seguridad y las recomendaciones actuales.
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
ms.openlocfilehash: c5a940676eab6ae3a07c526ecb1bd910ed8751fe
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667150"
---
# <a name="get-started-using-the-microsoft-365-defender-portal"></a>Comenzar mediante el portal de Microsoft 365 Defender

> [!IMPORTANT]
> Microsoft Defender para Empresas se está implementando para [Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender for Business como una suscripción independiente está en versión preliminar y se implementará gradualmente para los clientes y asociados de TI que [se registren aquí](https://aka.ms/mdb-preview) para solicitarla. La versión preliminar incluye un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a los productos o servicios preliminares que se pueden modificar sustancialmente antes de que se publiquen comercialmente. Microsoft no ofrece ninguna garantía, expresa o implícita, de la información que se proporciona aquí. 

Una vez que se haya registrado para Microsoft Defender para Empresas, querrá familiarizarse con el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En este artículo se incluyen las siguientes secciones:

- [Cómo navegar por el portal de Microsoft 365 Defender](#navigate-the-microsoft-365-defender-portal)

- [Learning módulos sobre incidentes y acciones de respuesta](#complete-a-learning-module-about-incidents-and-response-actions) 

- [Pasos siguientes](#next-steps)

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre Microsoft Defender para Empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="navigate-the-microsoft-365-defender-portal"></a>Navegar por el portal de Microsoft 365 Defender

El portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) es tu tienda integral para usar y administrar Microsoft Defender para Empresas. Incluye un banner de bienvenida y llamadas que te ayudarán a empezar, tarjetas que exponen información relevante y una barra de navegación para que puedas acceder fácilmente a las distintas características y funcionalidades.
 
Tómese un momento para familiarizarse con su portal de Microsoft 365 Defender.

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Portal de Microsoft 365 Defender":::

### <a name="use-the-navigation-bar"></a>Usar la barra de navegación

Use la barra de navegación del lado izquierdo de la pantalla para acceder a los incidentes, ver informes y administrar las directivas de seguridad. En la tabla siguiente se describen los elementos que verá en la barra de navegación.

| Item | Descripción |
|:---|:---|
| **Inicio** | Le lleva a la página principal en Microsoft 365 Defender. La página principal incluye tarjetas que resaltan las amenazas activas que se detectaron, junto con recomendaciones para ayudar a proteger los datos y los dispositivos de su empresa. <br/><br/>Recomendaciones se incluyen en Defender for Business puede ahorrar tiempo y esfuerzo al equipo de seguridad. Recomendaciones se basan en los procedimientos recomendados del sector. Para obtener más información sobre las recomendaciones, consulte [Recomendaciones de seguridad: Administración de amenazas y vulnerabilidades](../defender-endpoint/tvm-security-recommendation.md). |
| **Incidentes** | Le lleva a la lista de incidentes recientes. A medida que se desencadenan alertas, se crean incidentes. Un incidente puede incluir varias alertas. Asegúrese de revisar los incidentes con regularidad. <br/><br/>Para más información sobre los incidentes, consulte [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md).|
| **Centro de actividades** | Le lleva a la lista de acciones de respuesta, incluidas las acciones completadas o pendientes. <br/>- Seleccione la pestaña **Historial** para ver las acciones realizadas. Algunas acciones se realizan automáticamente; otros se toman manualmente o se completan después de que se aprueben. <br/>- Seleccione la pestaña **Pendiente** para ver las acciones que requieren aprobación para continuar. <br/><br/>Para obtener más información sobre el Centro de acciones, consulte [Revisar las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md). |
| **Análisis de amenazas** | Le lleva a una vista de las amenazas actuales y le proporciona una vista general del panorama de las amenazas. El análisis de amenazas también incluye informes e información de investigadores de seguridad de Microsoft. <br/><br/>Para más información sobre el análisis de amenazas, consulte [Seguimiento y respuesta a amenazas emergentes a través del análisis de amenazas](../defender-endpoint/threat-analytics.md). |
| **Puntuación de seguridad** | Proporciona una representación de la posición de seguridad de su empresa y ofrece sugerencias para mejorarla.<br/><br/>Para obtener más información sobre la puntuación de seguridad, consulte [Puntuación de seguridad de Microsoft para dispositivos](../defender-endpoint/tvm-microsoft-secure-score-devices.md). |
| **centro de Learning** | Proporciona acceso al entrenamiento de seguridad y a otros recursos a través de rutas de aprendizaje que se incluyen con la suscripción. Puede filtrar por producto, nivel de aptitud, rol y mucho más. El centro de Learning puede ayudar al equipo de seguridad a aumentar las características de seguridad & funcionalidades de Defender para empresas y más ofertas de Microsoft, como [Microsoft Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md) y [Microsoft Defender para Office 365](../office-365-security/defender-for-office-365.md).  |
| **Extremos** >  **Búsqueda** | Permite buscar uno o varios dispositivos que se incorporaron a Microsoft Defender para Empresas. |
| **Extremos** >  **Inventario de dispositivos** | Permite buscar uno o varios dispositivos que se incorporaron a Microsoft Defender para Empresas. |
| **Extremos** >  **Administración de vulnerabilidades** | Proporciona un panel, recomendaciones, actividades de corrección, un inventario de software y una lista de posibles debilidades dentro de la empresa. |
| **Extremos** >  **Tutoriales** | Proporciona acceso a tutoriales y simulaciones para ayudarle a obtener más información sobre cómo funcionan las características de protección contra amenazas. <br/><br/>Seleccione el vínculo **Leer el tutorial** antes de intentar obtener el archivo de simulación para cada tutorial. Algunas simulaciones requieren Office aplicaciones, como Microsoft Word, para leer el tutorial. |
| **Extremos** >  **Configuración del dispositivo** | Enumera las directivas de seguridad por sistema operativo y por tipo. <br/><br/>Para obtener más información sobre las directivas de seguridad, consulte [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-policies.md). |
| **Informes** | Enumera los informes de seguridad disponibles. Estos informes le permiten ver las tendencias de seguridad, ver detalles sobre las detecciones y alertas de amenazas y obtener más información sobre los dispositivos vulnerables de su empresa. |
| **Estado** | Permite ver el estado de mantenimiento del servicio y planear los próximos cambios. <br/>- Seleccione **Estado del servicio** para ver el estado de mantenimiento de los servicios de Microsoft 365 que se incluyen en la suscripción de su empresa. <br/>- Seleccione **Centro de** mensajes para obtener información sobre los cambios planeados y lo que se espera.  |
| **Permisos & roles** | Permite asignar permisos a las personas de la empresa que administrarán la seguridad y verán los incidentes e informes en el portal de Microsoft 365 Defender. También le permite configurar y administrar grupos de dispositivos para incorporar los dispositivos de su empresa y asignar las directivas de protección contra amenazas.  |
| **Configuración** | Permite editar la configuración del portal de Microsoft 365 Defender y Microsoft Defender para Empresas. Por ejemplo, puede incorporar (o offboard) y los dispositivos de su empresa (también conocidos como puntos de conexión). También puede definir reglas, como las reglas de supresión de alertas, y configurar indicadores para bloquear o permitir determinados archivos o procesos.  |
| **Más recursos** | Vaya a otros portales, como Azure Active Directory. Tenga en cuenta que el portal de Microsoft 365 Defender debe satisfacer sus necesidades sin necesidad de navegar a otros portales. |

## <a name="complete-a-learning-module-about-incidents-and-response-actions"></a>Completar un módulo de aprendizaje sobre incidentes y acciones de respuesta

Consulte el módulo de aprendizaje [Detectar y responder a problemas de seguridad](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/) para obtener información general sobre incidentes y acciones de respuesta. Obtendrá información sobre la cola de incidentes, las alertas y las acciones de respuesta que puede realizar. Este curso le ayudará a empezar a trabajar con incidentes en Defender for Business.

> [!NOTE]
> Aunque el módulo de aprendizaje ([Detectar y responder a problemas de seguridad](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/)) es realmente para Microsoft Defender para punto de conexión, los conceptos básicos y el flujo general son similares a los que verá en Defender para empresas.

## <a name="next-steps"></a>Siguientes pasos

Ahora que tiene información general sobre Defender para empresas, pruebe una o varias de las siguientes tareas:

- [Pruebe tutoriales y simulaciones en Microsoft Defender para Empresas](mdb-tutorials.md)

- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)

- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)

- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)

- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)

- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-policies.md)