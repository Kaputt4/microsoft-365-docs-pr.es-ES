---
title: 'Crear y ver excepciones para recomendaciones de seguridad: administración de amenazas y vulnerabilidades'
description: Crear y supervisar excepciones para recomendaciones de seguridad en la administración de amenazas y vulnerabilidades.
keywords: Microsoft Defender para la corrección de endpoint tvm, Microsoft Defender para Endpoint tvm, administración de amenazas y vulnerabilidades, administración de vulnerabilidades de & amenazas, corrección de la administración de vulnerabilidades de &, intune de corrección de tvm, sccm de corrección de tvm
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1af8e5ec9d3aef560c739de5212e8118cf89cd7a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933750"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a>Crear y ver excepciones para recomendaciones de seguridad: administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Como alternativa a una solicitud de corrección cuando una recomendación no es relevante en este momento, puede crear excepciones para las recomendaciones. Si tu organización tiene grupos de dispositivos, podrás tener en cuenta la excepción para grupos de dispositivos específicos. Las excepciones se pueden crear para grupos de dispositivos seleccionados o para todos los grupos de dispositivos pasados y presentes.  

Cuando se crea una excepción para una recomendación, la recomendación no estará activa hasta el final de la duración de la excepción. El estado de recomendación cambiará a **Excepción completa** o **Excepción parcial** (por grupo de dispositivos).

## <a name="permissions"></a>Permisos

Solo los usuarios con permisos de "control de excepciones" pueden administrar excepciones (incluida la creación o la cancelación). [Obtenga más información sobre los roles RBAC](user-roles.md).

![Vista del permiso de control de excepciones.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a>Crear una excepción

Seleccione una recomendación de seguridad para la que quiera crear una excepción y, a continuación, seleccione **Opciones de excepción** y rellene el formulario.  

![Mostrar dónde se encuentra el botón de "opciones de excepción" en un control de control de recomendación de seguridad.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a>Excepción por grupo de dispositivos

Aplica la excepción a todos los grupos de dispositivos actuales o elige grupos de dispositivos específicos. Los grupos de dispositivos futuros no se incluirán en la excepción. Los grupos de dispositivos que ya tienen una excepción no se mostrarán en la lista. Si solo seleccionas determinados grupos de dispositivos, el estado de recomendación cambiará de "activo" a "excepción parcial". El estado cambiará a "excepción completa" si seleccionas todos los grupos de dispositivos.

![Mostrar la lista desplegable de grupos de dispositivos.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a>Vistas filtradas

Si has filtrado por grupo de dispositivos en cualquiera de las páginas de administración de amenazas y vulnerabilidades, solo los grupos de dispositivos filtrados aparecerán como opciones.

Este es el botón para filtrar por grupo de dispositivos en cualquiera de las páginas de administración de amenazas y vulnerabilidades: 

![Mostrar el filtro de grupos de dispositivos seleccionados.](images/tvm-selected-device-groups.png)

Vista de excepción con grupos de dispositivos filtrados:

![Mostrar la lista desplegable de grupos de dispositivos filtrados.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a>Gran número de grupos de dispositivos

Si tu organización tiene más de 20 grupos de dispositivos, selecciona **Editar** junto a la opción grupo de dispositivos filtrado.

![Muestra cómo editar un gran número de grupos.](images/tvm-exception-edit-groups.png)

Aparecerá un menú desplegable donde puedes buscar y elegir los grupos de dispositivos que quieras incluir. Seleccione el icono de marca de verificación debajo de Buscar para activar o desactivar todo.

![Mostrar el menú desplegable de grupos de dispositivos grandes.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a>Excepciones globales

Si tiene permisos de administrador global, podrá crear y cancelar una excepción global. Afecta a todos **los** grupos de dispositivos actuales y futuros de la organización y solo un usuario con permisos similares podría cambiarlo. El estado de recomendación cambiará de "activo" a "excepción completa".

![Mostrar la opción de excepción global.](images/tvm-exception-global.png)

Algunas cosas a tener en cuenta:

- Si una recomendación está en excepción global, las excepciones recién creadas para grupos de dispositivos se suspenderán hasta que la excepción global haya expirado o se haya cancelado. Después de ese punto, las nuevas excepciones de grupo de dispositivos se harán efectivas hasta que expiren.
- Si una recomendación ya tiene excepciones para grupos de dispositivos específicos y se crea una excepción global, la excepción de grupo de dispositivos se suspenderá hasta que expire o la excepción global se cancele antes de que expire.

### <a name="justification"></a>Justificación

Seleccione la justificación de la excepción que necesita presentar en lugar de corregir la recomendación de seguridad en cuestión. Rellene el contexto de justificación y, a continuación, establezca la duración de la excepción.

En la siguiente lista se detallan las justificaciones detrás de las opciones de excepción:

- **Control de terceros:** un producto o software de terceros ya aborda esta recomendación: elegir este tipo de justificación reducirá la puntuación de exposición y aumentará la puntuación segura porque se reduce el riesgo
- **Mitigación alternativa:** una herramienta interna ya aborda esta recomendación: elegir este tipo de justificación reducirá la puntuación de exposición y aumentará la puntuación segura porque el riesgo se reduce.
- **Riesgo aceptado:** el riesgo bajo o la implementación de la recomendación es demasiado caro
- **Corrección planeada (gracia):** ya planeada, pero está a la espera de la ejecución o autorización

## <a name="view-all-exceptions"></a>Ver todas las excepciones

Vaya a la **pestaña Excepciones** de la **página Corrección.** Puede filtrar por justificación, tipo y estado.

 Seleccione una excepción para abrir un control desplegable con más detalles. Las excepciones por grupo de dispositivos tendrán una lista de todos los grupos de dispositivos que cubre la excepción, que puedes exportar. También puede ver la recomendación relacionada o cancelar la excepción.

![Mostrar la pestaña "Excepciones" en la página Corrección.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a>Cómo cancelar una excepción

Para cancelar una excepción, vaya a la **pestaña Excepciones** de la **página** Corrección. Seleccione la excepción.

Para cancelar la excepción para todos los grupos de dispositivos o para una excepción global, selecciona el **botón Cancelar excepción para todos los** grupos de dispositivos. Solo podrás cancelar excepciones para grupos de dispositivos para los que tienes permisos.

![Botón Cancelar.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a>Cancelar la excepción de un grupo de dispositivos específico

Selecciona el grupo de dispositivos específico para cancelar la excepción. Aparecerá un control desplegable para el grupo de dispositivos y puedes seleccionar **Cancelar excepción**.

![Muestra cómo seleccionar un grupo de dispositivos específico.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a>Ver impacto después de aplicar excepciones

En la página Recomendaciones de seguridad, seleccione **Personalizar** columnas y active las **casillas Dispositivos expuestos (después** de excepciones) e **Impacto (después de excepciones).**

![Mostrar opciones de personalizar columnas.](images/tvm-after-exceptions.png)

La columna dispositivos expuestos (después de excepciones) muestra los dispositivos restantes que siguen expuestos a vulnerabilidades después de aplicar excepciones. Las justificaciones de excepción que afectan a la exposición incluyen "control de terceros" y "mitigación alternativa". Otras justificaciones no reducen la exposición de un dispositivo y aún se consideran expuestas.

El impacto (después de las excepciones) muestra el impacto restante en la puntuación de exposición o la puntuación segura después de aplicar las excepciones. Las justificaciones de excepción que afectan a las puntuaciones incluyen "control de terceros" y "mitigación alternativa". Otras justificaciones no reducen la exposición de un dispositivo, por lo que la puntuación de exposición y la puntuación segura no cambian.

![Mostrar las columnas de la tabla.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Corregir puntos vulnerables](tvm-remediation.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Puntuación de exposición](tvm-exposure-score.md)
- [Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)
