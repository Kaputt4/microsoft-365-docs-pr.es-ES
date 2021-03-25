---
title: Crear una carga para el entrenamiento de simulación de ataques
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a crear cargas personalizadas para el aprendizaje de simulación de ataques en Microsoft Defender para Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205190"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Crear una carga personalizada para la simulación de ataques formación

Microsoft ofrece un sólido catálogo de cargas útiles para diversas técnicas de ingeniería social que se emparejan con el entrenamiento de simulación de ataques. Sin embargo, es posible que desee crear cargas personalizadas que funcionen mejor para su organización. En este artículo se describe cómo crear una carga en el aprendizaje de simulación de ataques en Microsoft Defender para Office 365.

Puede crear una carga haciendo clic en **Crear una** carga en la pestaña [Cargas **dedicadas**](https://security.microsoft.com/attacksimulator?viewid=payload) o en el asistente para la creación [de simulación.](attack-simulation-training.md#selecting-a-payload)

El primer paso del asistente le hará seleccionar un tipo de carga. **Actualmente, solo el correo electrónico está disponible.**

A continuación, seleccione una técnica asociada. Vea más detalles sobre técnicas en [Seleccionar una técnica de ingeniería social](attack-simulation-training.md#selecting-a-social-engineering-technique).

En el siguiente paso, asigne un nombre a la carga. Opcionalmente, puede darle una descripción.

## <a name="configure-payload"></a>Configurar carga

Ahora es el momento de crear la carga útil. Introduzca el nombre del remitente, la dirección de correo electrónico y el asunto del correo electrónico en la **sección Detalles del** remitente. Elija una dirección URL de suplantación de identidad de la lista proporcionada. Esta dirección URL se incrustará más adelante en el cuerpo del mensaje.

> [!TIP]
> Puede elegir un correo electrónico interno para el remitente de la carga, lo que hará que la carga aparezca como procedente de otro empleado de la compañía. Esto aumentará la susceptibilidad a la carga útil y ayudará a educar a los empleados sobre el riesgo de amenazas internas.

Hay disponible un editor de texto enriquecido para crear la carga. También puedes importar un correo electrónico que hayas creado previamente. A medida que cree el cuerpo del correo electrónico, aproveche las etiquetas **dinámicas** para personalizar el correo electrónico a sus destinos. Haga clic en El vínculo Suplantación de identidad **(phishing)** para agregar la dirección URL de suplantación de identidad seleccionada anteriormente en el cuerpo del mensaje.

![Vínculo de phishing y etiquetas dinámicas resaltadas en la creación de cargas para Microsoft Defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Para ahorrar tiempo, active la opción para reemplazar todos los vínculos del mensaje **de correo electrónico por el vínculo de suplantación de identidad**.

Una vez que haya terminado de compilar la carga a su gusto, haga clic en **Siguiente**.

## <a name="adding-indicators"></a>Agregar indicadores

Los indicadores ayudarán a los empleados que pasan por la simulación de ataque a comprender la pista que pueden buscar en ataques futuros. Para empezar, haga clic **en Agregar indicador**.

Selecciona un indicador que quieras usar en la lista desplegable. Esta lista está curada para contener las pistas más comunes que aparecen en los mensajes de correo electrónico de suplantación de identidad. Una vez seleccionado, asegúrese de que la ubicación del indicador está establecida en **Desde el cuerpo** del correo electrónico y haga clic en Seleccionar **texto**. Resalte la parte de la carga donde aparece este indicador y haga clic **en Seleccionar**.

![Texto resaltado en el cuerpo del mensaje para agregarlo a un indicador en el entrenamiento de simulación de ataques](../../media/attack-sim-preview-select-text.png)

Agregue una descripción personalizada para describir el indicador y haga clic en el marco de vista previa del indicador para ver una vista previa del indicador. Una vez hecho esto, haga clic **en Agregar**. Repita estos pasos hasta que haya cubierto todos los indicadores de la carga.

## <a name="review-payload"></a>Revisar carga

Ya ha terminado de compilar la carga útil. Ahora es el momento de revisar los detalles y ver una vista previa de la carga. La vista previa incluirá todos los indicadores que haya creado. Puede editar cada parte de la carga desde este paso. Una vez satisfecho, puede **enviar la** carga.

> [!IMPORTANT]
> Las cargas que haya creado tendrán **Tenant** como origen. Al seleccionar cargas, asegúrese de que no filtra **tenant**.

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Crear una simulación de ataque de suplantación de identidad](attack-simulation-training.md)

[Obtenga información a través de la formación de simulación de ataques](attack-simulation-training-insights.md)
