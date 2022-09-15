---
title: Comprobación de la ubicación del almacenamiento de datos y actualización de la configuración de retención de datos
description: Compruebe la ubicación del almacenamiento de datos y actualice la configuración de retención de datos para Microsoft Defender para punto de conexión
keywords: datos, almacenamiento, configuración, retención, actualización
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
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 3fbcb8b512258b4307cf691ff2b720f78f5d7796
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67709443"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>Compruebe la ubicación del almacenamiento de datos y actualice la configuración de retención de datos para Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-gensettings-abovefoldlink)

Durante el proceso de incorporación, un asistente le llevará a través de la configuración de almacenamiento y retención de datos de Defender para punto de conexión. 

Después de completar la incorporación, puede comprobar la selección en la página de configuración de retención de datos.

## <a name="verify-data-storage-location"></a>Comprobación de la ubicación del almacenamiento de datos
Durante la [fase de configuración](production-deployment.md), habría seleccionado la ubicación para almacenar los datos. 


Para comprobar la ubicación de los datos, vaya a **Configuración** \> **Puntos de conexión** \> **Retención de datos** (en **General**).


## <a name="update-data-retention-settings"></a>Actualización de la configuración de retención de datos

Puede actualizar la configuración de retención de datos. De forma predeterminada, el período de retención es de 180 días. 

1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** \> **Retención de datos** (en **General**).

2. Seleccione la duración de retención de datos en la lista desplegable.

    > [!NOTE]
    > Otras opciones de configuración no son editables.

3. Haga clic en **Guardar preferencias**.

## <a name="related-topics"></a>Temas relacionados
- [Actualización de la configuración de retención de datos](data-retention-settings.md)
- [Configuración de notificaciones de alertas en Defender para punto de conexión](configure-email-notifications.md)
- [Configurar funciones avanzadas](advanced-features.md)
