---
title: Cómo usar Power Automate Connector para configurar un Flow para eventos
ms.reviewer: ''
description: Use Microsoft Defender para endpoint Flow connector para crear un flujo que se desencadenará cada vez que se produzca un nuevo evento en el espacio empresarial.
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
ms.openlocfilehash: fdb3876de6f74c95858dee01aba9615198282b16
ms.sourcegitcommit: bcea69bacd1b48827bd60af2880909593a1609a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2022
ms.locfileid: "62202202"
---
# <a name="how-to-use-power-automate-connector-to-set-up-a-flow-for-events"></a>Cómo usar Power Automate Connector para configurar un Flow para eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


Automatizar los procedimientos de seguridad es un requisito estándar para todos los centros de operaciones de seguridad (SOC) modernos. Para que los equipos de SOC funcionen de la manera más eficiente, la automatización es imprescindible. Use Microsoft Power Automate para ayudarle a crear flujos de trabajo automatizados y crear una automatización de procedimientos de un extremo a otro en unos minutos. Microsoft Power Automate diferentes conectores creados exactamente para ello.  

Use este artículo para guiarlo en la creación de automatización desencadenada por un evento, como cuando se crea una nueva alerta en el espacio empresarial. La API de Microsoft Defender tiene un Power Automate Connector con muchas funcionalidades. 



:::image type="content" alt-text="Imagen de las credenciales de edición1." source="images/api-flow-0.png":::

> [!NOTE]
> Para obtener más información acerca de los requisitos previos de licencias de conectores premium, vea [Licensing for premium connectors](/power-automate/triggers-introduction#licensing-for-premium-connectors).


## <a name="usage-example"></a>Ejemplo de uso

En el ejemplo siguiente se muestra cómo crear un Flow que se desencadena cada vez que se produce una nueva alerta en el espacio empresarial. Se te guiará para definir qué evento inicia el flujo y qué acción siguiente se realizará cuando se produzca ese desencadenador.  

1. Inicie sesión en [Microsoft Power Automate](https://flow.microsoft.com).

2. Vaya a **Mis flujos** \> **Nuevo** \> **automatizado desde en blanco**.

    :::image type="content" alt-text="Imagen de las credenciales de edición2." source="images/api-flow-1.png":::

3. Elija un nombre para su Flow, busque "Desencadenadores de ATP de Microsoft Defender" como desencadenador y, a continuación, seleccione el nuevo desencadenador de alertas.

    :::image type="content" alt-text="Imagen de las credenciales de edición3." source="images/api-flow-2.png":::

Ahora tiene un Flow que se desencadena cada vez que se produce una nueva alerta.

:::image type="content" alt-text="Imagen de las credenciales de edición4." source="images/api-flow-3.png":::

Todo lo que necesita hacer ahora es elegir los pasos siguientes.
Por ejemplo, puedes aislar el dispositivo si la gravedad de la alerta es alta y enviar un correo electrónico al respecto.
El desencadenador de alerta solo proporciona el identificador de alerta y el id. de máquina. Puede usar el conector para expandir estas entidades.

### <a name="get-the-alert-entity-using-the-connector"></a>Obtener la entidad Alert mediante el conector

1. Elija **ATP de Microsoft Defender** para el nuevo paso.

2. Choose **Alerts - Get single alert API**.

3. Establezca el **identificador de alerta** del último paso como **Input**.

    :::image type="content" alt-text="Imagen de las credenciales de edición5." source="images/api-flow-4.png" lightbox="images/api-flow-4.png":::

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Aislar el dispositivo si la gravedad de la alerta es alta

1. Agregue **Condition** como un paso nuevo.

2. Compruebe si la gravedad de la alerta **es igual a** Alta.

   Si es así, agrega la **acción Atp de Microsoft Defender:** aislar la acción del equipo con el id. de máquina y un comentario.

    :::image type="content" alt-text="Imagen de las credenciales de edición6." source="images/api-flow-5.png" lightbox="images/api-flow-5.png":::

3. Agregue un nuevo paso para enviar mensajes de correo electrónico sobre la alerta y el aislamiento. Hay varios conectores de correo electrónico que son muy fáciles de usar, como Outlook o Gmail.

4. Guarde el flujo.

También puedes crear un **flujo programado que** ejecute consultas de búsqueda avanzada y mucho más.

## <a name="related-topic"></a>Tema relacionado
- [Microsoft Defender para api de punto de conexión](apis-intro.md)
