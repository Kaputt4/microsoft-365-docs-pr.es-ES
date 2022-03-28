---
title: Proteger los datos de la organización con el control de dispositivos
description: Supervisar la seguridad de datos de la organización a través de informes de control de dispositivos.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 8a31ce05ed6986159d9f6e4c489e6f7707cfecc4
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465297"
---
# <a name="device-control-report"></a>Informe de control de dispositivos

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

El control de dispositivos de Microsoft Defender para endpoints protege contra la pérdida de datos mediante la supervisión y el control del uso de medios por parte de los dispositivos de la organización, como el uso de dispositivos de almacenamiento extraíbles y unidades USB.

Con el informe de control de dispositivos, puedes ver eventos relacionados con el uso de medios, como:

- **Eventos de auditoría:** Muestra el número de eventos de auditoría que se producen cuando se conectan medios externos.
- **Eventos de directiva:** Muestra el número de eventos de directiva que se producen cuando se desencadena una directiva de control de dispositivos.

> [!NOTE]
> El evento de auditoría para realizar un seguimiento del uso de medios está habilitado de forma predeterminada para los dispositivos incorporados a Microsoft Defender para endpoint.

## <a name="understanding-the-audit-events"></a>Descripción de los eventos de auditoría

Los eventos de auditoría incluyen:

- **Montaje y desmontaje de la unidad USB:** Audite los eventos que se generan cuando se monta o desmonta una unidad USB.
- **PnP:** Los eventos de auditoría plug and play se generan cuando se conecta un almacenamiento extraíble, una impresora o Bluetooth multimedia.
- **Control de acceso de almacenamiento extraíble:** Los eventos se generan cuando se desencadena una directiva de control de acceso de almacenamiento extraíble. Puede ser Auditar, Bloquear o Permitir.

## <a name="monitor-device-control-security"></a>Supervisar la seguridad del control de dispositivos

El control de dispositivos en Microsoft Defender para endpoint habilita a los administradores de seguridad con herramientas que les permiten realizar un seguimiento de la seguridad del control de dispositivos de su organización a través de informes. Para encontrar el informe de control de dispositivos en el portal de Microsoft 365 Defender, vaya a **Informes > protección de dispositivos**.

La tarjeta de protección de dispositivos del panel **Informes** muestra el número de eventos de auditoría generados por tipo de medio en los últimos 180 días.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportCard](https://user-images.githubusercontent.com/81826151/138504137-e9a7673e-e988-48cd-820d-2625ec6df352.png)

El **botón Ver detalles** muestra más datos de uso multimedia en la página **del informe de control de** dispositivos.

La página proporciona un panel con un número agregado de eventos por tipo y una lista de eventos. Los administradores pueden filtrar por intervalo de tiempo, nombre de clase multimedia e identificador de dispositivo.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Detaileddevicecontrolreport.png" alt-text="La página Detalles del informe de control de dispositivos en el portal Microsoft 365 Defender dispositivo" lightbox="images/Detaileddevicecontrolreport.png":::

Al seleccionar un evento, aparece un flyout que muestra más información:

- **Detalles generales:** Fecha, modo acción, directiva y Acceso de este evento.
- **Información multimedia:** La información multimedia incluye nombre multimedia, nombre de clase, GUID de clase, id. de dispositivo, id. de proveedor, número de serie y tipo bus.
- **Detalles de ubicación:** Nombre del dispositivo, Usuario e Id. de dispositivo MDATP.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/devicecontrolreportfilter.png" alt-text="Página Filtrar en informe de control de dispositivos" lightbox="images/devicecontrolreportfilter.png":::

Para ver la actividad en tiempo real de este medio en toda la organización, seleccione el **botón Abrir búsqueda** avanzada. Esto incluye una consulta incrustada y predefinida.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Devicecontrolreportquery.png" alt-text="Página Consulta en informe de control de dispositivos" lightbox="images/Devicecontrolreportquery.png":::

Para ver la seguridad del dispositivo, selecciona el botón **Abrir página del** dispositivo en el control desplegable. Este botón abre la página de entidad del dispositivo.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Devicesecuritypage.png" alt-text="La página Entidad de dispositivo" lightbox="images/Devicesecuritypage.png":::

## <a name="reporting-delays"></a>Retrasos en la presentación de informes

El informe de control de dispositivos puede tener un retraso de 12 horas desde el momento en que se produce una conexión multimedia hasta el momento en que el evento se refleja en la tarjeta o en la lista de dominios.
