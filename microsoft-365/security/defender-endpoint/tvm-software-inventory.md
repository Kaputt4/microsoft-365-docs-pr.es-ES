---
title: Inventario de software en Administración de amenazas y vulnerabilidades
description: La página de inventario de software de Microsoft Defender para el punto de conexión Administración de amenazas y vulnerabilidades muestra cuántas debilidades y vulnerabilidades se han detectado en el software.
keywords: Administración de amenazas y vulnerabilidades, Microsoft Defender para endpoint, Inventario de software de Microsoft Defender para endpoint, Microsoft Defender para endpoint threat & administración de vulnerabilidades, Microsoft Defender for Endpoint threat & administración de vulnerabilidades de software, inventario de software de Microsoft Defender para Endpoint tvm, inventario de software de tvm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cbd4634e779fe2bf853aaf014b59b1e7e1c1928f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470051"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a>Inventario de software: Administración de amenazas y vulnerabilidades


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Amenaza y administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

El inventario de software en Administración de amenazas y vulnerabilidades es una lista de software conocido en su organización. El filtro predeterminado de la página de inventario de software muestra todo el software con enumeraciones de plataforma [común (CPE) oficiales](https://nvd.nist.gov/products/cpe). La vista incluye detalles como el nombre del proveedor, el número de debilidades, las amenazas y el número de dispositivos expuestos.

Puede quitar el filtro **CPE Disponible** para obtener más visibilidad y aumentar el ámbito de búsqueda en todo el software instalado de la organización. Esto significa que todo el software, incluido el software sin CPE, se mostrará ahora en la lista de inventario de software.

> [!NOTE]
> Como administración de vulnerabilidades usa las CPE para identificar el software y las vulnerabilidades, aunque los productos de software sin CPE se mostrarán en la página de inventario de software, no serán compatibles con Administración de amenazas y vulnerabilidades  y la información como, vulnerabilidades, número de dispositivos expuestos y debilidades no estará disponible para ellos.

## <a name="how-it-works"></a>Funcionamiento

En el campo de la detección, estamos aprovechando el mismo conjunto de señales responsables de la detección y evaluación de vulnerabilidades en Microsoft Defender para la detección de puntos de conexión y las capacidades [de respuesta](overview-endpoint-detection-response.md).

Dado que es en tiempo real, en cuestión de minutos, verá información de vulnerabilidad a medida que se descubran. El motor captura automáticamente información de varias fuentes de seguridad. De hecho, verás si un software determinado está conectado a una campaña de amenazas en directo. También proporciona un vínculo a un informe de Análisis de amenazas tan pronto como esté disponible.

## <a name="navigate-to-the-software-inventory-page"></a>Vaya a la página Inventario de software

Para obtener acceso a la página de inventario de software, seleccione **Inventario** de software Administración de amenazas y vulnerabilidades menú de navegación en [el portal Microsoft 365 Defender software](portal-overview.md).

Ver software en dispositivos específicos en las páginas de dispositivos individuales de la [lista de dispositivos](machines-view-overview.md).

> [!NOTE]
> Si busca software con la búsqueda global de Microsoft Defender para endpoint, asegúrese de colocar un carácter de subrayado en lugar de un espacio. Por ejemplo, para obtener los mejores resultados de búsqueda, escribiría "windows_10" o "windows_11" en lugar de "Windows 10" o "Windows 11".

## <a name="software-inventory-overview"></a>Introducción al inventario de software

La **página** Inventario de software se abre con una lista de software instalado en la red, incluido el nombre del proveedor, las debilidades encontradas, las amenazas asociadas a ellos, los dispositivos expuestos, el impacto en la puntuación de exposición y las etiquetas.

De forma predeterminada, la vista se filtra mediante **código de producto (CPE): disponible**. También puede filtrar la vista de lista en función de las debilidades encontradas en el software, las amenazas asociadas con ellos y etiquetas como si el software ha llegado al final de la compatibilidad.

:::image type="content" source="images/tvm-software-inventory.png" alt-text="Página de aterrizaje del inventario de software" lightbox="images/tvm-software-inventory.png":::

Seleccione el software que desea investigar. Se abrirá un panel desplegable con una vista más compacta de la información de la página. Puede profundizar en la investigación y seleccionar Abrir **página de software**, o marcar cualquier incoherencia técnica seleccionando **Imprecisión de informe**.

### <a name="software-that-isnt-supported"></a>Software que no es compatible

El software que actualmente no es compatible con amenazas & administración de vulnerabilidades puede estar presente en la página de inventario de software. Como no se admite, solo estarán disponibles datos limitados. Filtra por software no compatible con la opción "No disponible" en la sección "Debilidad".

:::image type="content" source="images/tvm-unsupported-software-filter.png" alt-text="Filtro de software no compatible" lightbox="images/tvm-unsupported-software-filter.png":::

Lo siguiente indica que el software no es compatible:

- El campo Debilidades muestra "No disponible"
- El campo Dispositivos expuestos muestra un guión
- Texto informativo agregado en el panel lateral y en la página de software
- La página de software no tendrá las recomendaciones de seguridad, vulnerabilidades detectadas ni secciones de escala de tiempo de eventos

## <a name="software-inventory-on-devices"></a>Inventario de software en dispositivos

En el panel Microsoft 365 Defender navegación del portal, vaya al **[Inventario de dispositivos](machines-view-overview.md)**. Selecciona el nombre de un dispositivo para abrir la página del dispositivo (como Computer1) y luego  selecciona la pestaña Inventario de software para ver una lista de todo el software conocido presente en el dispositivo. Seleccione una entrada de software específica para abrir el menú desplegable con más información.

El software puede estar visible en el nivel del dispositivo incluso si actualmente no es compatible con Administración de amenazas y vulnerabilidades. Sin embargo, solo estarán disponibles datos limitados. Sabrás si el software no es compatible porque dirá "No disponible" en la columna "Debilidad".

El software sin CPE también puede aparecer en este inventario de software específico del dispositivo.

### <a name="software-evidence"></a>Pruebas de software

Consulta la evidencia de dónde hemos detectado un software específico en un dispositivo desde el registro, el disco o ambos. Puedes encontrarlo en cualquier dispositivo en el inventario de software del dispositivo.

Seleccione un nombre de software para abrir el menú desplegable y busque la sección denominada "Evidencia de software".

:::image type="content" source="images/tvm-software-evidence.png" alt-text="El Windows 10 de la lista de dispositivos" lightbox="images/tvm-software-evidence.png":::

## <a name="software-pages"></a>Páginas de software

Puede ver las páginas de software de varias maneras diferentes:

- Página de inventario de > Seleccione un nombre de software > Página Seleccionar **software abierto** en el control desplegable
- [Página recomendaciones de](tvm-security-recommendation.md) seguridad > Seleccionar una recomendación > Página Seleccionar **software abierto** en el control desplegable
- [Página](threat-and-vuln-mgt-event-timeline.md) escala de tiempo de eventos > Seleccione un evento > Seleccione el nombre de software con hipervínculo (como Visual Studio 2017) en la sección denominada "Componente relacionado" en el control desplegable

 Aparecerá una página completa con todos los detalles de un software específico y la siguiente información:

- Panel lateral con información del proveedor, prevalencia del software en la organización (incluido el número de dispositivos en los que está instalado y dispositivos expuestos que no están parcheados), si está disponible y la vulnerabilidad de vulnerabilidad y el impacto en la puntuación de exposición.
- Visualizaciones de datos que muestran el número y la gravedad de vulnerabilidades y configuraciones erróneas. Además, gráficos con el número de dispositivos expuestos.
- Pestañas que muestran información como:
  - Recomendaciones de seguridad correspondientes para las debilidades y vulnerabilidades identificadas.
  - CVEs con nombre de vulnerabilidades detectadas.
  - Dispositivos que tienen instalado el software (junto con el nombre del dispositivo, el dominio, el sistema operativo y mucho más).
  - Lista de versiones de software (incluido el número de dispositivos en los que está instalada la versión, el número de vulnerabilidades detectadas y los nombres de los dispositivos instalados).

    :::image type="content" source="images/tvm-software-page-example.png" alt-text="The Visual Studio 2017 with the software details, weaknesses, exposed devices, and more" lightbox="images/tvm-software-page-example.png":::

## <a name="report-inaccuracy"></a>Imprecisión de informe

Informe de una imprecisión cuando vea información de vulnerabilidad y resultados de evaluación incorrectos.

1. Abra el control desplegable de software en la página Inventario de software.
2. Seleccione **Informar de imprecisión**.
3. En el panel desplegable, elija un problema desde el que informar:

    - un detalle de software es incorrecto
    - el software no está instalado en ningún dispositivo de mi organización
    - el número de dispositivos instalados o expuestos es incorrecto

4. Rellene los detalles solicitados sobre la imprecisión. Esto variará en función del problema que informe.

![Imprecisión de informe](images/report-inaccuracy-software.png)

5. Seleccione **Enviar**. Sus comentarios se envían inmediatamente a los Administración de amenazas y vulnerabilidades expertos.

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Línea de tiempo de eventos](threat-and-vuln-mgt-event-timeline.md)
- [Ver y organizar la lista de Microsoft Defender para dispositivos de punto de conexión](machines-view-overview.md)
