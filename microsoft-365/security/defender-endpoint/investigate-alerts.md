---
title: Investigar alertas de punto de conexión de Microsoft Defender
description: 'Use las opciones de investigación para obtener detalles sobre las alertas que afectan a su red, lo que significan y cómo resolverlas.'
keywords: 'investigar, investigar, dispositivos, dispositivos, cola de alertas, panel, dirección IP, archivo, enviar, envíos, análisis profundo, escala de tiempo, búsqueda, dominio, dirección URL, IP'
ms.prod: m365-security
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
ms.technology: mde
---

# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Investigar alertas en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatealerts-abovefoldlink)

Investigue las alertas que afectan a la red, comprenda lo que significan y cómo resolverlas.

Seleccione una alerta de la cola de alertas para ir a la página de alertas. Esta vista contiene el título de alerta, los activos afectados, el panel lateral de detalles y el artículo de alerta.

En la página de alertas, comience la investigación seleccionando los activos afectados o cualquiera de las entidades en la vista de árbol del artículo de alerta. El panel de detalles se rellena automáticamente con más información sobre lo que ha seleccionado. Para ver qué tipo de información puede ver aquí, lea [Revisar alertas en Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/review-alerts).

## <a name="investigate-using-the-alert-story"></a>Investigar con el artículo de alerta

El artículo de alerta detalla por qué se desencadenó la alerta, los eventos relacionados que sucedieron antes y después, así como otras entidades relacionadas.

Las entidades pueden hacer clic y todas las entidades que no son una alerta se pueden expandir mediante el icono expandir situado a la derecha de la tarjeta de esa entidad. La entidad en el foco se indicará mediante una franja azul al lado izquierdo de la tarjeta de esa entidad, con la alerta en el título en el foco al principio.

Expanda entidades para ver los detalles de un vistazo. Al seleccionar una entidad, se cambia el contexto del panel de detalles a esta entidad y se le permite revisar más información, así como administrar esa entidad. Si selecciona *...* a la derecha de la tarjeta de entidad, se mostrarán todas las acciones disponibles para esa entidad. Estas mismas acciones aparecen en el panel de detalles cuando esa entidad está en el foco.

> [!NOTE]
> La sección de artículo de alerta puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta seleccionada.

:::image type="content" source="images/alert-story-tree.png" alt-text="un artículo de alerta con una alerta en el foco y algunas tarjetas expandida" lightbox="images/alert-story-tree.png":::

## <a name="take-action-from-the-details-pane"></a>Realizar acciones desde el panel de detalles

Una vez que haya seleccionado una entidad de interés, el panel de detalles cambiará para mostrar información sobre el tipo de entidad seleccionada, información histórica cuando esté disponible y ofrecer controles para realizar acciones  en esta entidad directamente desde la página de alerta.

Una vez que haya terminado de investigar, vuelva a la alerta con la que inició, marque el estado de la alerta como **Resuelto** y clasifique como **Alerta** falsa o **Alerta verdadera**. Clasificar alertas ayuda a ajustar esta funcionalidad para proporcionar alertas más verdaderas y menos falsas.

Si la clasifica como una alerta verdadera, también puede seleccionar una determinación, como se muestra en la imagen siguiente.

:::image type="content" source="images/alert-details-resolved-true.png" alt-text="El panel de detalles con una alerta resuelta y la lista desplegable de determinación expandida" lightbox="images/alert-details-resolved-true.png":::

Si experimenta una alerta falsa con una aplicación de línea de negocio, cree una regla de supresión para evitar este tipo de alerta en el futuro.

:::image type="content" source="images/alert-false-suppression-rule.png" alt-text="Acciones y clasificación en el panel de detalles con la regla de supresión resaltada" lightbox="images/alert-false-suppression-rule.png":::

> [!TIP]
> Si tienes algún problema que no se describe anteriormente, usa el 🙂 botón para proporcionar comentarios o abrir un vale de soporte técnico.


## <a name="related-topics"></a>Temas relacionados
- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para puntos de conexión](manage-alerts.md)
- [Investigar un archivo asociado a una alerta de Defender for Endpoint](investigate-files.md)
- [Investigar dispositivos en la lista Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar una dirección IP asociada a una alerta de Defender for Endpoint](investigate-ip.md)
- [Investigar un dominio asociado a una alerta de Defender for Endpoint](investigate-domain.md)
- [Investigar una cuenta de usuario en Defender for Endpoint](investigate-user.md)


