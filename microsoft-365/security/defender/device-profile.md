---
title: Perfil de dispositivo en Microsoft 365 de seguridad
description: Ver los niveles de riesgo y exposición de un dispositivo de la organización. Analiza las amenazas pasadas y actuales y protege el dispositivo con las actualizaciones más recientes.
keywords: security, malware, Microsoft 365, M365, Microsoft 365 Defender, security center, Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, device page, device profile, machine page, machine profile, machine profile
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 8e2788fd9163a27b41bd3788facf5fc9623b0543
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935670"
---
# <a name="device-profile-page"></a>Página de perfil de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


El Microsoft 365 de seguridad le proporciona páginas de perfil de dispositivo para que pueda evaluar rápidamente el estado y el estado de los dispositivos de la red.

> [!IMPORTANT]
> La página de perfil de dispositivo puede parecer ligeramente diferente, en función de si el dispositivo está inscrito en Microsoft Defender para Endpoint, Microsoft Defender para Identity o en ambos.

Si el dispositivo está inscrito en Microsoft Defender para Endpoint, también puedes usar la página de perfil de dispositivo para realizar algunas tareas de seguridad comunes.

## <a name="navigating-the-device-profile-page"></a>Navegar por la página de perfil de dispositivo

La página de perfil se divide en varias secciones generales.

![Imagen de la página de perfil de dispositivo con (1) área de pestaña (2) Barra lateral y (3) Acciones resaltadas en rojo](../../media/mtp-device-profile/hybrid-device-overall.png)

En la barra lateral (1) se enumeran los detalles básicos sobre el dispositivo.

El área de contenido principal (2) contiene pestañas que puedes alternar para ver diferentes tipos de información sobre el dispositivo.

Si el dispositivo está inscrito en Microsoft Defender para Endpoint, también verás una lista de acciones de respuesta (3). Las acciones de respuesta permiten realizar tareas comunes relacionadas con la seguridad.

## <a name="sidebar"></a>Barra lateral

Junto al área de contenido principal de la página de perfil de dispositivo se encuentra la barra lateral.

![Imagen de la pestaña de la barra lateral para el perfil del dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

En la barra lateral se muestra el nombre completo y el nivel de exposición del dispositivo. También proporciona información básica importante en subsecciones pequeñas que se pueden alternar abiertas o cerradas, como:

* **Etiquetas:** cualquier Microsoft Defender para endpoint, Microsoft Defender para Identity o etiquetas personalizadas asociadas con el dispositivo. Las etiquetas de Microsoft Defender para Identity no son editables.
* **Información de seguridad:** abre incidentes y alertas activas. Los dispositivos inscritos en Microsoft Defender para Endpoint también mostrarán el nivel de exposición y el nivel de riesgo.

> [!TIP]
> El nivel de exposición se refiere a cuánto cumple el dispositivo con las recomendaciones de seguridad, mientras que el nivel de riesgo se calcula en función de una serie de factores, incluidos los tipos y la gravedad de las alertas activas.

* **Detalles del dispositivo:** dominio, sistema operativo, marca de tiempo para cuando se vio por primera vez el dispositivo, direcciones IP, recursos. Los dispositivos inscritos en Microsoft Defender para endpoint también muestran el estado de mantenimiento. Los dispositivos inscritos en Microsoft Defender para Identity mostrarán el nombre SAM y una marca de tiempo para cuando se creó el dispositivo por primera vez.
* **Actividad de red:** marcas de tiempo por primera vez y por última vez que se vio el dispositivo en la red.
* **Datos de directorio** (*solo para dispositivos* inscritos en Microsoft Defender para identidad ) : marcas [UAC,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN y](/windows/win32/ad/service-principal-names)pertenencias a grupos.

## <a name="response-actions"></a>Acciones de respuesta

Las acciones de respuesta ofrecen una forma rápida de defenderse y analizar las amenazas.

![Imagen de la barra de acciones para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Las acciones de](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) respuesta solo están disponibles si el dispositivo está inscrito en Microsoft Defender para endpoint.
> * Los dispositivos inscritos en Microsoft Defender para Endpoint pueden mostrar diferentes números de acciones de respuesta, según el sistema operativo y el número de versión del dispositivo.

Las acciones disponibles en la página de perfil de dispositivo incluyen:

* **Administrar etiquetas:** actualiza las etiquetas personalizadas que has aplicado a este dispositivo.
* **Aislar dispositivo:** aísla el dispositivo de la red de su organización mientras lo mantiene conectado a Microsoft Defender para Endpoint. Puedes elegir permitir que Outlook, Teams y Skype Empresarial se ejecuten mientras el dispositivo está aislado, con fines de comunicación.
* **Centro de acciones:** ver el estado de las acciones enviadas. Solo está disponible si ya se ha seleccionado otra acción.
* **Restringir la ejecución de** aplicaciones: impide que se ejecuten aplicaciones que no están firmadas por Microsoft.
* **Ejecutar examen antivirus:** actualiza Antivirus de Windows Defender definiciones e inmediatamente ejecuta un examen antivirus. Elija entre Examen rápido o Examen completo.
* **Recopilar paquete de investigación:** recopila información sobre el dispositivo. Cuando se complete la investigación, puede descargarla.
* **Iniciar sesión de respuesta en directo:** carga un shell remoto en el dispositivo para investigaciones [de seguridad en profundidad.](/microsoft-365/security/defender-endpoint/live-response)
* **Iniciar investigación automatizada:** investiga y corrige automáticamente [las amenazas.](../office-365-security/office-365-air.md) Aunque puede activar manualmente las investigaciones automatizadas para que se ejecuten desde esta [página,](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) determinadas directivas de alerta desencadenan investigaciones automáticas por sí solas.
* **Centro de acciones:** muestra información sobre las acciones de respuesta que se están ejecutando actualmente.

## <a name="tabs-section"></a>Sección Tabulaciones

Las pestañas de perfil de dispositivo te permiten alternar entre una introducción a los detalles de seguridad sobre el dispositivo y tablas que contienen una lista de alertas.

Los dispositivos inscritos en Microsoft Defender para endpoint también mostrarán pestañas que incluyen una escala de tiempo, una lista de recomendaciones de seguridad, un inventario de software, una lista de vulnerabilidades detectadas y KBs ausentes (actualizaciones de seguridad).

### <a name="overview-tab"></a>Ficha Información general

La pestaña predeterminada es **Overview**. Proporciona un vistazo rápido al hecho de seguridad más importante sobre el dispositivo.

![Imagen de la pestaña información general del perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Aquí puedes ver rápidamente las alertas activas del dispositivo y los usuarios que han iniciado sesión actualmente.

Si el dispositivo está inscrito en Microsoft Defender para Endpoint, también verás el nivel de riesgo del dispositivo y los datos disponibles en las evaluaciones de seguridad. Las evaluaciones de seguridad describen el nivel de exposición del dispositivo, proporcionan recomendaciones de seguridad y enumeran el software afectado y las vulnerabilidades detectadas.

### <a name="alerts-tab"></a>Ficha Alertas

La **pestaña** Alertas contiene una lista de alertas que se han elevado en el dispositivo, tanto de Microsoft Defender para Identity como de Microsoft Defender para endpoint.

![Imagen de la pestaña alertas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Puede personalizar el número de elementos que se muestran, así como las columnas que se muestran para cada elemento. El comportamiento predeterminado es enumerar treinta elementos por página.

Las columnas de esta pestaña incluyen información sobre la gravedad de la amenaza que desencadenó la alerta, así como el estado, el estado de investigación y a quién se asignó la alerta.

La *columna entidades afectadas* hace referencia al dispositivo (entidad) cuyo perfil está viendo actualmente, además de cualquier otro dispositivo de la red que se vea afectado.

Si selecciona un elemento de esta lista, se abrirá un menú desplegable que contiene aún más información sobre la alerta seleccionada.

Esta lista se puede filtrar por gravedad, estado o a quién se ha asignado la alerta.

### <a name="timeline-tab"></a>Pestaña Escala de tiempo

La **pestaña Escala** de tiempo incluye un gráfico cronológico interactivo de todos los eventos que se han producido en el dispositivo. Al mover el área resaltada del gráfico a la izquierda o a la derecha, puede ver eventos durante diferentes períodos de tiempo. También puede elegir un intervalo personalizado de fechas en el menú desplegable entre el gráfico interactivo y la lista de eventos.

Debajo del gráfico hay una lista de eventos para el intervalo de fechas seleccionado.

![Imagen de la pestaña escala de tiempo para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

El número de elementos que se muestran y las columnas de la lista se pueden personalizar. Las columnas predeterminadas muestran la hora del evento, el usuario activo, el tipo de acción, las entidades (procesos) y la información adicional sobre el evento.

Al seleccionar un elemento de esta lista, se abrirá un control desplegable que muestra un gráfico de entidades de evento, que muestra los procesos primarios y secundarios implicados en el evento.

La lista se puede filtrar por el tipo específico de evento; por ejemplo, eventos del Registro o Eventos de pantalla inteligente.

La lista también se puede exportar a un archivo CSV, para su descarga. Aunque el archivo no está limitado por el número de eventos, el intervalo de tiempo máximo que puede elegir exportar es de siete días.

### <a name="security-recommendations-tab"></a>Pestaña Recomendaciones de seguridad

En **la pestaña Recomendaciones de** seguridad se enumeran las acciones que puedes realizar para proteger el dispositivo. Si selecciona un elemento en esta lista, se abrirá un menú desplegable donde podrá obtener instrucciones sobre cómo aplicar la recomendación.

![Imagen de la pestaña recomendaciones de seguridad para el perfil del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Al igual que con las pestañas anteriores, se puede personalizar el número de elementos que se muestran por página, así como las columnas visibles.

La vista predeterminada incluye columnas que detallan las debilidades de seguridad abordadas, la amenaza asociada, el componente relacionado o el software afectado por la amenaza, y mucho más. Los elementos se pueden filtrar por el estado de la recomendación.

### <a name="software-inventory"></a>Inventario de software

La **pestaña Inventario de** software muestra el software instalado en el dispositivo.

![Imagen de la pestaña de inventario de software para el perfil del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

La vista predeterminada muestra el proveedor de software, el número de versión instalada, el número de debilidades de software conocidas, las perspectivas de amenazas, el código del producto y las etiquetas. El número de elementos que se muestran y las columnas que se muestran se pueden personalizar.

Al seleccionar un elemento de esta lista, se abre un desplegable que contiene más detalles sobre el software seleccionado, así como la ruta de acceso y la marca de tiempo de la última vez que se encontró el software.

Esta lista se puede filtrar por código de producto.

### <a name="discovered-vulnerabilities-tab"></a>Pestaña Vulnerabilidades detectadas

En **la pestaña Vulnerabilidades detectadas** se enumeran las vulnerabilidades y vulnerabilidades comunes (CVEs) que pueden afectar al dispositivo.

![Imagen de la pestaña vulnerabilidades detectadas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

La vista predeterminada enumera la gravedad de CVE, la puntuación de vulnerabilidad común (CVS), el software relacionado con CVE, cuando se publicó la CVE, cuando se actualizó por última vez la CVE y las amenazas asociadas con la CVE.

Al igual que con las pestañas anteriores, se puede personalizar el número de elementos mostrados y las columnas visibles.

Si selecciona un elemento de esta lista, se abrirá un desplegable que describe la CVE.

### <a name="missing-kbs"></a>Faltan KBs

En **la pestaña KBs que** faltan se enumeran las actualizaciones de Microsoft que aún no se han aplicado al dispositivo. Los "KBs" en cuestión son [artículos de Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que describen estas actualizaciones; por ejemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Imagen de la pestaña kbs que falta para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

La vista predeterminada enumera el boletín que contiene las actualizaciones, la versión del sistema operativo, los productos afectados, las CVE dirigidas, el número KB y las etiquetas.

El número de elementos que se muestran por página y las columnas que se muestran se pueden personalizar.

Al seleccionar un elemento, se abrirá un desplegable que vincula a la actualización.

## <a name="related-topics"></a>Temas relacionados

* [Microsoft 365 Introducción al defensor](microsoft-365-defender.md)
* [Activar Microsoft 365 Defender](m365d-enable.md)
* [Investigar entidades en dispositivos con respuesta en directo](../defender-endpoint/live-response.md)
* [Investigación y respuesta automatizadas (AIR) en Office 365](../office-365-security/office-365-air.md)
