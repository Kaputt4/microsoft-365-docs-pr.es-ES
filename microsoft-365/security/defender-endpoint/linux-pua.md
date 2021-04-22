---
title: Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para Endpoint en Linux
description: Detectar y bloquear aplicaciones potencialmente no deseadas (PUA) con Microsoft Defender para endpoint en Linux.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, pua, pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7ec3399129cc65d75b464f5d5f56bb11250ccaf2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933162"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para Endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

La característica de protección de aplicaciones potencialmente no deseadas (PUA) en Defender para Endpoint en Linux puede detectar y bloquear archivos PUA en puntos de conexión de la red.

Estas aplicaciones no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente a su rendimiento o uso. PUA también puede hacer referencia a aplicaciones que se consideran de mala reputación.

Estas aplicaciones pueden aumentar el riesgo de que la red se infecte con malware, hacer que las infecciones de malware sean más difíciles de identificar y pueden desperdiciar recursos de TI en la limpieza de las aplicaciones.

## <a name="how-it-works"></a>Cómo funciona

Defender para endpoint en Linux puede detectar e informar de archivos PUA. Cuando se configura en modo de bloqueo, los archivos PUA se mueven a la cuarentena.

Cuando se detecta una PUA en un punto de conexión, Defender for Endpoint en Linux mantiene un registro de la infección en el historial de amenazas. El historial se puede visualizar desde el portal del Centro de seguridad de Microsoft Defender o a través de la herramienta `mdatp` de línea de comandos. El nombre de la amenaza contendrá la palabra "Application".

## <a name="configure-pua-protection"></a>Configurar la protección de LA PUA

La protección de PUA en Defender para Endpoint en Linux se puede configurar de una de las siguientes maneras:

- **Desactivado:** la protección de LA PUA está deshabilitada.
- **Auditoría:** los archivos PUA se notifican en los registros del producto, pero no en el Centro de seguridad de Microsoft Defender. No se almacena ningún registro de la infección en el historial de amenazas y el producto no toma ninguna acción.
- **Bloquear:** los archivos PUA se notifican en los registros del producto y en el Centro de seguridad de Microsoft Defender. Un registro de la infección se almacena en el historial de amenazas y el producto toma medidas.

>[!WARNING]
>De forma predeterminada, la protección pua está configurada en **modo auditoría.**

Puede configurar cómo se controlan los archivos PUA desde la línea de comandos o desde la consola de administración.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Use la herramienta de línea de comandos para configurar la protección pua:

En Terminal, ejecute el siguiente comando para configurar la protección pua:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Use la consola de administración para configurar la protección pua:

En su empresa, puede configurar la protección de PUA desde una consola de administración, como Puppet o Ansible, de forma similar a la configuración de otros productos. Para obtener más información, consulta la sección Configuración del [tipo](linux-preferences.md#threat-type-settings) de amenaza del artículo [Establecer preferencias para Defender para Endpoint en Linux.](linux-preferences.md)

## <a name="related-articles"></a>Artículos relacionados

- [Establecer preferencias para Defender para Endpoint en Linux](linux-preferences.md)
