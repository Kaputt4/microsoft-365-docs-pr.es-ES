---
title: Comprobar la ubicación de almacenamiento de datos y actualizar la configuración de retención de datos
description: Comprobar la ubicación de almacenamiento de datos y actualizar la configuración de retención de datos para Microsoft Defender para endpoint
keywords: datos, almacenamiento, configuración, retención, actualización
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: eb9e4b905112d3d144b10d68418695df3cda29cb
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339255"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>Comprobar la ubicación de almacenamiento de datos y actualizar la configuración de retención de datos para Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

Durante el proceso de incorporación, un asistente le llevará a través de la configuración de almacenamiento y retención de datos de Defender for Endpoint. 

Después de completar la incorporación, puede comprobar la selección en la página de configuración de retención de datos.

## <a name="verify-data-storage-location"></a>Comprobar la ubicación de almacenamiento de datos
Durante la [fase de configuración,](production-deployment.md)habría seleccionado la ubicación para almacenar los datos. 

Para comprobar la ubicación de los datos, vaya a **Configuración** de retención de  >  **datos** de  >  **puntos de conexión**.

## <a name="update-data-retention-settings"></a>Actualizar la configuración de retención de datos

Puede actualizar la configuración de retención de datos. De forma predeterminada, el período de retención es de 180 días. 

1. En el panel de navegación, **seleccione Configuración** Datos de puntos  >  **de**  >  **conexión**.

2. Seleccione la duración de retención de datos de la lista desplegable.

    > [!NOTE]
    > Otras opciones de configuración no son editables.

3. Haga clic **en Guardar preferencias**.


## <a name="related-topics"></a>Temas relacionados
- [Actualizar la configuración de retención de datos](data-retention-settings.md)
- [Configurar notificaciones de alertas en Defender para endpoint](configure-email-notifications.md)
- [Configurar funciones avanzadas](advanced-features.md)
