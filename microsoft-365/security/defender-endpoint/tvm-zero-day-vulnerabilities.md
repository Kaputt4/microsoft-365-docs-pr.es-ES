---
title: 'Mitigar vulnerabilidades de día cero: administración de amenazas y vulnerabilidades'
description: Obtenga información sobre cómo encontrar y mitigar vulnerabilidades de día cero en su entorno mediante la administración de amenazas y vulnerabilidades.
keywords: Vulnerabilidades de Microsoft Defender para Endpoint tvm día cero, tvm, administración de vulnerabilidades & amenazas, cero día, 0 días, mitigar vulnerabilidades de 0 días, CVE vulnerable
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be508e646a67f01887814a0e72170e438ee86212
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933066"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a>Mitigar vulnerabilidades de día cero: administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Una vulnerabilidad de día cero es una vulnerabilidad divulgada públicamente para la que no se han publicado revisiones oficiales ni actualizaciones de seguridad. Las vulnerabilidades de día cero suelen tener niveles de gravedad altos y se aprovechan activamente.

La administración de amenazas y vulnerabilidades solo mostrará vulnerabilidades de día cero de las que tenga información.

## <a name="find-information-about-zero-day-vulnerabilities"></a>Buscar información sobre vulnerabilidades de día cero

Una vez que se haya encontrado una vulnerabilidad de día cero, la información sobre ella se transmitirá a través de las siguientes experiencias en el Centro de seguridad de Microsoft Defender.

### <a name="threat-and-vulnerability-management-dashboard"></a>Panel de administración de amenazas y vulnerabilidades

Busque recomendaciones con una etiqueta de día cero en la tarjeta "Recomendaciones de seguridad principales".

![Recomendaciones principales con una etiqueta de día cero.](images/tvm-zero-day-top-security-recommendations.png)

Busca el software superior con la etiqueta de día cero en la tarjeta "Software vulnerable superior".

![Software vulnerable superior con una etiqueta de día cero.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a>Página Puntos débiles

Busque la vulnerabilidad de día cero con nombre junto con una descripción y detalles.

- Si esta vulnerabilidad tiene asignado un identificador CVE, verás la etiqueta de día cero junto al nombre CVE.

- Si esta vulnerabilidad no tiene ningún identificador CVE asignado, lo encontrarás con un nombre interno y temporal que tenga el aspecto de "TVM-XXXX-XXXX". El nombre se actualizará una vez que se haya asignado un identificador CVE oficial, pero el nombre interno anterior aún se podrá buscar y se encontrará en el panel lateral.

![Ejemplo de día cero para CVE-2020-17087 en la página de puntos débiles.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a>Página de inventario de software

Busque software con la etiqueta de día cero. Filtra por la etiqueta "día cero" para ver solo el software con vulnerabilidades de día cero.

![Ejemplo de día cero de Windows Server 2016 en la página de inventario de software.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a>Página de software

Busque una etiqueta de día cero para cada software afectado por la vulnerabilidad de día cero.

![Ejemplo de día cero para la página de software de Windows Server 2016.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a>Página recomendaciones de seguridad

Vea sugerencias claras sobre las opciones de corrección y mitigación, incluidas las soluciones alternativas si existen. Filtre por la etiqueta "día cero" para ver solo las recomendaciones de seguridad que abordan las vulnerabilidades de día cero.

Si hay software con una vulnerabilidad de día cero y vulnerabilidades adicionales que solucionar, tendrás una recomendación sobre todas las vulnerabilidades.

![Ejemplo de día cero de Windows Server 2016 en la página recomendaciones de seguridad.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a>Abordar vulnerabilidades de día cero

Vaya a la página recomendación de seguridad y seleccione una recomendación con un día cero. Se abrirá un flyout con información sobre el día cero y otras vulnerabilidades de ese software.

Habrá un vínculo a las opciones de mitigación y soluciones alternativas si están disponibles. Las soluciones alternativas pueden ayudar a reducir el riesgo que representa esta vulnerabilidad de día cero hasta que se pueda implementar una revisión o actualización de seguridad.

Abra las opciones de corrección y elija el tipo de atención. Se recomienda una opción de corrección "necesaria para la atención" para las vulnerabilidades de día cero, ya que aún no se ha publicado una actualización. No podrá seleccionar una fecha de vencimiento, ya que no hay ninguna acción específica que realizar. Si hay vulnerabilidades más antiguas para este software que desea corregir, puede invalidar la opción de corrección "atención requerida" y elegir "actualizar".

![Ejemplo de flyout de día cero de Windows Server 2016 en la página de recomendaciones de seguridad.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a>Realizar un seguimiento de las actividades de corrección de día cero

Vaya a la página De corrección de la administración de amenazas y [vulnerabilidades](tvm-remediation.md) para ver el elemento de actividad de corrección. Si elige la opción de corrección "atención requerida", no habrá ninguna barra de progreso, estado de vale o fecha de vencimiento, ya que no hay ninguna acción real que podamos supervisar. Puede filtrar por tipo de corrección, como "actualización de software" o "atención necesaria", para ver todos los elementos de actividad de la misma categoría.

## <a name="patching-zero-day-vulnerabilities"></a>Revisión de vulnerabilidades de día cero

Cuando se libera una revisión para el día cero, la recomendación se cambiará a "Actualizar" y una etiqueta azul junto a ella que diga "Nueva actualización de seguridad para el día cero". Ya no se considerará como un día cero, la etiqueta de día cero se quitará de todas las páginas.

![Recomendación para "Actualizar Microsoft Windows 10" con nueva etiqueta de revisión.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Panel](tvm-dashboard-insights.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Inventario de software](tvm-software-inventory.md)
- [Vulnerabilidades de mi organización](tvm-weaknesses.md)
