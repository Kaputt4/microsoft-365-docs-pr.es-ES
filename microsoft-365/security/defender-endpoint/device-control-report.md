---
title: Protección de los datos de la organización con el control de dispositivos
description: Supervise la seguridad de los datos de su organización a través de informes de control de dispositivos.
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: conceptual
manager: dansimp
audience: ITPro
ms.subservice: mde
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: 451e255e09e87493c895f57d330ca957e01196b8
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620467"
---
# <a name="device-control-report"></a>Informe de control de dispositivo

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender para punto de conexión control de dispositivos protege contra la pérdida de datos mediante la supervisión y el control del uso de medios por parte de los dispositivos de la organización, como el uso de dispositivos de almacenamiento extraíbles y unidades USB.

Con el informe de control de dispositivos, puede ver eventos relacionados con el uso de medios. Estos eventos incluyen:

- **Eventos de auditoría:** Muestra el número de eventos de auditoría que se producen cuando se conecta un medio externo.
- **Eventos de directiva:** Muestra el número de eventos de directiva que se producen cuando se desencadena una directiva de control de dispositivo.

> [!NOTE]
> El evento de auditoría para realizar un seguimiento del uso de medios está habilitado de forma predeterminada para los dispositivos incorporados a Microsoft Defender para punto de conexión.

## <a name="understanding-the-audit-events"></a>Descripción de los eventos de auditoría

Los eventos de auditoría incluyen:

- **Montaje y desmontaje de la unidad USB:** Eventos de auditoría que se generan cuando se monta o desmonta una unidad USB.
- **Pnp:** Los eventos de auditoría plug and play se generan cuando se conecta el almacenamiento extraíble, una impresora o un medio Bluetooth.
- **Control de acceso de almacenamiento extraíble:** Los eventos se generan cuando se desencadena una directiva de control de acceso de almacenamiento extraíble. Puede ser Auditar, Bloquear o Permitir.

## <a name="monitor-device-control-security"></a>Supervisión de la seguridad del control de dispositivos

El control de dispositivos en Defender para punto de conexión proporciona a los administradores de seguridad herramientas que les permiten realizar un seguimiento de la seguridad del control de dispositivos de su organización a través de informes. Puede encontrar el informe de control de dispositivos en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). Vaya al **Informe de seguridad** **general** >  **de informes** > . Busque **Tarjeta de control de** dispositivo y seleccione el vínculo para abrir el informe. 

La tarjeta Protección de dispositivos del panel **Informes** muestra el número de eventos de auditoría generados por el tipo de medio en los últimos 180 días.

El botón **Ver detalles** muestra más datos de uso multimedia en la página **del informe de control de dispositivos** .

La página proporciona un panel con un número agregado de eventos por tipo y una lista de eventos y muestra 500 eventos por página, pero los administradores pueden desplazarse hacia abajo para ver más eventos y pueden filtrar por intervalo de tiempo, nombre de clase multimedia e identificador de dispositivo.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Detaileddevicecontrolreport.png" alt-text="Página Detalles del informe de control de dispositivos en el portal de Microsoft 365 Defender" lightbox="images/Detaileddevicecontrolreport.png":::

Al seleccionar un evento, aparece un control flotante que muestra más información:

- **Detalles generales:** Fecha, modo de acción, directiva y acceso de este evento.
- **Información multimedia:** La información multimedia incluye el nombre multimedia, el nombre de clase, el GUID de clase, el identificador de dispositivo, el identificador de proveedor, el número de serie y el tipo de bus.
- **Detalles de ubicación:** Nombre del dispositivo, usuario e identificador de dispositivo MDATP.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/devicecontrolreportfilter.png" alt-text="Página Filtrar en el informe de control de dispositivo" lightbox="images/devicecontrolreportfilter.png":::

Para ver la actividad en tiempo real de este medio en toda la organización, seleccione el botón **Abrir búsqueda avanzada** . Esto incluye una consulta incrustada predefinida.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Devicecontrolreportquery.png" alt-text="Página Consulta en el informe de control de dispositivo" lightbox="images/Devicecontrolreportquery.png":::

Para ver la seguridad del dispositivo, seleccione el botón **Abrir página del dispositivo** en el control flotante. Este botón abre la página de entidad del dispositivo.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Devicesecuritypage.png" alt-text="Página De entidad de dispositivo" lightbox="images/Devicesecuritypage.png":::

## <a name="reporting-delays"></a>Notificación de retrasos

Puede haber un retraso de hasta 12 horas desde el momento en que se produce una conexión multimedia hasta el momento en que el evento se refleja en la tarjeta o en la lista de dominios.
