---
title: Detección y bloqueo de aplicaciones potencialmente no deseadas con Microsoft Defender para punto de conexión en Linux
description: Detecte y bloquee aplicaciones potencialmente no deseadas (PUA) mediante Microsoft Defender para punto de conexión en Linux.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, pua, pus
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 004a9d7af09e8a2abb656c29db558d797173edcd
ms.sourcegitcommit: 612ce4d15d8a2fdbf7795393b50af477d81b6139
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65663610"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Detección y bloqueo de aplicaciones potencialmente no deseadas con Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

La característica de protección de aplicaciones potencialmente no deseadas (PUA) de Defender para punto de conexión en Linux puede detectar y bloquear archivos PUA en los puntos de conexión de la red.

Estas aplicaciones no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente a su rendimiento o uso. PUA también puede hacer referencia a aplicaciones que se consideran de mala reputación.

Estas aplicaciones pueden aumentar el riesgo de que la red se infecte con malware, hacer que las infecciones de malware sean más difíciles de identificar y pueden desperdiciar recursos de TI en la limpieza de las aplicaciones.

## <a name="how-it-works"></a>Cómo funciona

Defender para punto de conexión en Linux puede detectar y notificar archivos PUA. Cuando se configura en modo de bloqueo, los archivos PUA se mueven a la cuarentena.

Cuando se detecta una PUA en un punto de conexión, Defender para punto de conexión en Linux mantiene un registro de la infección en el historial de amenazas. El historial se puede visualizar desde el portal de Microsoft 365 Defender o a través de la `mdatp` herramienta de línea de comandos. El nombre de la amenaza contendrá la palabra "Application".

## <a name="configure-pua-protection"></a>Configuración de la protección de PUA

La protección pua en Defender para punto de conexión en Linux se puede configurar de una de las siguientes maneras:

- **Desactivado**: la protección pua está deshabilitada.
- **Auditoría**: los archivos PUA se notifican en los registros de productos, pero no en Microsoft 365 Defender. No hay registro de la infección se almacena en el historial de amenazas y no se realiza ninguna acción por el producto.
- **Bloquear**: los archivos PUA se notifican en los registros de productos y en Microsoft 365 Defender. Un registro de la infección se almacena en el historial de amenazas y la acción es tomada por el producto.

> [!WARNING]
> De forma predeterminada, la protección pua está configurada en modo **auditoría** .

Puede configurar cómo se controlan los archivos PUA desde la línea de comandos o desde la consola de administración.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Use la herramienta de línea de comandos para configurar la protección pua:

En Terminal, ejecute el siguiente comando para configurar la protección pua:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Use la consola de administración para configurar la protección pua:

En la empresa, puede configurar la protección de PUA desde una consola de administración, como Puppet o Ansible, de forma similar a cómo se configuran otras opciones de configuración del producto. Para obtener más información, consulte la sección [Configuración del tipo de amenaza](linux-preferences.md#threat-type-settings) del artículo [Establecer preferencias para Defender para punto de conexión en Linux](linux-preferences.md) .

## <a name="related-articles"></a>Artículos relacionados

- [Establecimiento de preferencias para Defender para punto de conexión en Linux](linux-preferences.md)
