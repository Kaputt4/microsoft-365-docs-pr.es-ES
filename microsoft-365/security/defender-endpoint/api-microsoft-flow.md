---
title: Conector de Atp Flow de Microsoft Defender
ms.reviewer: ''
description: Use el conector de flujo de ATP de Microsoft Defender para automatizar la seguridad y crear un flujo que se desencadenará cada vez que se produzca una nueva alerta en el inquilino.
keywords: flow, api admitidas, api, flujo de Microsoft, consulta, automatización
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6fd210ddfb8e3ab6e4f1f4ffc0635c8b813e3a07
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163392"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (anteriormente Microsoft Flow) y Azure Functions

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Automatizar los procedimientos de seguridad es un requisito estándar para todos los centros de operaciones de seguridad modernos. La falta de ciberdelincuntes profesionales obliga a SOC a trabajar de la manera más eficiente y la automatización es una obligación. Microsoft Power Automate admite diferentes conectores creados exactamente para ello. Puede crear una automatización de procedimientos de extremo a extremo en unos minutos.

La API de Microsoft Defender tiene un conector de flujo oficial con muchas capacidades.

![Imagen de las credenciales de edición1](images/api-flow-0.png)

> [!NOTE]
> Para obtener más información acerca de los requisitos previos de licencias de conectores premium, vea [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).


## <a name="usage-example"></a>Ejemplo de uso

En el ejemplo siguiente se muestra cómo crear un flujo que se desencadena cada vez que se produce una nueva alerta en el espacio empresarial.

1. Inicie sesión en [Microsoft Power Automate](https://flow.microsoft.com).

2. Vaya a **Mis flujos**  >  **Nuevo**  >  **automatizado desde en blanco**.

    ![Imagen de las credenciales de edición2](images/api-flow-1.png)

3. Elija un nombre para el flujo, busque "Desencadenadores de ATP de Microsoft Defender" como desencadenador y, a continuación, seleccione el nuevo desencadenador de alertas.

    ![Imagen de las credenciales de edición3](images/api-flow-2.png)

Ahora tienes un flujo que se desencadena cada vez que se produce una nueva alerta.

![Imagen de las credenciales de edición4](images/api-flow-3.png)

Todo lo que necesita hacer ahora es elegir los pasos siguientes.
Por ejemplo, puedes aislar el dispositivo si la gravedad de la alerta es alta y enviar un correo electrónico al respecto.
El desencadenador de alerta solo proporciona el identificador de alerta y el id. de máquina. Puede usar el conector para expandir estas entidades.

### <a name="get-the-alert-entity-using-the-connector"></a>Obtener la entidad Alert mediante el conector

1. Elija **ATP de Microsoft Defender** para el nuevo paso.

2. Choose **Alerts - Get single alert API**.

3. Establezca el **identificador de alerta** del último paso como **Input**.

    ![Imagen de las credenciales de edición5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Aislar el dispositivo si la gravedad de la alerta es alta

1. Agregue **Condition** como un paso nuevo.

2. Compruebe si la gravedad de la alerta **es igual a** Alta.

   Si es así, agrega la **acción Atp de Microsoft Defender:** aislar la acción del equipo con el id. de máquina y un comentario.

    ![Imagen de las credenciales de edición6](images/api-flow-5.png)

3. Agregue un nuevo paso para enviar mensajes de correo electrónico sobre la alerta y el aislamiento. Hay varios conectores de correo electrónico que son muy fáciles de usar, como Outlook o Gmail.

4. Guarde el flujo.

También puedes crear un **flujo programado que** ejecute consultas de búsqueda avanzada y mucho más.

## <a name="related-topic"></a>Tema relacionado
- [Microsoft Defender para api de punto de conexión](apis-intro.md)
