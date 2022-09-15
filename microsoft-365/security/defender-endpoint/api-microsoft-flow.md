---
title: Uso del conector de Power Automate para configurar un flujo para eventos
ms.reviewer: ''
description: Use Microsoft Defender para punto de conexión conector de Flow para crear un flujo que se desencadenará cada vez que se produzca un nuevo evento en el inquilino.
keywords: flow, api admitidas, API, Flujo de Microsoft, consulta, automatización, power automate
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
ms.topic: how-to
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 0b90fd4ecade2f79cac895c61a4a7327de8aaf66
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701970"
---
# <a name="how-to-use-power-automate-connector-to-set-up-a-flow-for-events"></a>Uso del conector de Power Automate para configurar un flujo para eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La automatización de los procedimientos de seguridad es un requisito estándar para cada centro de operaciones de seguridad (SOC) moderno. Para que los equipos de SOC funcionen de la manera más eficaz, la automatización es imprescindible. Use Microsoft Power Automate para ayudarle a crear flujos de trabajo automatizados y a crear una automatización de procedimientos de un extremo a otro en unos minutos. Microsoft Power Automate admite diferentes conectores que se crearon exactamente para eso.  

Use este artículo para guiarle en la creación de automatizaciones desencadenadas por un evento, como cuando se crea una nueva alerta en el inquilino. La API de Microsoft Defender tiene un conector oficial de Power Automate con muchas funcionalidades. 

:::image type="content" source="images/api-flow-0.png" alt-text="Página Acciones del portal de Microsoft Defender 365" lightbox="images/api-flow-0.png" :::

> [!NOTE]
> Para obtener más información sobre los requisitos previos de licencia de conectores Premium, consulte [Licencias para conectores Premium](/power-automate/triggers-introduction#licensing-for-premium-connectors).

## <a name="usage-example"></a>Ejemplo de uso

En el ejemplo siguiente se muestra cómo crear un flujo que se desencadena cada vez que se produce una nueva alerta en el inquilino. Se le guiará en la definición de qué evento inicia el flujo y qué acción siguiente se realizará cuando se produzca ese desencadenador.  

1. Inicie sesión en [Microsoft Power Automate](https://flow.microsoft.com).

2. Vaya a **Mis flujos** \> **Nuevo** \> **automatizado desde blanco**.

    :::image type="content" source="images/api-flow-1.png" alt-text="El panel Nuevo flujo en el elemento de menú Mis flujos del portal de Microsoft Defender 365" lightbox="images/api-flow-1.png":::

3. Elija un nombre para el flujo, busque "Desencadenadores de ATP de Microsoft Defender" como desencadenador y, a continuación, seleccione el nuevo desencadenador alertas.

    :::image type="content" source="images/api-flow-2.png" alt-text=" La sección Elegir el desencadenador del flujo en el portal de Microsoft Defender 365" lightbox="images/api-flow-2.png" :::

Ahora tiene un flujo que se desencadena cada vez que se produce una nueva alerta.

:::image type="content" source="images/api-flow-3.png" alt-text="Descripción del desencadenador" lightbox="images/api-flow-3.png":::

Todo lo que necesita hacer ahora es elegir los pasos siguientes.
Por ejemplo, puede aislar el dispositivo si la gravedad de la alerta es alta y enviar un correo electrónico al respecto.
El desencadenador de alerta proporciona solo el identificador de alerta y el identificador de máquina. Puede usar el conector para expandir estas entidades.

### <a name="get-the-alert-entity-using-the-connector"></a>Obtención de la entidad Alert mediante el conector

1. Elija **ATP de Microsoft Defender** para el nuevo paso.

2. Elija **Alertas: Obtener api de alerta única**.

3. Establezca el **identificador de alerta** del último paso como **Entrada**.

    :::image type="content" source="images/api-flow-4.png" alt-text="Panel Alertas"  lightbox="images/api-flow-4.png":::

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Aislar el dispositivo si la gravedad de la alerta es Alta

1. Agregue **Condición** como nuevo paso.

2. Compruebe si la gravedad de la alerta **es igual a** Alta.

   Si es así, agregue la acción **ATP de Microsoft Defender: Aislar la máquina** con el id. de equipo y un comentario.

    :::image type="content" source="images/api-flow-5.png" alt-text="Panel Acciones"  lightbox="images/api-flow-5.png":::

3. Agregue un nuevo paso para enviar correo electrónico sobre la alerta y el aislamiento. Hay varios conectores de correo electrónico que son muy fáciles de usar, como Outlook o Gmail.

4. Guarde el flujo.

También puede crear un flujo **programado** que ejecute consultas de búsqueda avanzada y mucho más.

## <a name="related-topic"></a>Tema relacionado
- [API de Microsoft Defender para punto de conexión](apis-intro.md)
