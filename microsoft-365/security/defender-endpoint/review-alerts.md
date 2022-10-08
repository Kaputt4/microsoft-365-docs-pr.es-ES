---
title: Revisión de alertas en Microsoft Defender para punto de conexión
description: Revise la información de alertas, incluido un artículo de alerta visualizado y los detalles de cada paso de la cadena.
keywords: incidente, incidentes, máquinas, dispositivos, usuarios, alertas, alertas, investigaciones, gráficos, pruebas
ms.service: microsoft-365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.date: 5/1/2020
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e6add9d91bf91be0d0a7588a2fcef3e632937ba1
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232658"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>Revisión de alertas en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-managealerts-abovefoldlink)

La página de alertas de Microsoft Defender para punto de conexión proporciona contexto completo a la alerta, mediante la combinación de señales de ataque y alertas relacionadas con la alerta seleccionada, para construir un artículo de alerta detallado.

Evalúe, investigue y tome medidas eficaces rápidamente en las alertas que afectan a su organización. Comprenda por qué se desencadenaron y su impacto desde una ubicación. Obtenga más información en esta introducción.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>Introducción a una alerta

Al seleccionar el nombre de una alerta en Defender para punto de conexión, aparecerá en su página de alerta. En la página de alertas, toda la información se mostrará en el contexto de la alerta seleccionada. Cada página de alerta consta de 4 secciones:

1. **El título de la alerta** muestra el nombre de la alerta y está allí para recordarle qué alerta inició la investigación actual, independientemente de lo que haya seleccionado en la página.
2. [**Los recursos afectados**](#review-affected-assets) muestran tarjetas de dispositivos y usuarios afectados por esta alerta en las que se puede hacer clic para obtener más información y acciones.
3. El **artículo de alertas** muestra todas las entidades relacionadas con la alerta, interconectadas por una vista de árbol. La alerta del título será la que esté centrada en la primera vez que aterrice en la página de la alerta seleccionada. Las entidades del artículo de alertas se pueden expandir y hacer clic para proporcionar información adicional y acelerar la respuesta, ya que le permiten realizar acciones directamente en el contexto de la página de alertas. Use el artículo de alertas para iniciar la investigación. Obtenga información sobre cómo [investigar alertas en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/investigate-alerts).
4. En el **panel de detalles** se mostrarán los detalles de la alerta seleccionada al principio, con detalles y acciones relacionadas con esta alerta. Si selecciona cualquiera de los recursos o entidades afectados en el artículo de alertas, el panel de detalles cambiará para proporcionar información contextual y acciones para el objeto seleccionado.

Tenga en cuenta el estado de detección de la alerta.

- Impedido: se evitó el intento de acción sospechosa. Por ejemplo, un archivo no se escribió en el disco o se ejecutó.

  :::image type="content" source="images/detstat-prevented.png" alt-text="Página que muestra la prevención de una amenaza" lightbox="images/detstat-prevented.png":::

- Bloqueado: se ejecutó un comportamiento sospechoso y, a continuación, se bloqueó. Por ejemplo, se ejecutó un proceso, pero como posteriormente mostró comportamientos sospechosos, el proceso se finalizó.

  :::image type="content" source="images/detstat-blocked.png" alt-text="Página que muestra el bloqueo de una amenaza" lightbox="images/detstat-blocked.png":::

- Detectado: se detectó un ataque y posiblemente sigue activo.

  :::image type="content" source="images/detstat-detected.png" alt-text="Página que muestra la detección de una amenaza" lightbox="images/detstat-detected.png":::

A continuación, también puede revisar los *detalles de la investigación automatizada* en el panel de detalles de la alerta para ver qué acciones ya se han realizado, así como leer la descripción de la alerta para las acciones recomendadas.

:::image type="content" source="images/alert-air-and-alert-description.png" alt-text="Panel de detalles con la descripción de la alerta y las secciones de investigación automática resaltadas" lightbox="images/alert-air-and-alert-description.png":::

Otra información disponible en el panel de detalles cuando se abre la alerta incluye técnicas de MITRE, origen y detalles contextuales adicionales.

> [!NOTE]
> Si ve un estado de *alerta de tipo de alerta no compatible* , significa que las funcionalidades de investigación automatizada no pueden recoger esa alerta para ejecutar una investigación automatizada. Sin embargo, puede [investigar estas alertas manualmente](../defender/investigate-incidents.md#alerts).

## <a name="review-affected-assets"></a>Revisión de los recursos afectados

Al seleccionar un dispositivo o una tarjeta de usuario en las secciones de recursos afectados, se cambiará a los detalles del dispositivo o usuario en el panel de detalles.

- **En el caso de los dispositivos**, el panel de detalles mostrará información sobre el propio dispositivo, como dominio, sistema operativo e IP. También están disponibles las alertas activas y los usuarios que han iniciado sesión en ese dispositivo. Puede realizar una acción inmediata si aísla el dispositivo, restringe la ejecución de la aplicación o ejecuta un examen antivirus. Como alternativa, puede recopilar un paquete de investigación, iniciar una investigación automatizada o ir a la página del dispositivo para investigar desde el punto de vista del dispositivo.

   :::image type="content" source="images/device-page-details.png" alt-text="Panel de detalles cuando se selecciona un dispositivo" lightbox="images/device-page-details.png":::

- **Para los usuarios**, el panel de detalles mostrará información detallada del usuario, como el nombre SAM y el SID del usuario, así como los tipos de inicio de sesión realizados por este usuario y las alertas e incidentes relacionados con él. Puede seleccionar *Abrir página de usuario* para continuar la investigación desde el punto de vista de ese usuario.

   :::image type="content" source="images/user-page-details.png" alt-text="Panel de detalles cuando se selecciona un usuario" lightbox="images/user-page-details.png":::

## <a name="related-topics"></a>Temas relacionados

- [Visualización y organización de la cola de incidentes](view-incidents-queue.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
