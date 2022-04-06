---
title: Comprender el informe HTML del analizador de cliente
description: Obtenga información sobre cómo analizar el informe HTML de Microsoft Defender para Endpoint Client Analyzer
keywords: Informe del analizador de cliente, informe html, analizador de cliente
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1f843c62d44ed7c25f07568cc0ee92709fb080a7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468907"
---
# <a name="understand-the-client-analyzer-html-report"></a>Comprender el informe HTML del analizador de cliente

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

El analizador de cliente genera un informe en formato HTML. Obtenga información sobre cómo revisar el informe para identificar posibles problemas del sensor para que pueda solucionarlos.

Use el siguiente ejemplo para comprender el informe.

 Ejemplo de salida del analizador en un equipo incorporado al id. de organización expirado y no se puede llegar a una de las direcciones URL de Microsoft Defender para extremo necesarias:

:::image type="content" source="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png" alt-text="Página De resultados del analizador de cliente MDE" lightbox="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png":::

- En la parte superior, la versión de script y el tiempo de ejecución del script se enumeran como referencia
- La **sección Información del** dispositivo proporciona un sistema operativo básico e identificadores de dispositivo para identificar de forma única el dispositivo en el que se ha ejecutado el analizador.
- Los **detalles de seguridad de** puntos de conexión proporcionan información general sobre Microsoft Defender para los procesos relacionados con endpoints, incluidos Antivirus de Microsoft Defender y el proceso del sensor. Si los procesos importantes no están en línea como se esperaba, el color cambiará a rojo.
  
-   Los **detalles de seguridad de** puntos de conexión proporcionan información general sobre Microsoft Defender para los procesos relacionados con endpoints, incluidos Antivirus de Microsoft Defender y el proceso del sensor. Si los procesos importantes no están en línea como se esperaba, el color cambiará a rojo.

    :::image type="content" source="images/85f56004dc6bd1679c3d2c063e36cb80.png" alt-text="Página Comprobar resumen de resultados" lightbox="images/85f56004dc6bd1679c3d2c063e36cb80.png":::

-   En **Comprobar resumen de** resultados, tendrá un recuento agregado de eventos de error, advertencia o informativos detectados por el analizador.

-   En **Resultados** detallados, verá una lista (ordenada por gravedad) con los resultados y las instrucciones basadas en las observaciones realizadas por el analizador.

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>Abrir un vale de soporte técnico a Microsoft e incluir los resultados del analizador

Para incluir archivos de resultados [del analizador al abrir un vale de soporte](contact-support.md#open-a-service-request) técnico, asegúrese de usar la sección **Datos** adjuntos e incluir el `MDEClientAnalyzerResult.zip` archivo:

:::image type="content" source="images/508c189656c3deb3b239daf811e33741.png" alt-text="Un símbolo del sistema de datos adjuntos" lightbox="images/508c189656c3deb3b239daf811e33741.png":::

> [!NOTE]
> Si el tamaño del archivo es mayor que 25 MB, el ingeniero de soporte técnico asignado a su caso proporcionará un área de trabajo segura dedicada para cargar archivos grandes para su análisis.
