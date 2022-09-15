---
title: Investigación de dispositivos en la lista defender para dispositivos de punto de conexión
description: Investigue los dispositivos afectados revisando alertas, información de conexión de red, agregando etiquetas y grupos de dispositivos y comprobando el estado del servicio.
keywords: devices, tags, groups, endpoint, alerts queue, alerts, device name, domain, last seen, internal IP, active alerts, threat category, filter, sort, review alerts, network, connection, type, password stealer, ransomware, exploit, threat, low severity, service health
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 6b8529338522df41c25dafb30d25b879a5790861
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67709466"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a>Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Investigue los detalles de una alerta que se genera en un dispositivo específico para identificar otros comportamientos o eventos que podrían estar relacionados con la alerta o el posible ámbito de la infracción.

> [!NOTE]
> Como parte del proceso de investigación o respuesta, puede recopilar un paquete de investigación de un dispositivo. A continuación se muestra cómo: [Recopilar el paquete de investigación de los dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).

Puede hacer clic en los dispositivos afectados cada vez que los vea en el portal para abrir un informe detallado sobre ese dispositivo. Los dispositivos afectados se identifican en las siguientes áreas:

- [Lista de dispositivos](investigate-machines.md)
- [Cola de alertas](alerts-queue.md)
- [Panel de operaciones de seguridad](security-operations-dashboard.md)
- Cualquier alerta individual
- Cualquier vista de detalles de archivo individual
- Cualquier dirección IP o vista de detalles de dominio

Al investigar un dispositivo específico, verá lo siguiente:

- Detalles del dispositivo
- Acciones de respuesta
- Pestañas (información general, alertas, escala de tiempo, recomendaciones de seguridad, inventario de software, vulnerabilidades detectadas, KB que faltan)
- Tarjetas (alertas activas, usuarios registrados, evaluación de seguridad, estado de mantenimiento del dispositivo) 
 

:::image type="content" source="images/specific-device.png" alt-text="Vista del dispositivo" lightbox="images/specific-device.png":::

> [!NOTE]
> Debido a restricciones de productos, el perfil del dispositivo no considera todas las pruebas cibernéticas al determinar el período de tiempo "Última vista" (como se ve también en la página del dispositivo).
> Por ejemplo, el valor "Última vez" de la página Dispositivo puede mostrar un período de tiempo anterior aunque haya alertas o datos más recientes disponibles en la escala de tiempo del equipo.

## <a name="device-details"></a>Detalles del dispositivo

La sección de detalles del dispositivo proporciona información como el dominio, el sistema operativo y el estado de mantenimiento del dispositivo. Si hay un paquete de investigación disponible en el dispositivo, verá un vínculo que le permite descargar el paquete.

## <a name="response-actions"></a>Acciones de respuesta

Las acciones de respuesta se ejecutan en la parte superior de una página de dispositivo específica e incluyen:

- Administrar etiquetas
- Aislar el dispositivo
- Restringir ejecución de aplicación
- Ejecutar examen de antivirus
- Recopilar el paquete de investigación
- Iniciar sesión de respuesta dinámica
- Inicio de una investigación automatizada
- Consultar a un experto en amenazas
- Centro de actividades

Puede realizar acciones de respuesta en el Centro de acciones, en una página de dispositivo específica o en una página de archivo específica.

Para obtener más información sobre cómo realizar acciones en un dispositivo, consulte [Acción de respuesta en un dispositivo](respond-machine-alerts.md).

Para obtener más información, vea [Investigar entidades de usuario](investigate-user.md).

## <a name="tabs"></a>Pestañas

Las pestañas proporcionan información de seguridad y prevención de amenazas pertinente relacionada con el dispositivo. En cada pestaña, puede personalizar las columnas que se muestran seleccionando **Personalizar columnas** en la barra situada encima de los encabezados de columna.

### <a name="overview"></a>Información general

En la pestaña **Información general** se muestran las [tarjetas](#cards) para las alertas activas, los usuarios que han iniciado sesión y la evaluación de seguridad.

:::image type="content" source="images/overview-device.png" alt-text="Pestaña Información general en la página del dispositivo" lightbox="images/overview-device.png":::

### <a name="alerts"></a>Alertas

La pestaña **Alertas** proporciona una lista de alertas asociadas al dispositivo. Esta lista es una versión filtrada de la [cola de alertas](alerts-queue.md) y muestra una breve descripción de la alerta, la gravedad (alta, media, baja, informativa), el estado en la cola (nueva, en curso, resuelta), la clasificación (no establecida, la alerta falsa, la alerta verdadera), el estado de investigación, la categoría de alerta, quién está abordando la alerta y la última actividad. También puede filtrar las alertas.

:::image type="content" source="images/alerts-device.png" alt-text="Pestaña de las alertas relacionadas con el dispositivo" lightbox="images/alerts-device.png":::

Cuando se selecciona el icono de círculo situado a la izquierda de una alerta, aparece un control flotante. Desde este panel puede administrar la alerta y ver más detalles, como el número de incidente y los dispositivos relacionados. Se pueden seleccionar varias alertas a la vez.

Para ver una vista de página completa de una alerta, incluido el gráfico de incidentes y el árbol de procesos, seleccione el título de la alerta.

### <a name="timeline"></a>Escala de tiempo

La pestaña **Escala de tiempo** proporciona una vista cronológica de los eventos y las alertas asociadas que se han observado en el dispositivo. Esto puede ayudarle a correlacionar eventos, archivos y direcciones IP en relación con el dispositivo.

La escala de tiempo también permite explorar en profundidad de forma selectiva los eventos que se produjeron en un período de tiempo determinado. Puede ver la secuencia temporal de eventos que se produjeron en un dispositivo durante un período de tiempo seleccionado. Para controlar aún más la vista, puede filtrar por grupos de eventos o personalizar las columnas.

> [!NOTE]
> Para que se muestren los eventos de firewall, deberá habilitar la directiva de auditoría; consulte Conexión de la [plataforma de filtrado de auditoría](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).
>
> El firewall cubre los siguientes eventos:
>
> - [5025](/windows/security/threat-protection/auditing/event-5025) : servicio de firewall detenido
> - [5031](/windows/security/threat-protection/auditing/event-5031) : aplicación bloqueada para no aceptar conexiones entrantes en la red
> - [5157](/windows/security/threat-protection/auditing/event-5157) : conexión bloqueada

:::image type="content" source="images/timeline-device.png" alt-text="Escala de tiempo del dispositivo con eventos" lightbox="images/timeline-device.png":::

Algunas de las funciones incluyen:

- Búsqueda de eventos específicos
  - Use la barra de búsqueda para buscar eventos de escala de tiempo específicos.
- Filtrar eventos desde una fecha específica
  - Seleccione el icono de calendario en la parte superior izquierda de la tabla para mostrar los eventos del último día, semana, 30 días o intervalo personalizado. De forma predeterminada, la escala de tiempo del dispositivo se establece para mostrar los eventos de los últimos 30 días.
  - Use la escala de tiempo para ir a un momento específico en el tiempo resaltando la sección. Las flechas de la escala de tiempo identifican las investigaciones automatizadas
- Exportación de eventos detallados de escala de tiempo del dispositivo
  - Exporte la escala de tiempo del dispositivo para la fecha actual o un intervalo de fechas especificado de hasta siete días.

En la sección **Información adicional** se proporcionan más detalles sobre determinados eventos. Estos detalles varían en función del tipo de evento, por ejemplo:

- Contenido en Application Guard: el evento del explorador web estaba restringido por un contenedor aislado
- Se detectó una amenaza activa: la detección de amenazas se produjo mientras se estaba ejecutando la amenaza.
- Corrección incorrecta: se invocó un intento de corregir la amenaza detectada, pero se produjo un error
- Corrección correcta: la amenaza detectada se ha detenido y limpiado.
- Advertencia omitida por el usuario: el usuario ha descartado y invalidado la advertencia de SmartScreen Windows Defender
- Script sospechoso detectado: se encontró un script potencialmente malintencionado en ejecución
- La categoría de alerta: si el evento condujo a la generación de una alerta, se proporciona la categoría de alerta ("Movimiento lateral", por ejemplo).

#### <a name="event-details"></a>Detalles del evento

Seleccione un evento para ver los detalles pertinentes sobre ese evento. Se muestra un panel para mostrar información general del evento. Cuando sea aplicable y los datos estén disponibles, también se muestra un gráfico que muestra las entidades relacionadas y sus relaciones.

Para inspeccionar aún más el evento y los eventos relacionados, puede ejecutar rápidamente una consulta de [búsqueda avanzada](advanced-hunting-overview.md) seleccionando **Buscar eventos relacionados**. La consulta devolverá el evento seleccionado y la lista de otros eventos que se produjeron aproximadamente al mismo tiempo en el mismo punto de conexión.

:::image type="content" source="images/event-details.png" alt-text="Panel de detalles del evento" lightbox="images/event-details.png":::

### <a name="security-recommendations"></a>Recomendaciones de seguridad

**Las recomendaciones de seguridad** se generan a partir de la funcionalidad [de administración de vulnerabilidades](tvm-dashboard-insights.md) de Microsoft Defender para punto de conexión. Al seleccionar una recomendación, se mostrará un panel en el que puede ver detalles pertinentes, como la descripción de la recomendación y los posibles riesgos asociados a no aplicarla. Consulte [Recomendación de seguridad](tvm-security-recommendation.md) para obtener más información.

:::image type="content" source="images/security-recommendations-device.png" alt-text="Pestaña Recomendaciones de seguridad" lightbox="images/security-recommendations-device.png":::

### <a name="software-inventory"></a>Inventario de software

La pestaña **Inventario de** software le permite ver el software en el dispositivo, junto con cualquier debilidad o amenaza. Al seleccionar el nombre del software, se le llevará a la página de detalles del software, donde podrá ver recomendaciones de seguridad, vulnerabilidades detectadas, dispositivos instalados y distribución de versiones. Consulte [Inventario de software](tvm-software-inventory.md) para obtener más información.

:::image type="content" source="images/software-inventory-device.png" alt-text="Pestaña Inventario de software" lightbox="images/software-inventory-device.png":::

### <a name="discovered-vulnerabilities"></a>Vulnerabilidades detectadas

**La pestaña Vulnerabilidades detectadas** muestra el nombre, la gravedad y la información sobre amenazas de las vulnerabilidades detectadas en el dispositivo. Al seleccionar vulnerabilidades específicas, se mostrará una descripción y detalles.

:::image type="content" source="images/discovered-vulnerabilities-device.png" alt-text="Pestaña Vulnerabilidades detectadas" lightbox="images/discovered-vulnerabilities-device.png":::

### <a name="missing-kbs"></a>KB que faltan
En la pestaña **Missing KBs (Faltan KBs** ) se enumeran las actualizaciones de seguridad que faltan para el dispositivo.

:::image type="content" source="images/missing-kbs-device.png" alt-text="Pestaña KBs que faltan" lightbox="images/missing-kbs-device.png":::

## <a name="cards"></a>Tarjetas

### <a name="active-alerts"></a>Alertas activas

La tarjeta **Azure Advanced Threat Protection** mostrará información general de alto nivel de las alertas relacionadas con el dispositivo y su nivel de riesgo, si ha habilitado la característica Microsoft Defender for Identity y hay alertas activas. Hay más información disponible en la exploración en profundidad "Alertas".

:::image type="content" source="images/risk-level-small.png" alt-text="La tarjeta de alertas activas" lightbox="images/risk-level-small.png":::

> [!NOTE]
> Tendrá que habilitar la integración en Microsoft Defender for Identity y Defender para punto de conexión para usar esta característica. En Defender para punto de conexión, puede habilitar esta característica en características avanzadas. Para obtener más información sobre cómo habilitar características avanzadas, consulte [Activar características avanzadas](advanced-features.md).

### <a name="logged-on-users"></a>Usuarios que han iniciado sesión

**La tarjeta Usuarios con sesión** iniciada muestra cuántos usuarios han iniciado sesión en los últimos 30 días, junto con los usuarios más y menos frecuentes. Al seleccionar el vínculo "Ver todos los usuarios", se abre el panel de detalles, que muestra información como el tipo de usuario, el tipo de inicio de sesión y la primera y última vez que se vio al usuario. Para obtener más información, vea [Investigar entidades de usuario](investigate-user.md).

:::image type="content" source="images/logged-on-users.png" alt-text="Panel de detalles del usuario" lightbox="images/logged-on-users.png":::

> [!NOTE]
> El valor de usuario "Más frecuente" solo se calcula en función de la evidencia de los usuarios que iniciaron sesión correctamente de forma interactiva.
> Sin embargo, el panel lateral "Todos los usuarios" calcula todo tipo de inicios de sesión de usuario, por lo que se espera que vea usuarios más frecuentes en el panel lateral, dado que es posible que esos usuarios no sean interactivos.

### <a name="security-assessments"></a>Evaluaciones de seguridad

La tarjeta **Evaluaciones de seguridad** muestra el nivel de exposición general, las recomendaciones de seguridad, el software instalado y las vulnerabilidades detectadas. El nivel de exposición de un dispositivo viene determinado por el impacto acumulativo de sus recomendaciones de seguridad pendientes.

:::image type="content" source="images/security-assessments.png" alt-text="La tarjeta de evaluaciones de seguridad" lightbox="images/security-assessments.png":::

### <a name="device-health-status"></a>Estado de mantenimiento del dispositivo

La tarjeta **estado de mantenimiento** del dispositivo muestra un informe de estado resumido para el dispositivo específico. Uno de los siguientes mensajes se muestra en la parte superior de la tarjeta para indicar el estado general del dispositivo (en orden de mayor a menor prioridad):

- Antivirus de Defender no activo
- La inteligencia de seguridad no está actualizada
- El motor no está actualizado
- Error en el examen rápido
- Error en el examen completo
- La plataforma no está actualizada
- El estado de actualización de inteligencia de seguridad es desconocido
- El estado de actualización del motor es desconocido
- El estado del examen rápido es desconocido
- El estado del examen completo es desconocido
- El estado de actualización de la plataforma es desconocido
- El dispositivo está actualizado
- Estado no disponible para macOS & Linux

Otra información de la tarjeta incluye: el último examen completo, el último examen rápido, la versión de actualización de inteligencia de seguridad, la versión de actualización del motor, la versión de actualización de la plataforma y el modo Antivirus de Defender. 

Tenga en cuenta que un círculo gris indica que los datos son desconocidos. 

> [!NOTE]
> El mensaje de estado general para dispositivos macOS y Linux aparece actualmente como "Estado no disponible para macOS & Linux". Actualmente, el resumen de estado solo está disponible para dispositivos Windows. Toda la otra información de la tabla está actualizada para mostrar los estados individuales de cada señal de estado de dispositivo para todas las plataformas admitidas. 

Para obtener una vista detallada del informe de estado del dispositivo, puede ir a **Informes > estado de dispositivos**. Para obtener más información, consulte [Informe de cumplimiento y estado del dispositivo en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/machine-reports). 

:::image type="content" source="images/device-health-status.png"  alt-text="Tarjeta de estado de mantenimiento del dispositivo" lightbox="images/device-health-status.png":::

## <a name="related-topics"></a>Temas relacionados

- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de un archivo asociado a una alerta de Defender para punto de conexión](investigate-files.md)
- [Investigación de una dirección IP asociada a una alerta de Defender para punto de conexión](investigate-ip.md)
- [Investigación de un dominio asociado a una alerta de Defender para punto de conexión](investigate-domain.md)
- [Investigación de una cuenta de usuario en Defender para punto de conexión](investigate-user.md)
- [Recomendación de seguridad](tvm-security-recommendation.md)
- [Inventario de software](tvm-software-inventory.md)