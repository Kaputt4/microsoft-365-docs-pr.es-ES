---
title: Perfil de dispositivo en el portal de seguridad de Microsoft 365
description: Vea los niveles de riesgo y exposición de un dispositivo de su organización. Analice las amenazas pasadas y presentes y proteja el dispositivo con las actualizaciones más recientes.
keywords: seguridad, malware, Microsoft 365, M365, Microsoft 365 Defender, security center, Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Identity, página de dispositivo, perfil de dispositivo, página de equipo, perfil de equipo
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: dansimp
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: b701d93aefcab19ff352830815c7894fc062140a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466973"
---
# <a name="device-profile-page"></a>Página perfil de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


El portal de seguridad de Microsoft 365 proporciona páginas de perfil de dispositivo para que pueda evaluar rápidamente el estado y el estado de los dispositivos de la red.

> [!IMPORTANT]
> La página de perfil del dispositivo puede parecer ligeramente diferente, dependiendo de si el dispositivo está inscrito en Microsoft Defender para punto de conexión, Microsoft Defender for Identity o ambos.

Si el dispositivo está inscrito en Microsoft Defender para punto de conexión, también puede usar la página de perfil del dispositivo para realizar algunas tareas de seguridad comunes.

## <a name="navigating-the-device-profile-page"></a>Navegación por la página del perfil del dispositivo

La página de perfil se divide en varias secciones amplias.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-overall.png" alt-text="Página Perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-overall.png":::

La barra lateral (1) muestra detalles básicos sobre el dispositivo.

El área de contenido principal (2) contiene pestañas que puede alternar para ver diferentes tipos de información sobre el dispositivo.

Si el dispositivo está inscrito en Microsoft Defender para punto de conexión, también verá una lista de acciones de respuesta (3). Las acciones de respuesta permiten realizar tareas comunes relacionadas con la seguridad.

## <a name="sidebar"></a>Barra lateral

Junto al área de contenido principal de la página de perfil del dispositivo se encuentra la barra lateral.

:::image type="content" source="../../media/mtp-device-profile/azure-atp-only-device-sidebar.png" alt-text="Pestaña Barra lateral del perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/azure-atp-only-device-sidebar.png":::

La barra lateral muestra el nombre completo del dispositivo y el nivel de exposición. También proporciona información básica importante en subsecciones pequeñas que se pueden alternar abiertas o cerradas, como:

* **Etiquetas**: cualquier etiqueta Microsoft Defender para punto de conexión, Microsoft Defender for Identity o personalizada asociada al dispositivo. Las etiquetas de Microsoft Defender for Identity no son editables.
* **Información de seguridad** : abra incidentes y alertas activas. Los dispositivos inscritos en Microsoft Defender para punto de conexión también mostrarán el nivel de exposición y el nivel de riesgo.

> [!TIP]
> El nivel de exposición está relacionado con cuánto el dispositivo cumple con las recomendaciones de seguridad, mientras que el nivel de riesgo se calcula en función de una serie de factores, incluidos los tipos y la gravedad de las alertas activas.

* **Detalles del dispositivo** : dominio, sistema operativo, marca de tiempo para la primera vez que se vio el dispositivo, direcciones IP, recursos. Los dispositivos inscritos en Microsoft Defender para punto de conexión también muestran el estado de mantenimiento. Los dispositivos inscritos en Microsoft Defender for Identity mostrarán el nombre SAM y una marca de tiempo para la primera vez que se creó el dispositivo.
* **Actividad de red** : marcas de tiempo por primera vez y la última vez que se vio el dispositivo en la red.
* **Datos de directorio** (*solo para dispositivos inscritos en Microsoft Defender for Identity*): marcas [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview), [SPN y pertenencias](/windows/win32/ad/service-principal-names) a grupos.

## <a name="response-actions"></a>Acciones de respuesta

Las acciones de respuesta ofrecen una manera rápida de defenderse y analizar las amenazas.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-long-action-bar.png" alt-text="Barra de acciones para el perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-long-action-bar.png":::

> [!IMPORTANT]
> * [Las acciones de respuesta](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) solo están disponibles si el dispositivo está inscrito en Microsoft Defender para punto de conexión.
> * Los dispositivos inscritos en Microsoft Defender para punto de conexión pueden mostrar diferentes números de acciones de respuesta, en función del sistema operativo y el número de versión del dispositivo.

Entre las acciones disponibles en la página del perfil del dispositivo se incluyen:

* **Administrar etiquetas**: Novedades etiquetas personalizadas que ha aplicado a este dispositivo.
* **Aislar dispositivo**: aísla el dispositivo de la red de la organización mientras lo mantiene conectado a Microsoft Defender para punto de conexión. Puede optar por permitir que Outlook, Teams y Skype Empresarial se ejecuten mientras el dispositivo está aislado, con fines de comunicación.
* **Centro de acciones** : vea el estado de las acciones enviadas. Solo está disponible si ya se ha seleccionado otra acción.
* **Restringir la ejecución** de aplicaciones: impide que se ejecuten las aplicaciones que no están firmadas por Microsoft.
* **Ejecución del examen antivirus**: Novedades definiciones de Antivirus de Microsoft Defender y ejecuta inmediatamente un examen antivirus. Elija entre Examen rápido o Examen completo.
* **Recopilar paquete de investigación** : recopila información sobre el dispositivo. Una vez completada la investigación, puede descargarla.
* **Iniciar sesión de respuesta** activa: carga un shell remoto en el dispositivo para [realizar investigaciones de seguridad detalladas](/microsoft-365/security/defender-endpoint/live-response).
* **Iniciar una investigación automatizada** : [investiga y corrige automáticamente las amenazas](../office-365-security/office-365-air.md). Aunque puede desencadenar manualmente investigaciones automatizadas para que se ejecuten desde esta página, [ciertas directivas de alerta](../../compliance/alert-policies.md#default-alert-policies) desencadenan investigaciones automáticas por sí solas.
* **Centro de acciones** : muestra información sobre las acciones de respuesta que se están ejecutando actualmente.

## <a name="tabs-section"></a>Sección Tabulaciones

Las pestañas de perfil de dispositivo le permiten alternar a través de una introducción a los detalles de seguridad sobre el dispositivo y las tablas que contienen una lista de alertas.

Los dispositivos inscritos en Microsoft Defender para punto de conexión también mostrarán pestañas que incluyen una escala de tiempo, una lista de recomendaciones de seguridad, un inventario de software, una lista de vulnerabilidades detectadas y los KB que faltan (actualizaciones de seguridad).

### <a name="overview-tab"></a>‎Pestaña da Información general

La pestaña predeterminada es **Información general**. Proporciona un vistazo rápido al hecho de seguridad más importante sobre el dispositivo.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-overview.png" alt-text="Pestaña Información general del perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-tab-overview.png":::

Aquí puede ver rápidamente las alertas activas del dispositivo y cualquier usuario que haya iniciado sesión actualmente.

Si el dispositivo está inscrito en Microsoft Defender para punto de conexión, también verá el nivel de riesgo del dispositivo y los datos disponibles en las evaluaciones de seguridad. Las evaluaciones de seguridad describen el nivel de exposición del dispositivo, proporcionan recomendaciones de seguridad y enumeran el software afectado y las vulnerabilidades detectadas.

### <a name="alerts-tab"></a>Ficha Alertas

La pestaña **Alertas** contiene una lista de alertas que se han generado en el dispositivo, tanto de Microsoft Defender for Identity como de Microsoft Defender para punto de conexión.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-alerts.png" alt-text="Pestaña Alertas del perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-tab-alerts.png":::

Puede personalizar el número de elementos mostrados, así como las columnas que se muestran para cada elemento. El comportamiento predeterminado es enumerar treinta elementos por página.

Las columnas de esta pestaña incluyen información sobre la gravedad de la amenaza que desencadenó la alerta, así como el estado, el estado de investigación y a quién se ha asignado la alerta.

La columna *de entidades afectadas* hace referencia al dispositivo (entidad) cuyo perfil está viendo actualmente, además de cualquier otro dispositivo de la red que se vea afectado.

Al seleccionar un elemento de esta lista, se abrirá un control flotante que contiene aún más información sobre la alerta seleccionada.

Esta lista se puede filtrar por gravedad, estado o a quién se ha asignado la alerta.

### <a name="timeline-tab"></a>Pestaña Escala de tiempo

La pestaña **Escala de tiempo** incluye un gráfico interactivo y cronológico de todos los eventos generados en el dispositivo. Al mover el área resaltada del gráfico a la izquierda o a la derecha, puede ver eventos durante diferentes períodos de tiempo. También puede elegir un intervalo personalizado de fechas en el menú desplegable entre el gráfico interactivo y la lista de eventos.

Debajo del gráfico hay una lista de eventos para el intervalo de fechas seleccionado.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-timeline.png" alt-text="Pestaña Escala de tiempo del perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-tab-timeline.png":::

El número de elementos mostrados y las columnas de la lista se pueden personalizar. Las columnas predeterminadas enumeran la hora del evento, el usuario activo, el tipo de acción, las entidades (procesos) y la información adicional sobre el evento.

Al seleccionar un elemento de esta lista, se abrirá un control flotante que muestra un gráfico De entidades de eventos, que muestra los procesos primarios y secundarios implicados en el evento.

La lista se puede filtrar por el tipo específico de evento; por ejemplo, eventos del Registro o eventos de pantalla inteligente.

La lista también se puede exportar a un archivo CSV para su descarga. Aunque el archivo no está limitado por el número de eventos, el intervalo de tiempo máximo que puede elegir exportar es de siete días.

### <a name="security-recommendations-tab"></a>Pestaña Recomendaciones de seguridad

En la pestaña **Recomendaciones de seguridad** se enumeran las acciones que puede realizar para proteger el dispositivo. Al seleccionar un elemento de esta lista, se abrirá un control flotante en el que puede obtener instrucciones sobre cómo aplicar la recomendación.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-security-recs.png" alt-text="Pestaña Recomendaciones de seguridad para el perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-tab-security-recs.png":::

Al igual que con las pestañas anteriores, se puede personalizar el número de elementos mostrados por página, así como las columnas visibles.

La vista predeterminada incluye columnas que detallan los puntos débiles de seguridad abordados, la amenaza asociada, el componente o el software relacionados afectados por la amenaza, etc. Los elementos se pueden filtrar por el estado de la recomendación.

### <a name="software-inventory"></a>Inventario de software

La pestaña **Inventario de** software muestra el software instalado en el dispositivo.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png" alt-text="Pestaña Inventario de software del perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png":::

La vista predeterminada muestra el proveedor de software, el número de versión instalado, el número de puntos débiles de software conocidos, la información sobre amenazas, el código de producto y las etiquetas. El número de elementos mostrados y las columnas que se muestran se pueden personalizar.

Al seleccionar un elemento de esta lista, se abre un control flotante que contiene más detalles sobre el software seleccionado, así como la ruta de acceso y la marca de tiempo de la última vez que se encontró el software.

Esta lista se puede filtrar por código de producto.

### <a name="discovered-vulnerabilities-tab"></a>Pestaña Vulnerabilidades detectadas

En la pestaña **Vulnerabilidades detectadas se** enumeran las vulnerabilidades comunes y vulnerabilidades de seguridad (CVE) que pueden afectar al dispositivo.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png" alt-text="Pestaña Vulnerabilidades detectadas del perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png":::

La vista predeterminada enumera la gravedad del CVE, la puntuación de vulnerabilidad común (CVS), el software relacionado con el CVE, cuando se publicó el CVE, la última vez que se actualizó el CVE y las amenazas asociadas al CVE.

Al igual que con las pestañas anteriores, se puede personalizar el número de elementos que se muestran y las columnas visibles.

Al seleccionar un elemento de esta lista, se abrirá un control flotante que describe el CVE.

### <a name="missing-kbs"></a>KB que faltan

En la pestaña **Missing KBs (Faltan KBs**) se enumeran los Novedades de Microsoft que aún no se han aplicado al dispositivo. Los "KB" en cuestión son [artículos de Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que describen estas actualizaciones; por ejemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG" alt-text="Pestaña KB que falta para el perfil de dispositivo en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG":::

En la vista predeterminada se muestra el boletín que contiene las actualizaciones, la versión del sistema operativo, los productos afectados, los CVE direccionados, el número de KB y las etiquetas.

Se puede personalizar el número de elementos mostrados por página y las columnas que se muestran.

Al seleccionar un elemento, se abrirá un control flotante que vincula a la actualización.

## <a name="related-topics"></a>Temas relacionados

* [introducción a Microsoft 365 Defender](microsoft-365-defender.md)
* [Activar Microsoft 365 Defender](m365d-enable.md)
* [Investigación de entidades en dispositivos mediante respuesta en directo](../defender-endpoint/live-response.md)
* [Investigación y respuesta automatizadas (AIR) en Office 365](../office-365-security/office-365-air.md)
