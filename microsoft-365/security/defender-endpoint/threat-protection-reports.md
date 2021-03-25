---
title: Informe de protección contra amenazas en ATP de Microsoft Defender
description: Realizar un seguimiento de las detecciones de alertas, categorías y gravedad con el informe de protección contra amenazas
keywords: detección de alertas, origen, alerta por categoría, gravedad de alerta, clasificación de alertas, determinación
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ecd2df31e1e03da5134d3d4180dcba75d3cee26
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183842"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Informe de protección contra amenazas en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

El informe de protección contra amenazas proporciona información de alto nivel sobre las alertas generadas en la organización. El informe incluye información de tendencias que muestra los orígenes de detección, categorías, gravedades, estados, clasificaciones y determinaciones de alertas a lo largo del tiempo.

El panel está estructurado en dos secciones:

![Imagen del informe de protección contra amenazas](images/threat-protection-reports.png)

Section | Descripción 
:---|:---
1 | Tendencias de alertas
2 | Resumen de alertas

## <a name="alert-trends"></a>Tendencias de alerta
De forma predeterminada, las tendencias de alerta muestran información de alerta del período de 30 días que termina en el último día completo. Para obtener una mejor perspectiva de las tendencias que se producen en su organización, puede ajustar el período de informes ajustando el período de tiempo que se muestra. Para ajustar el período de tiempo, seleccione un intervalo de tiempo en las opciones desplegables:

- 30 días
- 3 meses
- 6 meses
- Personalizado

>[!NOTE]
>Estos filtros solo se aplican en la sección de tendencias de alerta. No afecta a la sección de resumen de alertas.


## <a name="alert-summary"></a>Resumen de alertas
Aunque las tendencias de alerta muestran información de alerta de tendencias, el resumen de alerta muestra información de alerta en el ámbito del día actual.

 El resumen de alerta le permite explorar en profundidad una cola de alertas determinada con el filtro correspondiente aplicado. Por ejemplo, al hacer clic en la barra de EDR de la tarjeta Orígenes de detección, aparecerá la cola de alertas con resultados que muestran solo alertas generadas a partir de detecciones de EDR. 

>[!NOTE]
>Los datos reflejados en la sección de resumen están en el ámbito de 180 días antes de la fecha actual. Por ejemplo, si la fecha de hoy es el 5 de noviembre de 2019, los datos de la sección de resumen reflejarán números a partir del 5 de mayo de 2019 al 5 de noviembre de 2019.<br>
> El filtro aplicado en la sección tendencias no se aplica en la sección de resumen. 

## <a name="alert-attributes"></a>Atributos de alerta
El informe está hecho de tarjetas que muestran los siguientes atributos de alerta:

- **Orígenes de detección:** muestra información sobre los sensores y las tecnologías de detección que proporcionan los datos usados por Microsoft Defender para endpoint para desencadenar alertas.

- **Categorías de amenazas:** muestra los tipos de actividad de amenazas o ataques que desencadenaron alertas, lo que indica posibles áreas de foco para las operaciones de seguridad.

- **Gravedad:** muestra el nivel de gravedad de las alertas, lo que indica el impacto potencial colectivo de las amenazas en su organización y el nivel de respuesta necesario para abordarlas.

- **Estado:** muestra el estado de resolución de las alertas, lo que indica la eficacia de las respuestas de alerta manual y de la corrección automatizada (si está habilitada). 

- **Clasificación & determinación:** muestra cómo ha clasificado las alertas tras la resolución, si las ha clasificado como amenazas reales (alertas verdaderas) o como detecciones incorrectas (alertas falsas). Estas tarjetas también muestran la determinación de alertas resueltas, lo que proporciona información adicional como los tipos de amenazas reales encontradas o las actividades legítimas que se detectaron incorrectamente.


 

## <a name="filter-data"></a>Filtrar datos

Use los filtros proporcionados para incluir o excluir alertas con determinados atributos.

>[!NOTE]
>Estos filtros se aplican a **todas** las tarjetas del informe.

Por ejemplo, para mostrar solo datos sobre alertas de gravedad alta:

1. En **Filters > Severity**, seleccione **High**
2. Asegúrese de que todas las demás opciones en **Gravedad** están deseleccionados.
3. Seleccione **Aplicar**. 

## <a name="related-topic"></a>Tema relacionado
- [Informe de cumplimiento y estado del dispositivo](machine-reports.md)
