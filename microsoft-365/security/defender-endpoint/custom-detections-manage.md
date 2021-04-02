---
title: Ver y administrar reglas de detección personalizadas en ATP de Microsoft Defender
ms.reviewer: ''
description: Obtenga información sobre cómo ver y administrar reglas de detección personalizadas
keywords: detecciones personalizadas, ver, administrar, alertas, editar, ejecutar a petición, reglas de detección, búsqueda avanzada, búsqueda, búsqueda, consulta, acciones de respuesta, mdatp, atp de microsoft defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498754"
---
# <a name="view-and-manage-custom-detection-rules"></a>Ver y administrar reglas de detección personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Administre las reglas de [detección personalizadas existentes](custom-detection-rules.md) para asegurarse de que están detectando amenazas y llevando a cabo acciones de forma eficaz. Explore cómo ver la lista de reglas, comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado. También puede ejecutar una regla a petición y modificarla.

## <a name="required-permissions"></a>Permisos necesarios

Para crear o administrar detecciones personalizadas, [el rol](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) debe tener el permiso administrar la **configuración de** seguridad.

## <a name="view-existing-rules"></a>Ver reglas existentes

Para ver todas las reglas de detección personalizadas existentes, vaya **a Configuración**  >  **Detecciones personalizadas**. La página enumera todas las reglas con la siguiente información de ejecución:

- **Última ejecución:** cuando se ejecuta por última vez una regla para comprobar si hay coincidencias de consulta y generar alertas
- **Estado de la última ejecución:** si una regla se ejecutó correctamente
- **Siguiente ejecución**: la siguiente ejecución programada
- **Estado:** si se ha activado o desactivado una regla

## <a name="view-rule-details-modify-rule-and-run-rule"></a>Ver detalles de regla, modificar regla y ejecutar regla

Para ver información completa acerca de una regla de detección personalizada, seleccione el nombre de la regla de la lista de reglas en **Configuración**  >  **Detecciones personalizadas**. Una página sobre la regla seleccionada muestra la siguiente información:

- Información general sobre la regla, incluidos los detalles de la alerta, el estado de ejecución y el ámbito
- Lista de alertas desencadenadas
- Lista de acciones desencadenadas

![Página de regla de detección personalizada](images/atp-custom-detection-rule-details.png)<br>
*Página de regla de detección personalizada*

También puede realizar las siguientes acciones en la regla desde esta página:

- **Ejecutar**: ejecute la regla inmediatamente. Esta acción también restablece el intervalo de la siguiente ejecución.
- **Editar**: modificar la regla sin cambiar la consulta
- **Modificar consulta**: editar la consulta en búsqueda avanzada
- **Activar**  /  **Desactivar :** habilitar la regla o impedir que se ejecute
- **Eliminar**: desactivar la regla y quitarla

>[!TIP]
>Para ver rápidamente la información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.

## <a name="related-topics"></a>Temas relacionados
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
- [Crear y administrar reglas de detección](custom-detection-rules.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Ver y organizar alertas](alerts-queue.md)
