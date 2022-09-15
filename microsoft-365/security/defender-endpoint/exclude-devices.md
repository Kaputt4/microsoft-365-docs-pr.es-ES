---
title: Excluir dispositivos en Microsoft Defender para punto de conexión
description: Excluir dispositivos de la lista de inventario de dispositivos
keywords: Excluir
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: c23b510de6c3fd68fc1489aa3db5952d06e936a9
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698858"
---
# <a name="exclude-devices"></a>Excluir dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-respondmachine-abovefoldlink)

## <a name="exclude-devices-from-vulnerability-management"></a>Excluir dispositivos de la administración de vulnerabilidades

Excluir dispositivos inactivos, duplicados o fuera del ámbito le permite centrarse en detectar y priorizar los riesgos en los dispositivos activos. Esta acción también puede ayudar a reflejar una puntuación de exposición de administración de vulnerabilidades más precisa, ya que los dispositivos excluidos no estarán visibles en los informes de administración de vulnerabilidades.

Una vez que se excluyen los dispositivos, no podrá ver información actualizada o relevante sobre vulnerabilidades y software instalado en estos dispositivos. Afecta a todas las páginas de administración de vulnerabilidades, informes y tablas relacionadas en la búsqueda avanzada.

Aunque la característica de exclusión de dispositivos quita los datos del dispositivo de las páginas e informes de administración de vulnerabilidades, los dispositivos permanecen conectados a la red y pueden seguir siendo un riesgo para la organización. Podrá cancelar la exclusión del dispositivo en cualquier momento.

## <a name="how-to-exclude-a-device"></a>Cómo excluir un dispositivo

Puede optar por excluir un solo dispositivo o varios dispositivos al mismo tiempo.

### <a name="exclude-a-single-device"></a>Excluir un único dispositivo

1. Vaya a la página **Inventario de** dispositivos y seleccione el dispositivo que desea excluir.
2. Seleccione **Excluir** en la barra de acciones de la página de inventario del dispositivo o en el menú de acciones del control flotante del dispositivo.

   ![Imagen de la opción de menú Excluir dispositivo.](images/exclude-devices-menu.png)

3. Seleccione una justificación:

    - Dispositivo inactivo
    - Dispositivo duplicado
    - El dispositivo no existe
    - Fuera de ámbito
    - Otros

4. Escriba una nota y seleccione **Excluir dispositivo**.

![Imagen del dispositivo de exclusión.](images/exclude-device.png)

También puede excluir un dispositivo de su página de dispositivo.

> [!NOTE]
> No se recomienda excluir los dispositivos activos, ya que es especialmente arriesgado no tener visibilidad sobre su información de vulnerabilidad. Si un dispositivo está activo e intenta excluirlo, recibirá un mensaje de advertencia y un mensaje emergente de confirmación que le preguntará si está seguro de que desea excluir un dispositivo activo.

Un dispositivo puede tardar hasta 10 horas en excluirse completamente de los datos y vistas de administración de vulnerabilidades.

Los dispositivos excluidos siguen estando visibles en la lista Inventario de dispositivos. Puede administrar la vista de los dispositivos excluidos mediante:

- Agregar la columna **Estado de exclusión** a la vista de inventario de dispositivos.
- Usar el filtro **de estado de exclusión** para ver la lista pertinente de dispositivos.

![Imagen del estado de exclusión.](images/exclusion-state.png)

### <a name="bulk-device-exclusion"></a>Exclusión masiva de dispositivos

También puede optar por excluir varios dispositivos al mismo tiempo:

1. Vaya a la página **Inventario de** dispositivos y seleccione los dispositivos que desea excluir.

2. En la barra de acciones, seleccione **Excluir**.

3. Elija una justificación y seleccione **Excluir dispositivo**.

Si selecciona varios dispositivos en la lista de dispositivos con diferentes estados de exclusión, el control flotante Excluir dispositivos seleccionados le proporcionará detalles sobre cuántos de los dispositivos seleccionados ya están excluidos. Puede volver a excluir los dispositivos, pero se invalidarán la justificación y las notas.

![Imagen de exclusión masiva](images/exclude-device-bulk.png)

Una vez que se excluye un dispositivo, si va a la página del dispositivo de un dispositivo excluido, no podrá ver los datos de las vulnerabilidades detectadas, el inventario de software o las recomendaciones de seguridad. Los datos tampoco se mostrarán en páginas de administración de vulnerabilidades, tablas de búsqueda avanzada relacionadas y el informe de dispositivos vulnerables.

## <a name="stop-excluding-a-device"></a>Detener la exclusión de un dispositivo

Podrá dejar de excluir un dispositivo en cualquier momento. Una vez que los dispositivos ya no se excluyen, sus datos de vulnerabilidad serán visibles en las páginas de administración de vulnerabilidades, los informes y en la búsqueda avanzada. Los cambios pueden tardar hasta 8 horas en surtir efecto.

1. Vaya al inventario de dispositivos, seleccione el dispositivo excluido para abrir el control flotante y, a continuación, seleccione **Detalles de exclusión**.
2. Seleccione **Detener exclusión.**

![Imagen de los detalles de exclusión](images/exclusion-details.png)

## <a name="see-also"></a>Vea también

- [Inventario de dispositivos](machines-view-overview.md)
