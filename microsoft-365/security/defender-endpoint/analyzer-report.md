---
title: Comprender el informe HTML del analizador de cliente
description: Obtenga información sobre cómo analizar el informe HTML de Microsoft Defender para Endpoint Client Analyzer
keywords: Informe del analizador de cliente, informe html, analizador de cliente
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 735b2a0331e399fa7bf3444ff8e5326898c038b4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187585"
---
# <a name="understand-the-client-analyzer-html-report"></a>Comprender el informe HTML del analizador de cliente

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

El analizador de cliente genera un informe en formato HTML. Obtenga información sobre cómo revisar el informe para identificar posibles problemas del sensor para que pueda solucionarlos.

Use el siguiente ejemplo para comprender el informe.

 Ejemplo de salida del analizador en un equipo incorporado al id. de organización expirado y no se puede llegar a una de las direcciones URL de Microsoft Defender para extremo necesarias:

![Imagen del resultado del analizador de cliente.](images/147cbcf0f7b6f0ff65d200bf3e4674cb.png)

- En la parte superior, la versión de script y el tiempo de ejecución de script se enumeran como referencia
- La **sección Información del** dispositivo proporciona un sistema operativo básico e identificadores de dispositivo para identificar de forma única el dispositivo en el que se ha ejecutado el analizador.
- Los **detalles de seguridad de** puntos de conexión proporcionan información general sobre Microsoft Defender para los procesos relacionados con endpoints, incluidos Antivirus de Microsoft Defender y el proceso del sensor. Si los procesos importantes no están en línea como se esperaba, el color cambiará a rojo.

  ![Imagen del resultado detallado del analizador de cliente](images/85f56004dc6bd1679c3d2c063e36cb80.png)

-   Los **detalles de seguridad de** puntos de conexión proporcionan información general sobre Microsoft Defender para los procesos relacionados con endpoints, incluidos Antivirus de Microsoft Defender y el proceso del sensor. Si los procesos importantes no están en línea como se esperaba, el color cambiará a rojo.

![Imagen del resultado detallado del analizador de cliente.](images/85f56004dc6bd1679c3d2c063e36cb80.png)

-   En **Comprobar resumen de** resultados, tendrá un recuento agregado de eventos de error, advertencia o informativos detectados por el analizador.

-   En **los resultados detallados** verá una lista (ordenada por gravedad) con los resultados y las instrucciones basadas en las observaciones realizadas por el analizador.

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>Abrir un vale de soporte técnico a Microsoft e incluir los resultados del analizador

Para incluir archivos de resultados del analizador [al abrir un vale](contact-support.md#open-a-service-request)de soporte técnico, asegúrese de usar la sección **Datos** adjuntos e incluir el `MDEClientAnalyzerResult.zip` archivo:

![Imagen del símbolo del sistema de datos adjuntos.](images/508c189656c3deb3b239daf811e33741.png)

> [!NOTE]
> Si el tamaño del archivo es mayor que 25 MB, el ingeniero de soporte técnico asignado a su caso proporcionará un área de trabajo segura dedicada para cargar archivos grandes para su análisis.
