---
title: Investigar alertas de Microsoft Defender para punto de conexión
description: Use las opciones de investigación para obtener detalles sobre las alertas que afectan a la red, lo que significan y cómo resolverlas.
keywords: investigación, investigación, dispositivos, dispositivo, cola de alertas, panel, dirección IP, archivo, envío, envíos, análisis profundos, escala de tiempo, búsqueda, dominio, dirección URL, IP
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.subservice: mde
ms.openlocfilehash: a2bc1b44cc49e2ded0a3079360436df2880b2f58
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522970"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Investigación de alertas en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatealerts-abovefoldlink)

Investigue las alertas que afectan a la red, comprenda lo que significan y cómo resolverlas.

Seleccione una alerta de la cola de alertas para ir a la página de alertas. Esta vista contiene el título de la alerta, los recursos afectados, el panel lateral de detalles y el artículo de alertas.

En la página de alertas, comience la investigación seleccionando los recursos afectados o cualquiera de las entidades en la vista de árbol del artículo de alertas. El panel de detalles se rellena automáticamente con más información sobre lo que seleccionó. Para ver qué tipo de información puede ver aquí, lea [Revisar alertas en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/review-alerts).

## <a name="investigate-using-the-alert-story"></a>Investigación mediante el artículo de alertas

En el artículo de alerta se detalla por qué se desencadenó la alerta, los eventos relacionados que se produjeron antes y después, así como otras entidades relacionadas.

Las entidades se pueden hacer clic y todas las entidades que no son una alerta se pueden expandir mediante el icono de expansión del lado derecho de la tarjeta de esa entidad. La entidad en foco se indicará mediante una franja azul al lado izquierdo de la tarjeta de esa entidad, con la alerta en el título en el foco al principio.

Expanda las entidades para ver los detalles de un vistazo. Al seleccionar una entidad, se cambiará el contexto del panel de detalles a esta entidad y se le permitirá revisar más información, así como administrar esa entidad. Al seleccionar *...* a la derecha de la tarjeta de entidad, se mostrarán todas las acciones disponibles para esa entidad. Estas mismas acciones aparecen en el panel de detalles cuando esa entidad está en el foco.

> [!NOTE]
> La sección del artículo de alertas puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta que ha seleccionado.

:::image type="content" source="images/alert-story-tree.png" alt-text="un artículo de alerta con una alerta en el foco y algunas tarjetas expandidas" lightbox="images/alert-story-tree.png":::

## <a name="take-action-from-the-details-pane"></a>Realizar una acción desde el panel de detalles

Una vez que haya seleccionado una entidad de interés, el panel de detalles cambiará para mostrar información sobre el tipo de entidad seleccionado, información histórica cuando esté disponible y ofrecer controles para **realizar acciones** en esta entidad directamente desde la página de alertas.

Una vez que haya terminado de investigar, vuelva a la alerta con la que comenzó, marque el estado de la alerta como **Resuelto** y clasifique como **Alerta falsa** o **Alerta verdadera**. La clasificación de alertas ayuda a optimizar esta funcionalidad para proporcionar más alertas verdaderas y menos alertas falsas.

Si la clasifica como una alerta verdadera, también puede seleccionar una determinación, como se muestra en la imagen siguiente.

:::image type="content" source="images/alert-details-resolved-true.png" alt-text="Panel de detalles con una alerta resuelta y la lista desplegable de determinación expandida" lightbox="images/alert-details-resolved-true.png":::

Si experimenta una alerta falsa con una aplicación de línea de negocio, cree una regla de supresión para evitar este tipo de alerta en el futuro.

:::image type="content" source="images/alert-false-suppression-rule.png" alt-text="Acciones y clasificación en el panel de detalles con la regla de supresión resaltada" lightbox="images/alert-false-suppression-rule.png":::

> [!TIP]
> Si experimenta algún problema no descrito anteriormente, use el 🙂 botón para proporcionar comentarios o abrir una incidencia de soporte técnico.

## <a name="related-topics"></a>Temas relacionados

- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigación de un archivo asociado a una alerta de Defender para punto de conexión](investigate-files.md)
- [Investigación de dispositivos en la lista defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigación de una dirección IP asociada a una alerta de Defender para punto de conexión](investigate-ip.md)
- [Investigación de un dominio asociado a una alerta de Defender para punto de conexión](investigate-domain.md)
- [Investigación de una cuenta de usuario en Defender para punto de conexión](investigate-user.md)
