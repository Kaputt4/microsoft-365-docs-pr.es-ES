---
title: Introducción al plan 1 de Microsoft Defender para punto de conexión
description: Introducción al uso del plan 1 de Defender para punto de conexión. Obtenga información sobre cómo usar Defender for Cloud, administrar alertas y dispositivos y ver informes.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/03/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.custom: intro-get-started
ms.openlocfilehash: 3926282bce47af2abee905f5c95844a8a78c6d33
ms.sourcegitcommit: 44ece87e3e0c0c851dfc1e77211ac3e5e4a5b973
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66617116"
---
# <a name="get-started-with-microsoft-defender-for-endpoint-plan-1"></a>Introducción al plan 1 de Microsoft Defender para punto de conexión

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

El portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) le permite ver información sobre las amenazas detectadas, administrar las alertas e incidentes, realizar las acciones necesarias en las amenazas detectadas y administrar los dispositivos. El portal de Microsoft 365 Defender es donde puede empezar a interactuar con las funcionalidades de protección contra amenazas que obtiene con el plan 1 de Defender para punto de conexión. En las secciones siguientes se describe cómo empezar a trabajar:

- [El portal de Microsoft 365 Defender incluye:](#the-microsoft-365-defender-portal)
- [Visualización y administración de incidentes & alertas](#view-and-manage-incidents--alerts)
- [Administración de dispositivos](#manage-devices)
- [Visualización de informes](#view-reports)

## <a name="the-microsoft-365-defender-portal"></a>El portal de Microsoft 365 Defender incluye:

El portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) es donde verá alertas, administrará dispositivos y verá informes. Al iniciar sesión en el portal de Microsoft 365 Defender, comenzará con la página Inicio, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/m365-defender-portal.png" alt-text="El portal de Microsoft 365 Defender" lightbox="../../media/mde-p1/m365-defender-portal.png":::

La página Inicio proporciona al equipo de seguridad una vista agregada de instantáneas de alertas, estado del dispositivo y amenazas detectadas. Defender for Cloud está configurado para que el equipo de operaciones de seguridad pueda encontrar la información que busca de forma rápida y sencilla.

> [!NOTE]
> Nuestros ejemplos que se muestran en este artículo pueden diferir de lo que se ve en el portal de Microsoft 365 Defender. Lo que vea en el portal depende de sus licencias y permisos. Además, el equipo de seguridad puede personalizar el portal de la organización agregando, quitando y reorganizando tarjetas.

### <a name="cards-highlight-key-information-and-include-recommendations"></a>Las tarjetas resaltan información clave e incluyen recomendaciones

La página Inicio incluye tarjetas, como la tarjeta Incidentes activos que se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/active-incidents-card.png" alt-text="La tarjeta Incidentes activos" lightbox="../../media/mde-p1/active-incidents-card.png":::

La tarjeta le proporciona información de un vistazo, junto con un vínculo o botón que puede seleccionar para ver información más detallada. En referencia a nuestra tarjeta de incidentes activos de ejemplo, podemos seleccionar **Ver todos los incidentes** para ir a nuestra lista de incidentes.

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="Lista de incidentes" lightbox="../../media/mde-p1/incidents.png":::

### <a name="navigation-bar-makes-it-easy-to-find-alerts-the-action-center-and-more"></a>La barra de navegación facilita la búsqueda de alertas, el Centro de acciones y mucho más

La barra de navegación del lado izquierdo de la pantalla le permite moverse fácilmente entre incidentes, alertas, el Centro de acciones, los informes y la configuración. En la tabla siguiente se describe la barra de navegación.<br/><br/>

| Elemento de barra de navegación | Descripción |
|:---|:---|
| **Inicio** | Navega a la página Inicio del [portal de Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md). |
| **Alertas de & incidentes** | Se expande para mostrar incidentes y **alertas**. |
| **Alertas de &** >  incidentes **Incidentes** | Navega a la lista **Incidentes** . Los incidentes se crean cuando se desencadenan alertas o se detectan amenazas. De forma predeterminada, la lista Incidentes muestra los datos de los **últimos** 30 días, con el incidente más reciente en primer lugar. <br/><br/> Para más información, consulte [Incidentes](view-incidents-queue.md). |
| **Alertas de &** >  incidentes **Alertas** | Navega a la lista **Alertas** (también denominada **cola de alertas**). Las alertas se desencadenan cuando se detecta un archivo, proceso o comportamiento sospechoso o malintencionado. De forma predeterminada, la lista **Alertas** muestra los datos de los últimos 30 días, con la alerta más reciente en primer lugar. <br/><br/> Para obtener más información, consulte [Alertas](alerts-queue.md). |
| **Centro de acciones** | Navega al Centro de acciones, que realiza un seguimiento de las acciones de corrección y respuesta manual. El Centro de acciones realiza un seguimiento de actividades como las siguientes: <br/>- Antivirus de Microsoft Defender encuentra un archivo malintencionado y, a continuación, bloquea o quita ese archivo. <br/>- El equipo de seguridad aísla un dispositivo.<br/>- Defender para punto de conexión detecta y pone en cuarentena un archivo. <br/><br/> Para obtener más información, consulte [Centro de acciones](auto-investigation-action-center.md). |
| **Puntuación de seguridad** | Muestra una representación de la posición de seguridad de la organización junto con una lista de acciones y métricas de mejora. <br/><br/> Para obtener más información, consulte [Puntuación de seguridad de Microsoft](../defender/microsoft-secure-score.md). |
| **Centro de aprendizaje** | Navega a una lista de rutas de aprendizaje a las que puede acceder para obtener más información sobre las funcionalidades de seguridad de Microsoft 365.  |
| **Extremos** >  **Búsqueda** | Navega a una página donde puede buscar dispositivos específicos por nombre de dispositivo. En la lista de resultados, puede ver detalles, como el nivel de riesgo y el estado de mantenimiento, de un vistazo. |
|  **Extremos** >  **Inventario de dispositivos** | Navega a la lista de dispositivos que se incorporan a Defender para punto de conexión. Proporciona información sobre los dispositivos, como sus niveles de exposición y riesgo. <br/><br/> Para más información, consulte [Inventario de dispositivos](machines-view-overview.md). |
|  **Extremos** >  **Líneas base de & de configuración** | Se expande para mostrar **las líneas base de seguridad** y **la administración de configuración**. |
|  **Extremos** >  Líneas base  >  **de & de configuración** **Líneas base de seguridad** | Las líneas base de seguridad son directivas preconfiguradas y grupos de opciones de configuración que pueden ayudarle a aplicar la configuración de seguridad recomendada de forma eficaz y eficaz. Las líneas base incluyen configuraciones basadas en los procedimientos recomendados del sector. Puede mantener la configuración predeterminada o personalizar las líneas base para satisfacer las necesidades de su organización. <br/><br/> Para más información, consulte [Uso de líneas base de seguridad para configurar dispositivos Windows 10 en Intune](/mem/intune/protect/security-baselines). |
|  **Extremos** >  Líneas base  >  **de & de configuración** **Administración de configuración** | Navega a la página **Administración de configuración** de dispositivos, donde puede ver información sobre los dispositivos incorporados y realizar pasos para incorporar más dispositivos. |
| **Informes** | Navega a los informes, como el [informe de protección contra amenazas](threat-protection-reports.md), el [informe de cumplimiento y estado del dispositivo](machine-reports.md) y el [informe de protección web](web-protection-overview.md). |
| **Estado** | Incluye vínculos al **Estado del servicio** y **al Centro de mensajes**.  |
| **Salud** >  **Estado del servicio** | Navega a la página Estado del servicio del Centro de administración de Microsoft 365. Esta página le permite ver el estado de mantenimiento en todos los servicios disponibles con las suscripciones de su organización.   |
| **Salud** >  **Centro de mensajes** | Navega al Centro de mensajes en el Centro de administración de Microsoft 365. El Centro de mensajes proporciona información sobre los cambios planeados. Cada mensaje describe lo que viene, cómo puede afectar a los usuarios y cómo administrar los cambios. |  
| **Permisos & roles** | Permite conceder permisos para usar el portal de Microsoft 365 Defender. Los permisos se conceden a través de roles en Azure Active Directory (Azure AD). Seleccione un rol y aparecerá un panel flotante. El control flotante contiene un vínculo a Azure AD donde puede agregar o quitar miembros de un grupo de roles. <br/><br/> Para más información, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).  |
| **Configuración** | Navega a la configuración general del portal de Microsoft 365 Defender (que aparece como Centro de **seguridad**) y Defender para punto de conexión (que aparece como **puntos de conexión**). <br/><br/> Para más información, consulte [Configuración](../defender/microsoft-365-defender-portal.md). |
| **Más recursos** | Muestra una lista de más portales y centros, como Azure Active Directory y el portal de cumplimiento Microsoft Purview. <br/><br/> Para más información, consulte [Portales de seguridad y centros de administración de Microsoft](../defender/portals.md). |

> [!TIP]
> Para más información, consulte la [introducción al portal de Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="view-and-manage-incidents--alerts"></a>Visualización y administración de incidentes & alertas

Al iniciar sesión en el portal de Microsoft 365 Defender, asegúrese de ver y administrar los incidentes y las alertas. Comience con la lista **incidentes** . En la imagen siguiente se muestra una lista de incidentes, incluido uno con gravedad alta y otro con gravedad media.

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="Lista de incidentes":::

Seleccione un incidente para ver detalles sobre el incidente. Los detalles incluyen qué alertas se desencadenaron, cuántos dispositivos y usuarios se vieron afectados y otros detalles. En la imagen siguiente se muestra un ejemplo de detalles del incidente.

:::image type="content" source="../../media/mde-p1/single-incident.png" alt-text="Detalles de un incidente" lightbox="../../media/mde-p1/single-incident.png":::

Use las pestañas **Alertas**, **Dispositivos** y **Usuarios** para ver más información, como las alertas que se desencadenaron, los dispositivos afectados y las cuentas de usuario que se vieron afectadas. Desde allí, puede realizar acciones de respuesta manuales, como aislar un dispositivo, detener y poner en cuarentena un archivo, etc.

> [!TIP]
> Para más información sobre el uso de la vista **Incidentes** , consulte [Administración de incidentes](manage-incidents.md).

## <a name="manage-devices"></a>Administrar dispositivos

Para ver y administrar los dispositivos de la organización, en la barra de navegación, en **Puntos de conexión**, seleccione **Inventario de dispositivos**. Verá una lista de dispositivos como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/device-inventory.png" alt-text="Inventario de dispositivos" lightbox="../../media/mde-p1/device-inventory.png":::

La lista incluye los dispositivos para los que se generaron alertas. De forma predeterminada, los datos que se muestran son de los últimos 30 días, con los elementos más recientes enumerados primero. Seleccione un dispositivo para ver más información al respecto. Se abre un panel flotante, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/device-inventory-selecteddevice.png" alt-text="Detalles del dispositivo seleccionados" lightbox="../../media/mde-p1/device-inventory-selecteddevice.png":::

El panel flotante muestra detalles, como las alertas activas del dispositivo, e incluye vínculos para realizar acciones, como aislar un dispositivo.

Si hay alertas activas en el dispositivo, puede verlas en el panel flotante. Seleccione una alerta individual para ver más detalles al respecto. O bien, realice una acción, como **Aislar dispositivo**, para que pueda investigarlo aún más y minimizar el riesgo de infectar otros dispositivos.

> [!TIP]
> Para obtener más información, consulte [Investigar dispositivos en la lista de dispositivos de Defender para punto de conexión](investigate-machines.md).

## <a name="view-reports"></a>Ver informes

En El plan 1 de Defender para punto de conexión, hay varios informes disponibles en el portal de Microsoft 365 Defender. Para acceder a los informes, siga estos pasos:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En la barra de navegación, elija **Informes**.

3. Seleccione un informe en la lista. Verá los tres informes siguientes:

   - Informe de protección contra amenazas
   - Informe de estado del dispositivo
   - Informe de protección web

> [!TIP]
> Para obtener más información, consulte [Informes de protección contra amenazas](threat-protection-reports.md).

### <a name="threat-protection-report"></a>Informe de protección contra amenazas

Para acceder al informe de protección contra amenazas, en el portal de Microsoft 365 Defender, elija **Informes** y, a continuación, elija **Protección contra amenazas**. El informe de Protección contra amenazas muestra tendencias de alertas, estado, categorías y mucho más. Las vistas se organizan en dos columnas: **Tendencias de alerta y** **Estado de alerta**, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/threat-protection-report.png" alt-text="Informe de protección contra amenazas" lightbox="../../media/mde-p1/threat-protection-report.png":::

Desplácese hacia abajo para ver todas las vistas de cada lista.

- De forma predeterminada, las vistas de la columna **Tendencias de alerta** muestran datos de los últimos 30 días, pero puede establecer una vista para mostrar los datos de los últimos tres meses, los últimos seis meses o un intervalo de tiempo personalizado (hasta 180 días).
- Las vistas de la columna **Estado** de alerta son una instantánea del día laborable anterior.

> [!TIP]
> Para más información, consulte [Informe de protección contra amenazas en Defender para punto de conexión](threat-protection-reports.md).

### <a name="device-health-report"></a>Informe de estado del dispositivo

Para acceder al informe de estado del dispositivo, en el portal de Microsoft 365 Defender, elija **Informes** y, a continuación, elija **Estado del dispositivo**. El informe Estado del dispositivo muestra el estado de mantenimiento y el antivirus en todos los dispositivos de la organización. De forma similar al [informe protección contra amenazas](#threat-protection-report), las vistas se organizan en dos columnas: **Tendencias del dispositivo** y **Resumen del dispositivo**, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/device-health-report.png" alt-text="Informe de estado del dispositivo" lightbox="../../media/mde-p1/device-health-report.png":::

Desplácese hacia abajo para ver todas las vistas de cada lista. De forma predeterminada, las vistas de la columna **Tendencias del dispositivo** muestran datos de los últimos 30 días, pero puede cambiar una vista para mostrar los datos de los últimos tres meses, los últimos seis meses o un intervalo de tiempo personalizado (hasta 180 días). Las vistas **de resumen del dispositivo** son instantáneas del día laborable anterior.

> [!TIP]
> Para más información, consulte [Estado del dispositivo](machine-reports.md).

### <a name="web-protection-report"></a>Informe de protección web

Para acceder al informe de estado del dispositivo, en el portal de Microsoft 365 Defender, elija **Informes** y, a continuación, elija **Protección web**. El informe de protección web muestra detecciones a lo largo del tiempo, como direcciones URL malintencionadas e intentos de acceso a direcciones URL bloqueadas, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/web-protection-report.png" alt-text="Informe de protección web" lightbox="../../media/mde-p1/web-protection-report.png":::

Desplácese hacia abajo para ver todas las vistas en el informe de protección web. Algunas vistas incluyen vínculos que permiten ver más detalles, configurar las características de protección contra amenazas e incluso administrar indicadores que sirven como excepciones en Defender para punto de conexión.

> [!TIP]
> Para más información, consulte [Protección web](web-protection-overview.md).

## <a name="next-steps"></a>Pasos siguientes

- [Administrar Microsoft Defender para punto de conexión plan 1](mde-p1-maintenance-operations.md)
- [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md)
