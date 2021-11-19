---
title: Introducción al Plan 1 de Microsoft Defender para endpoints (versión preliminar)
description: Introducción al uso de Defender para el plan de extremo 1. Aprende a usar Defender para la nube, administrar alertas y dispositivos y ver informes.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 10/01/2021
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: e361c8a93d35a9e0cc589b8d47adadfe54ef141b
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111140"
---
# <a name="get-started-with-microsoft-defender-for-endpoint-plan-1-preview"></a>Introducción al Plan 1 de Microsoft Defender para endpoints (versión preliminar)

> [!TIP]
> Si tiene Microsoft 365 E3 O A3 pero no Microsoft 365 E5 o A5, visite [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) para registrarse en el programa de vista previa.

El portal de Microsoft 365 Defender ( ) le permite ver información sobre las amenazas detectadas, administrar las alertas e incidentes, tomar las medidas necesarias en las amenazas detectadas y administrar [https://security.microsoft.com](https://security.microsoft.com) dispositivos. El Microsoft 365 Defender es donde puede empezar a interactuar con las capacidades de protección contra amenazas que obtiene con Defender for Endpoint Plan 1 (versión preliminar). En las secciones siguientes se describe cómo empezar:

- [El portal de Microsoft 365 Defender](#the-microsoft-365-defender-portal)
- [Visualización y administración de incidentes & alertas](#view-and-manage-incidents--alerts)
- [Administración de dispositivos](#manage-devices)
- [Visualización de informes](#view-reports)

## <a name="the-microsoft-365-defender-portal"></a>El portal de Microsoft 365 Defender

El Microsoft 365 Defender web ( ) es donde verá alertas, administrará dispositivos [https://security.microsoft.com](https://security.microsoft.com) y verá informes. Cuando inicie sesión en el portal de Microsoft 365 Defender, empezará por la página principal, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/m365-defender-portal.png" alt-text="Portal de Microsoft 365 Defender":::

La página principal proporciona al equipo de seguridad una vista de agregado de instantáneas de alertas, estado del dispositivo y amenazas detectadas. Defender para la nube está configurado para que el equipo de operaciones de seguridad pueda encontrar la información que está buscando de forma rápida y sencilla.

> [!NOTE]
> Nuestros ejemplos que se muestran en este artículo pueden diferir de lo que se ve en el portal Microsoft 365 Defender web. Lo que vea en el portal depende de sus licencias y permisos. Además, el equipo de seguridad puede personalizar el portal de la organización agregando, quitando y reorganizando tarjetas.

### <a name="cards-highlight-key-information-and-include-recommendations"></a>Tarjetas resaltan información clave e incluyen recomendaciones

La página principal incluye tarjetas, como la tarjeta Incidentes activos que se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/active-incidents-card.png" alt-text="Tarjeta de incidentes activos":::

La tarjeta le proporciona información de un vistazo, junto con un vínculo o botón que puede seleccionar para ver información más detallada. En referencia a nuestra tarjeta de ejemplo Incidentes activos, podemos seleccionar **Ver** todos los incidentes para navegar a nuestra lista de incidentes.

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="Lista de incidentes":::

### <a name="navigation-bar-makes-it-easy-to-find-alerts-the-action-center-and-more"></a>La barra de navegación facilita la búsqueda de alertas, el Centro de acciones y mucho más

La barra de navegación de la parte izquierda de la pantalla le permite moverse fácilmente entre incidentes, alertas, centro de acción, informes y configuración. En la tabla siguiente se describe la barra de navegación.<br/><br/>

| Elemento de barra de navegación | Descripción |
|:---|:---|
| **Inicio** | Navega a la página principal del [Microsoft 365 Defender portal](../defender/microsoft-365-security-center-mde.md). |
| **Alertas de & incidentes** | Se expande para mostrar **incidentes** y **alertas**. |
| **Alertas de & incidentes**  >  **Incidentes** | Navega a la **lista Incidentes.** Los incidentes se crean cuando se desencadenan alertas o se detectan amenazas. De forma predeterminada, la lista Incidentes muestra los datos de los **últimos** 30 días, con el incidente más reciente enumerado primero. <br/><br/> Para obtener más información, vea [Incidents](view-incidents-queue.md). |
| **Alertas de & incidentes**  >  **Alertas** | Navega a la lista **alertas** (también denominada cola **de alertas**). Las alertas se desencadenan cuando se detecta un archivo, proceso o comportamiento sospechoso o malintencionado. De forma predeterminada, la **lista de** alertas muestra los datos de los últimos 30 días, con la alerta más reciente en primer lugar. <br/><br/> Para obtener más información, vea [Alerts](alerts-queue.md). |
| **Centro de acciones** | Navega al Centro de acciones, que realiza un seguimiento de las acciones de corrección y respuesta manual. El Centro de acciones realiza un seguimiento de actividades como estas: <br/>- Antivirus de Microsoft Defender encuentra un archivo malintencionado y, a continuación, bloquea o quita ese archivo. <br/>- El equipo de seguridad aísla un dispositivo.<br/>- Defender for Endpoint detecta y pone en cuarentena un archivo. <br/><br/> Para obtener más información, vea [Centro de acciones](auto-investigation-action-center.md). |
| **Puntuación de seguridad** | Muestra una representación de la posición de seguridad de la organización junto con una lista de acciones de mejora y métricas. <br/><br/> Para obtener más información, consulte [Puntuación segura de Microsoft](../defender/microsoft-secure-score.md). |
| **Learning central** | Navega a una lista de rutas de aprendizaje a las que puede acceder para obtener más información sobre Microsoft 365 de seguridad.  |
| **Puntos de conexión**  >  **Búsqueda** | Navega a una página donde puedes buscar dispositivos específicos por nombre de dispositivo. En la lista de resultados, puede ver detalles, como el nivel de riesgo y el estado de mantenimiento, de un vistazo. |
|  **Puntos de conexión**  >  **Inventario de dispositivos** | Navega a la lista de dispositivos que están incorporados a Defender para endpoint. Proporciona información sobre dispositivos, como sus niveles de exposición y riesgo. <br/><br/> Para obtener más información, consulta [Inventario de dispositivos](machines-view-overview.md). |
|  **Puntos de conexión**  >  **Líneas & de configuración** | Se expande para mostrar **líneas base de seguridad** y administración de **configuración.** |
|  **Puntos de conexión**  >  **Líneas & base de configuración**  >  **Líneas base de seguridad** | Las líneas base de seguridad son directivas preconfiguradas y grupos de opciones de configuración que pueden ayudarle a aplicar la configuración de seguridad recomendada de forma eficaz y eficaz. Las líneas base incluyen opciones basadas en los procedimientos recomendados del sector. Puede mantener la configuración predeterminada o personalizar las líneas base para que se adapten a las necesidades de su organización. <br/><br/> Para obtener más información, consulte [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines). |
|  **Puntos de conexión**  >  **Líneas & base de configuración**  >  **Administración de configuración** | Navega a la página **Administración de configuración** de dispositivos, donde puedes ver información sobre dispositivos incorporados y tomar medidas para incorporar más dispositivos. |
| **Informes** | Navega a los informes, como el informe de protección contra [amenazas,](threat-protection-reports.md)el informe [de estado](machine-reports.md)y cumplimiento del dispositivo y el informe de [protección web](web-protection-overview.md). |
| **Estado** | Incluye vínculos al **Centro de mensajes y estado** del **servicio.**  |
| **Estado**  >  **Estado del servicio** | Navega a la página Estado del servicio en el Centro de administración de Microsoft 365. Esta página le permite ver el estado de mantenimiento en todos los servicios disponibles con las suscripciones de su organización.   |
| **Estado**  >  **Centro de mensajes** | Navega al Centro de mensajes en el Centro de administración de Microsoft 365. El Centro de mensajes proporciona información sobre los cambios planeados. Cada mensaje describe lo que viene, cómo puede afectar a los usuarios y cómo administrar los cambios. |  
| **Permisos & roles** | Permite conceder permisos para usar el portal Microsoft 365 Defender web. Los permisos se conceden a través de roles Azure Active Directory (Azure AD). Seleccione un rol y aparecerá un panel desplegable. El menú desplegable contiene un vínculo a Azure AD donde puede agregar o quitar miembros de un grupo de roles. <br/><br/> Para obtener más información, vea [Manage portal access using role-based access control](rbac.md).  |
| **Configuración** | Navega a la configuración general de su portal de Microsoft 365 Defender (enumerado como Centro de **seguridad)** y Defender para endpoint (enumerado **como Extremos**). <br/><br/> Para obtener más información, [vea Configuración](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal). |
| **Más recursos** | Muestra una lista de más portales y centros, como Azure Active Directory y el Centro de cumplimiento de Microsoft 365. <br/><br/> Para obtener más información, vea [Portales de seguridad de Microsoft y centros de administración](../defender/portals.md). |

> [!TIP]
> Para obtener más información, vea [la información general Microsoft 365 Defender portal .](../defender/microsoft-365-security-center-mde.md)

## <a name="view-and-manage-incidents--alerts"></a>Ver y administrar incidentes & alertas

Cuando inicie sesión en el portal de Microsoft 365 Defender, asegúrese de ver y administrar sus incidentes y alertas. Comience con la **lista incidentes.** En la siguiente imagen se muestra una lista de incidentes, incluidos uno con gravedad alta y otro con gravedad media.

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="Lista de incidentes":::

Seleccione un incidente para ver detalles sobre el incidente. Los detalles incluyen qué alertas se desencadenaron, cuántos dispositivos y usuarios se vieron afectados y otros detalles. En la siguiente imagen se muestra un ejemplo de detalles de incidentes.

:::image type="content" source="../../media/mde-p1/single-incident.png" alt-text="Detalles del incidente":::

Usa las **pestañas**  Alertas, **Dispositivos** y Usuarios para ver más información, como las alertas que se desencadenaron, los dispositivos que se vieron afectados y las cuentas de usuario que se vieron afectadas. Desde allí, puedes realizar acciones de respuesta manuales, como aislar un dispositivo, detener y anular un archivo, y así sucesivamente.

> [!TIP]
> Para obtener más información sobre el uso de **la vista** Incidentes, vea [Administrar incidentes](manage-incidents.md).

## <a name="manage-devices"></a>Administrar dispositivos

Para ver y administrar los dispositivos de la organización, en la barra de navegación, en **Extremos**, seleccione **Inventario de dispositivos**. Verás una lista de dispositivos como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/device-inventory.png" alt-text="Inventario de dispositivos":::

La lista incluye dispositivos para los que se generaron alertas. De forma predeterminada, los datos mostrados son de los últimos 30 días, con los elementos más recientes enumerados primero. Selecciona un dispositivo para ver más información sobre él. Se abre un panel desplegable, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/device-inventory-selecteddevice.png" alt-text="Detalles del dispositivo seleccionado":::

El panel desplegable muestra detalles, como las alertas activas del dispositivo, e incluye vínculos para realizar acciones, como aislar un dispositivo.

Si hay alertas activas en el dispositivo, puedes verlos en el panel desplegable. Seleccione una alerta individual para ver más detalles sobre ella. También puedes realizar una acción, como Aislar **dispositivo,** para que puedas investigar el dispositivo aún más mientras minimizas el riesgo de infectar otros dispositivos.

> [!TIP]
> Para obtener más información, consulta [Investigar dispositivos en la lista Defender para dispositivos de punto de conexión](investigate-machines.md).

## <a name="view-reports"></a>Ver informes

En Defender for Endpoint Plan 1, hay varios informes disponibles en Microsoft 365 Defender portal. Para obtener acceso a los informes, siga estos pasos:

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En la barra de navegación, elija **Informes**.

3. Seleccione un informe en la lista. Verá los tres informes siguientes:

   - Informe de protección contra amenazas
   - Informe de estado del dispositivo
   - Informe de protección web

> [!TIP]
> Para obtener más información, vea [Informes de protección contra amenazas](threat-protection-reports.md).

### <a name="threat-protection-report"></a>Informe de protección contra amenazas

Para obtener acceso al informe de protección contra amenazas, en el portal de Microsoft 365 Defender, elija **Informes** y, a continuación, elija **Protección contra amenazas**. El informe de protección contra amenazas muestra tendencias de alerta, estado, categorías y mucho más. Las vistas se organizan en dos columnas: **Tendencias de alerta** y Estado de **alerta,** como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/threat-protection-report.png" alt-text="Informe de protección contra amenazas":::

Desplácese hacia abajo para ver todas las vistas de cada lista.

- De forma predeterminada,  las vistas de la columna Tendencias de alerta muestran datos de los últimos 30 días, pero puede establecer una vista para mostrar datos de los últimos tres meses, los últimos seis meses o un intervalo de tiempo personalizado (hasta 180 días).
- Las vistas de la **columna Estado de** alerta son una instantánea del día laborable anterior.

> [!TIP]
> Para obtener más información, vea [Informe de protección contra amenazas en Defender for Endpoint](threat-protection-reports.md).

### <a name="device-health-report"></a>Informe de estado del dispositivo

Para obtener acceso al informe de estado del dispositivo, en el portal de Microsoft 365 Defender, elija **Informes** y, a continuación, elija **Estado del dispositivo**. El informe de estado del dispositivo muestra el estado de mantenimiento y el antivirus en todos los dispositivos de la organización. De forma similar al [informe de protección](#threat-protection-report)contra amenazas, las vistas se organizan en dos columnas: Tendencias de dispositivo y **Resumen** de dispositivos, como se muestra en la imagen siguiente: 

:::image type="content" source="../../media/mde-p1/device-health-report.png" alt-text="Informe de estado del dispositivo":::

Desplácese hacia abajo para ver todas las vistas de cada lista. De forma predeterminada,  las vistas de la columna Tendencias de dispositivo muestran datos de los últimos 30 días, pero puede cambiar una vista para mostrar los datos de los últimos tres meses, los últimos seis meses o un intervalo de tiempo personalizado (hasta 180 días). Las **vistas de resumen del** dispositivo son instantáneas del día laborable anterior.

> [!TIP]
> Para obtener más información, consulta [Estado del dispositivo](machine-reports.md).

### <a name="web-protection-report"></a>Informe de protección web

Para obtener acceso al informe de estado del dispositivo, en el portal de Microsoft 365 Defender, elija **Informes** y, a continuación, **elija Protección web**. El informe de protección web muestra detecciones con el tiempo, como direcciones URL malintencionadas e intentos de obtener acceso a direcciones URL bloqueadas, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/web-protection-report.png" alt-text="Informe de protección web":::

Desplácese hacia abajo para ver todas las vistas del informe de protección web. Algunas vistas incluyen vínculos que permiten ver más detalles, configurar las características de protección contra amenazas e incluso administrar indicadores que sirven como excepciones en Defender para endpoint.

> [!TIP]
> Para obtener más información, vea [Protección web](web-protection-overview.md).

## <a name="next-steps"></a>Siguientes pasos

- [Administrar Microsoft Defender para endpoint plan 1 (versión preliminar)](mde-p1-maintenance-operations.md)
- [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md)
