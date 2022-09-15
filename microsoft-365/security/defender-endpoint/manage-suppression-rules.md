---
title: Administración de reglas de supresión de Microsoft Defender para punto de conexión
description: Es posible que tenga que impedir que aparezcan alertas en el portal mediante reglas de supresión. Obtenga información sobre cómo administrar las reglas de supresión en Microsoft Defender para punto de conexión.
keywords: administrar supresión, reglas, nombre de regla, ámbito, acción, alertas, activar, desactivar
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 89c7be7c5fcdad33932e9e537d3c05b35656fc44
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67700210"
---
# <a name="manage-suppression-rules"></a>Administrar reglas de supresión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


Puede haber escenarios en los que tenga que suprimir la aparición de alertas en el portal. Puede crear reglas de supresión para alertas específicas que se sabe que son inofensivos, como herramientas o procesos conocidos de la organización. Para obtener más información sobre cómo suprimir alertas, vea [Suprimir alertas](manage-alerts.md).

Puede ver una lista de todas las reglas de supresión y administrarlas en un solo lugar. También puede activar o desactivar una regla de supresión de alertas.


1. En el panel de navegación, seleccione **Configuración** \> **Supresión de alertas**\> de **puntos** \> **de conexión**. Se muestra la lista de reglas de supresión que han creado los usuarios de la organización.

2. Seleccione una regla haciendo clic en la casilla situada junto al nombre de la regla.

3. Haga clic **en Activar regla**, **Editar regla** o  **Eliminar regla**. Al realizar cambios en una regla, puede elegir liberar las alertas que ya ha suprimido, independientemente de si estas alertas coinciden o no con los nuevos criterios. 


## <a name="view-details-of-a-suppression-rule"></a>Ver detalles de una regla de supresión

1. En el panel de navegación, seleccione **Configuración** \> **Supresión de alertas**\> de **puntos** \> **de conexión**. Se muestra la lista de reglas de supresión que han creado los usuarios de la organización.

2. Haga clic en un nombre de regla. Se muestran los detalles de la regla. Verá los detalles de la regla, como el estado, el ámbito, la acción, el número de alertas coincidentes creadas por y la fecha en que se creó la regla. También puede ver las alertas asociadas y las condiciones de regla.

## <a name="related-topics"></a>Temas relacionados

- [Administrar alertas](manage-alerts.md)
