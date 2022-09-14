---
title: Informe de protección contra amenazas en Microsoft Defender para punto de conexión
description: Seguimiento de detecciones de alertas, categorías y gravedad mediante el informe de protección contra amenazas
keywords: detección de alertas, origen, alerta por categoría, gravedad de alerta, clasificación de alertas, determinación
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
ms.openlocfilehash: 2e9fae2aa286204c51fdb485b8dd1dccac765110
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689237"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Informe de protección contra amenazas en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

El informe de protección contra amenazas proporciona información de alto nivel sobre las alertas generadas en su organización. El informe incluye información de tendencias que muestra los orígenes de detección, categorías, gravedades, estados, clasificaciones y determinaciones de alertas a lo largo del tiempo.

El panel se estructura en dos secciones:

:::image type="content" source="images/threat-protection-reports.png" alt-text="Informe de protección contra amenazas" lightbox="images/threat-protection-reports.png":::

Sección|Descripción
---|---
1|Tendencias de alertas
2|Resumen de alertas

## <a name="alert-trends"></a>Tendencias de alertas
De forma predeterminada, las tendencias de alerta muestran información de alertas del período de 30 días que termina en el último día completo. Para obtener una mejor perspectiva sobre las tendencias que se producen en su organización, puede ajustar el período de informes ajustando el período de tiempo mostrado. Para ajustar el período de tiempo, seleccione un intervalo de tiempo en las opciones desplegables:

- 30 días
- 3 meses
- 6 meses
- Personalizado

> [!NOTE]
> Estos filtros solo se aplican en la sección tendencias de alerta. No afecta a la sección de resumen de alertas.

## <a name="alert-summary"></a>Resumen de alertas

Aunque las tendencias de alertas muestran información de alertas de tendencia, el resumen de alertas muestra información de alertas con el ámbito del día actual.

 El resumen de alertas permite explorar en profundidad una cola de alertas determinada con el filtro correspondiente aplicado. Por ejemplo, al hacer clic en la barra EDR de la tarjeta Orígenes de detección, se mostrará la cola de alertas con resultados que muestran solo las alertas generadas a partir de detecciones de EDR.

> [!NOTE]
> Los datos reflejados en la sección de resumen se limitan a 180 días antes de la fecha actual. Por ejemplo, si la fecha de hoy es el 5 de noviembre de 2019, los datos de la sección de resumen reflejarán los números a partir del 5 de mayo de 2019 al 5 de noviembre de 2019.
>
> El filtro aplicado en la sección tendencias no se aplica en la sección de resumen.

## <a name="alert-attributes"></a>Atributos de alerta

El informe se compone de tarjetas que muestran los siguientes atributos de alerta:

- **Orígenes de detección**: muestra información sobre los sensores y las tecnologías de detección que proporcionan los datos usados por Microsoft Defender para punto de conexión para desencadenar alertas.
- **Categorías de amenazas**: muestra los tipos de actividad de amenazas o ataques que desencadenaron alertas, lo que indica posibles áreas de enfoque para las operaciones de seguridad.
- **Gravedad**: muestra el nivel de gravedad de las alertas, que indica el impacto potencial colectivo de las amenazas para su organización y el nivel de respuesta necesario para abordarlas.
- **Estado**: muestra el estado de resolución de las alertas, que indica la eficacia de las respuestas manuales de alertas y de la corrección automatizada (si está habilitada).
- **Clasificación & determinación**: muestra cómo ha clasificado las alertas tras la resolución, si las ha clasificado como amenazas reales (alertas verdaderas) o como detecciones incorrectas (alertas falsas). Estas tarjetas también muestran la determinación de las alertas resueltas, lo que proporciona información adicional, como los tipos de amenazas reales encontradas o las actividades legítimas que se detectaron incorrectamente.

## <a name="filter-data"></a>Filtrar datos

Use los filtros proporcionados para incluir o excluir alertas con determinados atributos.

> [!NOTE]
> Estos filtros se aplican a **todas** las tarjetas del informe.

Por ejemplo, para mostrar solo datos sobre alertas de gravedad alta:

1. En **Incidentes & alertas** **Filtros de alertas** \> \> **> gravedad**, seleccione **Alto**.
2. Asegúrese de que todas las demás opciones de **Gravedad** estén desactivadas.
3. Seleccione **Aplicar**.

## <a name="related-topic"></a>Tema relacionado

- [Cumplimiento normativo y estado del dispositivo](machine-reports.md)
