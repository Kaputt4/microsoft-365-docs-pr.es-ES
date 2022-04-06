---
title: Cómo usar Power Automate Connector para configurar un Flow para eventos
ms.reviewer: ''
description: Use Microsoft Defender para endpoint Flow connector para crear un flujo que se desencadenará cada vez que se produzca un nuevo evento en el inquilino.
keywords: flow, api admitidas, api, flujo de Microsoft, consulta, automatización, power automate
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63626978311b679d0f8b520e4b041d92942bd1fd
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468003"
---
# <a name="how-to-use-power-automate-connector-to-set-up-a-flow-for-events"></a>Cómo usar Power Automate Connector para configurar un Flow para eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Automatizar los procedimientos de seguridad es un requisito estándar para todos los centros de operaciones de seguridad (SOC) modernos. Para que los equipos de SOC funcionen de la manera más eficiente, la automatización es imprescindible. Use Microsoft Power Automate para crear flujos de trabajo automatizados y crear una automatización de procedimientos de extremo a extremo en unos minutos. Microsoft Power Automate diferentes conectores creados exactamente para ello.  

Use este artículo para guiarlo en la creación de automatización desencadenadas por un evento, como cuando se crea una nueva alerta en el espacio empresarial. La API de Microsoft Defender tiene un conector Power Automate con muchas capacidades. 

:::image type="content" source="images/api-flow-0.png" alt-text="La página Acciones del portal de Microsoft Defender 365" lightbox="images/api-flow-0.png" :::

> [!NOTE]
> Para obtener más información sobre los requisitos previos de licencias de conectores premium, consulte [Licensing for premium connectors](/power-automate/triggers-introduction#licensing-for-premium-connectors).

## <a name="usage-example"></a>Ejemplo de uso

En el ejemplo siguiente se muestra cómo crear un Flow que se desencadena cada vez que se produce una nueva alerta en el espacio empresarial. Se te guiará para definir qué evento inicia el flujo y qué acción siguiente se realizará cuando se produzca ese desencadenador.  

1. Inicie sesión en [Microsoft Power Automate](https://flow.microsoft.com).

2. Vaya a **Mis flujos Nuevo** \>  \> **automatizado desde en blanco**.

    :::image type="content" source="images/api-flow-1.png" alt-text="El panel Nuevo flujo debajo del elemento de menú Mis flujos en el portal de Microsoft Defender 365" lightbox="images/api-flow-1.png":::

3. Elija un nombre para su Flow, busque "Desencadenadores de ATP de Microsoft Defender" como desencadenador y, a continuación, seleccione el nuevo desencadenador de alertas.

    :::image type="content" source="images/api-flow-2.png" alt-text=" La sección Elegir el desencadenador del flujo en el portal de Microsoft Defender 365" lightbox="images/api-flow-2.png" :::

Ahora tienes un Flow que se desencadena cada vez que se produce una nueva alerta.

:::image type="content" source="images/api-flow-3.png" alt-text="Descripción del desencadenador" lightbox="images/api-flow-3.png":::

Todo lo que necesita hacer ahora es elegir los pasos siguientes.
Por ejemplo, puedes aislar el dispositivo si la gravedad de la alerta es alta y enviar un correo electrónico al respecto.
El desencadenador de alerta solo proporciona el identificador de alerta y el id. de máquina. Puede usar el conector para expandir estas entidades.

### <a name="get-the-alert-entity-using-the-connector"></a>Obtener la entidad Alert mediante el conector

1. Elija **ATP de Microsoft Defender** para el nuevo paso.

2. Elija **Alertas: obtener la API de alerta única**.

3. Establezca el **identificador de alerta** del último paso como **Entrada**.

    :::image type="content" source="images/api-flow-4.png" alt-text="El panel Alertas"  lightbox="images/api-flow-4.png":::

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Aislar el dispositivo si la gravedad de la alerta es alta

1. Agregue **Condition** como un paso nuevo.

2. Compruebe si la gravedad de la alerta **es igual a** Alta.

   Si es así, agrega la **acción Atp de Microsoft Defender:** aislar la acción del equipo con el id. de máquina y un comentario.

    :::image type="content" source="images/api-flow-5.png" alt-text="Panel Acciones"  lightbox="images/api-flow-5.png":::

3. Agregue un nuevo paso para enviar mensajes de correo electrónico sobre la alerta y el aislamiento. Hay varios conectores de correo electrónico que son muy fáciles de usar, como Outlook o Gmail.

4. Guarde el flujo.

También puedes crear un **flujo programado que** ejecute consultas de búsqueda avanzada y mucho más.

## <a name="related-topic"></a>Tema relacionado
- [Microsoft Defender para api de punto de conexión](apis-intro.md)
