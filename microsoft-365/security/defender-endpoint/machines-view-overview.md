---
title: Inventario de dispositivos
description: Obtenga información sobre las características disponibles que puede usar en la lista Dispositivos, como ordenar, filtrar y exportar la lista para mejorar las investigaciones.
keywords: sort, filter, export, csv, device name, domain, last seen, internal IP, health state, active alerts, active malware detections, threat category, review alerts, network, connection, malware, type, password stealer, ransomware, exploit, threat, general malware, unwanted software
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 81ff80776d3b12e4ec90d6d2c2473389686ae9c9
ms.sourcegitcommit: bc35c7826e3403f259725ac72cca5bafd36aa56a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66554475"
---
# <a name="device-inventory"></a>Inventario de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-machinesview-abovefoldlink)

El **inventario de** dispositivos muestra una lista de los dispositivos de la red donde se generaron alertas. De forma predeterminada, la cola muestra los dispositivos vistos en los últimos 30 días.

De un vistazo verá información como dominio, nivel de riesgo, plataforma del sistema operativo y otros detalles para facilitar la identificación de los dispositivos más en riesgo.

> [!NOTE]
> El inventario de dispositivos está disponible en diferentes servicios de Microsoft 365 Defender. La información disponible para usted variará en función de su licencia. Obtendrá el conjunto más completo de funcionalidades al usar [Microsoft Defender para punto de conexión plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037).

Hay varias opciones entre las que puede elegir para personalizar la vista de lista de dispositivos. En la navegación superior, puede hacer lo siguiente:

- Agregar o quitar columnas
- Exportación de toda la lista en formato CSV
- Seleccionar el número de elementos que se van a mostrar por página
- Aplicar filtros

Durante el proceso de incorporación, la **lista Dispositivos** se rellena gradualmente con dispositivos a medida que comienzan a notificar los datos del sensor. Use esta vista para realizar un seguimiento de los puntos de conexión incorporados a medida que se conecten o descargue la lista completa de puntos de conexión como un archivo CSV para el análisis sin conexión.

> [!NOTE]
> Si exporta la lista de dispositivos, contendrá todos los dispositivos de la organización. La descarga puede tardar mucho tiempo, en función del tamaño de su organización. La exportación de la lista en formato CSV muestra los datos de forma no filtrada. El archivo CSV incluirá todos los dispositivos de la organización, independientemente de los filtros aplicados en la propia vista.

:::image type="content" source="images/device-inventory.png" alt-text="La lista de dispositivos" lightbox="images/device-inventory.png":::

## <a name="sort-and-filter-the-device-list"></a>Ordenar y filtrar la lista de dispositivos

Puede aplicar los siguientes filtros para limitar la lista de alertas y obtener una vista más centrada.

### <a name="device-name"></a>Nombre del dispositivo

Durante el proceso de incorporación de Microsoft Defender para punto de conexión, los dispositivos incorporados a MDE se rellenan gradualmente en el inventario de dispositivos a medida que comienzan a notificar los datos del sensor. A continuación, los dispositivos que se detectan en la red a través del proceso de detección de dispositivos rellenan el inventario de dispositivos. El inventario de dispositivos tiene tres pestañas que enumeran los dispositivos por:

- **Equipos y dispositivos móviles**: puntos de conexión empresariales (estaciones de trabajo, servidores y dispositivos móviles)
- **Dispositivos de red**: dispositivos como enrutadores y conmutadores
- **Dispositivos IoT**: dispositivos como impresoras y cámaras

## <a name="navigate-to-the-device-inventory-page"></a>Vaya a la página Inventario de dispositivos

Para acceder a la página de inventario de dispositivos, seleccione **Inventario** de dispositivos en el menú de navegación **Puntos de conexión** del [portal de Microsoft 365 Defender](/microsoft-365/security/defender-business/mdb-get-started).

## <a name="device-inventory-overview"></a>Información general del inventario de dispositivos

El inventario de dispositivos se abre en la pestaña **Equipos y dispositivos móviles** . De un vistazo verá información como el nombre del dispositivo, el dominio, el nivel de riesgo, el nivel de exposición, la plataforma del sistema operativo, el estado de incorporación, el estado de mantenimiento del sensor y otros detalles para facilitar la identificación de los dispositivos más en riesgo.

Use la columna **Estado de incorporación** para ordenar y filtrar por dispositivos detectados y los que ya están incorporados a Microsoft Defender para punto de conexión.

![Imagen de la lista de dispositivos con lista de dispositivos.](images/device-inventory.png)

En las pestañas **Dispositivos de red** y **Dispositivos ioT** , también verá información como proveedor, modelo y tipo de dispositivo:

![Imagen de la lista de dispositivos de red.](images/device-inventory-networkdevices.png)

En la parte superior de cada pestaña de inventario de dispositivos, puede ver el número total de dispositivos, el número de dispositivos que aún no están incorporados y el número de dispositivos que se han identificado como un mayor riesgo para su organización. Puede usar esta información para ayudarle a priorizar los dispositivos para mejorar la posición de seguridad.

El recuento **de dispositivos recién detectados** para los dispositivos de red y las pestañas de dispositivos IoT muestra el número de nuevos dispositivos detectados, en los últimos 7 días, enumerados en la vista actual.

![Imagen del nuevo recuento de dispositivos detectados.](images/new-discovered-devices.png)

## <a name="explore-the-device-inventory"></a>Exploración del inventario de dispositivos

Hay varias opciones entre las que puede elegir para personalizar la vista de inventario de dispositivos. En la navegación superior de cada pestaña, puede hacer lo siguiente:

- Búsqueda de un dispositivo por nombre
- Busque un dispositivo con el prefijo de dirección IP o dirección IP usado más recientemente.
- Agregar o quitar columnas
- Exportación de toda la lista en formato CSV para el análisis sin conexión
- Seleccione el intervalo de fechas que se va a mostrar.
- Aplicar filtros

> [!NOTE]
> Si exporta la lista de dispositivos, contendrá todos los dispositivos de la organización. La descarga puede tardar mucho tiempo, en función del tamaño de su organización. La exportación de la lista en formato CSV muestra los datos de forma no filtrada. El archivo CSV incluirá todos los dispositivos de la organización, independientemente de los filtros aplicados en la propia vista.

Puede usar la funcionalidad de ordenación y filtro disponible en cada pestaña de inventario de dispositivos para obtener una vista más centrada y ayudarle a evaluar y administrar los dispositivos de su organización.

Los recuentos en la parte superior de cada pestaña se actualizarán en función de la vista actual.

## <a name="use-filters-to-customize-the-device-inventory-views"></a>Uso de filtros para personalizar las vistas de inventario de dispositivos

Filtro | Descripción
:---|:---
**Nivel de riesgo** </br> | El nivel de riesgo refleja la evaluación general del riesgo del dispositivo en función de una combinación de factores, incluidos los tipos y la gravedad de las alertas activas en el dispositivo. La resolución de alertas activas, la aprobación de actividades de corrección y la supresión de las alertas posteriores pueden reducir el nivel de riesgo.
**Nivel de exposición** </br> | El nivel de exposición refleja la exposición actual del dispositivo en función del impacto acumulado de sus recomendaciones de seguridad pendientes. Los niveles posibles son bajo, medio y alto. Una exposición baja significa que los dispositivos son menos vulnerables a la explotación. </br> </br> Si el nivel de exposición indica "No hay datos disponibles", hay algunas razones por las que puede ser así:</br>- El dispositivo dejó de informar durante más de 30 días. En ese caso, se considera inactivo y la exposición no se calcula.</br>- No se admite el sistema operativo del dispositivo: consulte [los requisitos mínimos para Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/minimum-requirements).</br>- Dispositivo con agente obsoleto (poco probable).
**Tags** </br> | Filtre la lista en función de la agrupación y el etiquetado que haya agregado a dispositivos individuales. Consulte [Creación y administración de etiquetas de dispositivo](machine-tags.md).
**Valor del dispositivo**</br> | Filtre la lista en función de si el dispositivo se ha marcado como valor alto o bajo.
**Estado de exclusión** </br> | Filtre la lista en función de si el dispositivo se ha excluido o no. Para obtener más información, consulte [Excluir dispositivos](exclude-devices.md).
**Plataforma del sistema operativo** </br>| Filtrar por las plataformas del sistema operativo que le interesan investigar </br></br>(_Solo equipos y dispositivos móviles e IoT_)
**Primero visto** </br> | Filtre la vista en función de cuándo se vio el dispositivo por primera vez en la red o cuando el sensor de Microsoft Defender para punto de conexión lo notificó por primera vez.</br></br>(_Solo equipos y dispositivos móviles e IoT_)
**Versión de Windows** </br> | Filtre por las versiones de Windows que le interese investigar.</br></br> (_Solo equipos y dispositivos móviles_)
**Estado del sensor** </br> | Filtre por los siguientes estados de mantenimiento del sensor para los dispositivos incorporados a Microsoft Defender para punto de conexión:</br> - **Activo**: dispositivos que informan activamente de los datos del sensor al servicio.</br> - **Inactivo**: dispositivos que han dejado de enviar señales durante más de 7 días. </br> - **Mal configurado**: los dispositivos que han deteriorado las comunicaciones con el servicio o no pueden enviar datos del sensor. </br> Los dispositivos mal configurados se pueden clasificar aún más en: </br>  - Sin datos del sensor </br>  - Comunicaciones afectadas </br>  Para obtener más información sobre cómo solucionar problemas en dispositivos mal configurados, consulte [Corrección de sensores incorrectos](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors).</br></br> (_Solo equipos y dispositivos móviles_)
**Estado de incorporación** </br> | El estado de incorporación indica si el dispositivo está incorporado actualmente a Microsoft Defender para punto de conexión o no. Puede filtrar por los siguientes estados: </br> - **Incorporado**: el punto de conexión se incorpora a Microsoft Defender para punto de conexión.  </br> - **Se puede incorporar**: el punto de conexión se detectó en la red como un dispositivo compatible, pero no está incorporado actualmente. Microsoft recomienda encarecidamente la incorporación de estos dispositivos. </br> - **No compatible**: el punto de conexión se detectó en la red, pero no es compatible con Microsoft Defender para punto de conexión. </br> - **Información insuficiente**: el sistema no pudo determinar la compatibilidad del dispositivo.</br></br> (_Solo equipos y dispositivos móviles_)
**Estado del antivirus** </br> | Filtre la vista en función de si el estado del antivirus está deshabilitado, no actualizado o desconocido.</br></br> (_Solo equipos y dispositivos móviles_)
**Grupo** </br> | Filtre la lista según el grupo que le interesa investigar. </br></br> (_Solo equipos y dispositivos móviles_)
**Administrado por** </br> | Administrado por indica cómo se administra el dispositivo. Se puede filtrar por:</br> - Microsoft Defender para punto de conexión</br> - Microsoft Endpoint Manager (MEM), incluida la administración conjunta con Microsoft Configuration Manager a través de la asociación de inquilinos</br>- Microsoft Configuration Manager (ConfigMgr)</br> - Desconocido: esto podría deberse a la ejecución de una versión de Windows obsoleta, administración de GPO u otro MDM de terceros.</br></br> (_Solo equipos y dispositivos móviles_) 
**Tipo de dispositivo** </br> | Filtre por el tipo de dispositivo que le interesa investigar.</br></br> (_solo dispositivos IoT_)

## <a name="use-columns-to-customize-the-device-inventory-views"></a>Uso de columnas para personalizar las vistas de inventario de dispositivos

Puede agregar o quitar columnas de la vista y ordenar las entradas haciendo clic en un encabezado de columna disponible.

En la pestaña **Equipo y dispositivos móviles** , seleccione **Personalizar columnas** para ver las columnas disponibles. Los valores predeterminados se comprueban en la imagen siguiente:

![Imagen de equipos y dispositivos móviles](images/computerandmobilescolumns.png)

En la pestaña **Dispositivos de red** , seleccione **Personalizar columnas** para ver las columnas disponibles. Los valores predeterminados se comprueban en la imagen siguiente:

![Imagen de las columnas de dispositivo de red](images/networkdevicescolumns.png)

En la pestaña **Dispositivos IoT** , seleccione **Personalizar columnas** para ver las columnas disponibles. Los valores predeterminados se comprueban en la imagen siguiente:

![Imagen de las columnas de dispositivo IoT](images/iotdevicescolumns.png)

## <a name="related-articles"></a>Artículos relacionados

[Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión](investigate-machines.md)
