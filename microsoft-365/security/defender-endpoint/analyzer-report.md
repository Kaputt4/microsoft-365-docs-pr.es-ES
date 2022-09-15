---
title: Descripción del informe HTML del analizador de cliente
description: Obtenga información sobre cómo analizar el informe HTML del Analizador de clientes Microsoft Defender para punto de conexión
keywords: informe del analizador de cliente, informe html, analizador de cliente
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: c9ba1865710dbaaf0c35cfbd37c4985ad4fa1ad1
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702608"
---
# <a name="understand-the-client-analyzer-html-report"></a>Descripción del informe HTML del analizador de cliente

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

El analizador de cliente genera un informe en formato HTML. Obtenga información sobre cómo revisar el informe para identificar posibles problemas de sensor para que pueda solucionarlos.

Use el ejemplo siguiente para comprender el informe.

 Salida de ejemplo del analizador en una máquina incorporada al identificador de organización expirado y no se puede alcanzar una de las direcciones URL de Microsoft Defender para punto de conexión necesarias:

:::image type="content" source="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png" alt-text="Página de resultados del analizador de cliente de MDE" lightbox="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png":::

- Además, la versión del script y el tiempo de ejecución del script aparecen como referencia.
- La sección **Información del dispositivo** proporciona identificadores básicos del sistema operativo y del dispositivo para identificar de forma única el dispositivo en el que se ha ejecutado el analizador.
- **Los detalles de seguridad del punto de conexión** proporcionan información general sobre los procesos relacionados con Microsoft Defender para punto de conexión, incluidos el Antivirus de Microsoft Defender y el proceso del sensor. Si los procesos importantes no están en línea como se esperaba, el color cambiará a rojo.
  
-   **Los detalles de seguridad del punto de conexión** proporcionan información general sobre los procesos relacionados con Microsoft Defender para punto de conexión, incluidos el Antivirus de Microsoft Defender y el proceso del sensor. Si los procesos importantes no están en línea como se esperaba, el color cambiará a rojo.

    :::image type="content" source="images/85f56004dc6bd1679c3d2c063e36cb80.png" alt-text="Página Resumen de resultados de comprobación" lightbox="images/85f56004dc6bd1679c3d2c063e36cb80.png":::

-   En **Resumen de resultados de comprobación**, tendrá un recuento agregado de eventos de error, advertencia o información detectados por el analizador.

-   En **Resultados detallados**, verá una lista (ordenada por gravedad) con los resultados y las instrucciones basadas en las observaciones realizadas por el analizador.

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>Abra una incidencia de soporte técnico en Microsoft e incluya los resultados del analizador.

Para incluir archivos de resultados del analizador [al abrir una incidencia de soporte](contact-support.md#open-a-service-request) técnico, asegúrese de usar la sección **Datos adjuntos** e incluir el `MDEClientAnalyzerResult.zip` archivo:

:::image type="content" source="images/508c189656c3deb3b239daf811e33741.png" alt-text="Una solicitud de datos adjuntos" lightbox="images/508c189656c3deb3b239daf811e33741.png":::

> [!NOTE]
> Si el tamaño del archivo es superior a 25 MB, el ingeniero de soporte técnico asignado a su caso proporcionará un área de trabajo segura dedicada para cargar archivos grandes para su análisis.
