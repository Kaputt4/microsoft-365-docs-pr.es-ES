---
title: Crear una carga para la formación de simulación de ataques
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Los administradores pueden obtener información sobre cómo crear cargas personalizadas para la formación de simulación de ataques en Microsoft defender para Office 365.
ms.openlocfilehash: c42090634f6fa9500ae4c3e781b49b607ee928f5
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667548"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Crear una carga personalizada para la simulación de ataques formación

Microsoft ofrece un catálogo de carga sólida para diversas técnicas de ingeniería social que se deben emparejar con la formación de simulación de ataques. Sin embargo, es posible que desee crear cargas personalizadas que funcionen mejor para su organización. En este artículo se describe cómo crear una carga en el aprendizaje de simulación de ataques en Microsoft defender para Office 365.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Puede crear una carga haciendo clic en **crear una carga** , en la [ficha **cargas** dedicadas](https://security.microsoft.com/attacksimulator?viewid=payload) o en el [Asistente para la creación de simulación](attack-simulation-training.md#selecting-a-payload).

El primer paso del asistente tendrá que seleccionar un tipo de carga. **Actualmente, solo está disponible el correo electrónico**.

A continuación, seleccione una técnica asociada. Consulte más detalles sobre las técnicas de [selección de una técnica de ingeniería social](attack-simulation-training.md#selecting-a-social-engineering-technique).

En el siguiente paso, asigne un nombre a su carga. Opcionalmente, puede darle una descripción.

## <a name="configure-payload"></a>Configurar carga

Ahora es el momento de crear su carga. Escriba el nombre del remitente, la dirección de correo electrónico y el asunto del correo electrónico en la sección **detalles del remitente** . Seleccione una dirección URL de suplantación de identidad en la lista proporcionado. Esta dirección URL se incrustará más adelante en el cuerpo del mensaje.

> [!TIP]
> Puede elegir un correo electrónico interno para el remitente de la carga, lo que hará que la carga aparezca como procedente de otro empleado de la compañía. Esto aumentará la susceptibilidad a la carga útil y contribuirá al aprendizaje de los empleados en el riesgo de amenazas internas.

Hay un editor de texto enriquecido disponible para crear su carga. También puede importar un correo electrónico que haya creado previamente. Al crear el cuerpo del correo electrónico, aprovéchese de las **etiquetas dinámicas** para personalizar el correo electrónico en sus objetivos. Haga clic en **vínculo de suplantación de identidad** para agregar la dirección URL de suplantación de identidad seleccionada previamente en el cuerpo del mensaje.

![Vínculo de suplantación de identidad y etiquetas dinámicas resaltadas en creación de carga para Microsoft defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Para ahorrar tiempo, active la opción para **reemplazar todos los vínculos del mensaje de correo electrónico con el vínculo suplantación de identidad (phishing)**.

Una vez que haya terminado de crear la carga, haga clic en **siguiente**.

## <a name="adding-indicators"></a>Adición de indicadores

Los indicadores ayudarán a los empleados que se redirigen a través de la simulación de ataque a comprender la pista que pueden buscar en futuros ataques. Para empezar, haga clic en **Agregar indicador**.

Seleccione un indicador que le gustaría usar en la lista desplegable. Esta lista es creados para contener las pistas más comunes que aparecen en los mensajes de correo electrónico de suplantación de identidad. Una vez seleccionado, asegúrese de que la ubicación del indicador esté configurada en **el cuerpo del correo electrónico** y haga clic en **Seleccionar texto**. Resalte la parte de su carga donde aparece este indicador y haga clic en **seleccionar**.

![Texto resaltado en el cuerpo del mensaje para agregar a un indicador en la simulación de ataques](../../media/attack-sim-preview-select-text.png)

Agregue una descripción personalizada para describir el indicador y haga clic en el marco de vista previa del indicador para ver una vista previa del indicador. Una vez hecho, haga clic en **Agregar**. Repita estos pasos hasta que haya cubierto todos los indicadores de la carga.

## <a name="review-payload"></a>Revisión de la carga

Ya ha terminado de crear la carga útil. Ahora es el momento de revisar los detalles y ver una vista previa de su carga. La vista previa incluirá todos los indicadores que haya creado. Puede editar cada parte de la carga de este paso. Una vez que se haya satisfecho, **envíe** la carga.

> [!IMPORTANT]
> Las cargas que ha creado tendrán **tenant** como origen. Al seleccionar cargas, asegúrese de no filtrar el **espacio empresarial**.
