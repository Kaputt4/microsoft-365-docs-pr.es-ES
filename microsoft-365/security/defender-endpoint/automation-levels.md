---
title: Niveles de automatización en la investigación y corrección automatizadas
description: Obtenga información general sobre los niveles de automatización y cómo funcionan en Microsoft Defender para endpoint
keywords: automated, investigation, level, Microsoft Defender for Endpoint
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.date: 10/22/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: e440675a46a4340e2f659b23a31b19dbab33d2c0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328167"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Niveles de automatización en las funcionalidades automatizadas de investigación y corrección

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Las capacidades de investigación y corrección automatizadas (AIR) en Microsoft Defender para endpoint se pueden configurar en uno de los varios niveles de automatización. El nivel de automatización afecta a si las acciones de corrección siguientes a las investigaciones de AIR se toman automáticamente o solo después de su aprobación.

- *La automatización completa* (recomendada) significa que las acciones de corrección se toman automáticamente en artefactos determinados como malintencionados.
- *Semi-automation* means some remediation actions are taken automatically, but other remediation actions await approval before being taken. (Vea la tabla en [Niveles de automatización](#levels-of-automation)).
- Todas las acciones de corrección, ya sean pendientes o completadas, se realiza un seguimiento en el Centro de acciones ([https://security.microsoft.com](https://security.microsoft.com)).

> [!TIP]
> Para obtener los mejores resultados, se recomienda usar la automatización completa al [configurar AIR](configure-automated-investigations-remediation.md). Los datos recopilados y analizados durante el año pasado muestran que los clientes que usan la automatización completa han quitado un 40 % más de muestras de malware de elevada confianza que los clientes que usan niveles de automatización más bajos. La automatización completa puede ayudar a liberar los recursos de las operaciones de seguridad para centrarse más en sus iniciativas estratégicas.

## <a name="levels-of-automation"></a>Niveles de automatización

En la tabla siguiente se describe cada nivel de automatización y cómo funciona.

<br>

****

|Nivel de automatización|Descripción|
|---|---|
|**Completa: corregir las amenazas automáticamente** <br> (también denominada automatización *completa*)|Con la automatización completa, las acciones de corrección se realizan automáticamente. Todas las acciones de corrección que se toman se pueden ver en el [Centro de acciones](auto-investigation-action-center.md) de la **pestaña** Historial. Si es necesario, se puede deshacer una acción de corrección. <p> **_Se recomienda_* la automatización completa y se selecciona de forma predeterminada para los inquilinos que se crearon el 16 de agosto de 2020 o después de él con Microsoft Defender para endpoint, sin que aún se haya definido ningún grupo de dispositivos.*|
|**Semi: requerir aprobación para cualquier corrección** <br> (también denominada *semi automatización*)|Con este nivel de semi automatización, se requiere la aprobación para *cualquier* acción de corrección. Estas acciones pendientes se pueden ver y aprobar en el [Centro de acciones](auto-investigation-action-center.md), en la **pestaña** Pendiente. <p> *Este nivel de semi automatización está seleccionado de forma predeterminada para los inquilinos que se crearon antes del 16 de agosto de 2020 con Microsoft Defender para endpoint, sin que se haya definido ningún grupo de dispositivos.*|
|**Semi: requerir aprobación para la corrección de carpetas principales** <br> (también un tipo de *semi automatización*)|Con este nivel de semiautomización, se requiere la aprobación para las acciones de corrección necesarias en archivos o ejecutables que se encuentran en carpetas principales. Las carpetas principales incluyen directorios del sistema operativo, como **el Windows** (`\windows\*`). <p> Las acciones de corrección se pueden realizar automáticamente en archivos o archivos ejecutables que se encuentran en otras carpetas (no principales). <p> Las acciones pendientes de archivos o ejecutables en carpetas principales se pueden ver y aprobar en el Centro [de acciones,](auto-investigation-action-center.md) en la **pestaña** Pendiente. <p> Las acciones realizadas en archivos o ejecutables de otras carpetas se pueden ver en el Centro [de acciones,](auto-investigation-action-center.md) en la **pestaña** Historial.|
|**Semi: requerir aprobación para la corrección de carpetas no temporales** <br> (también un tipo de *semi automatización*)|Con este nivel de semiautomización, se requiere la aprobación para las acciones de corrección necesarias en archivos o ejecutables *que no se* encuentran en carpetas temporales. <p> Las carpetas temporales pueden incluir los siguientes ejemplos: <ul><li>`\users\*\appdata\local\temp\*`</li><li>`\documents and settings\*\local settings\temp\*`</li><li>`\documents and settings\*\local settings\temporary\*`</li><li>`\windows\temp\*`</li><li>`\users\*\downloads\*`</li><li>`\program files\`</li><li>`\program files (x86)\*`</li><li>`\documents and settings\*\users\*`</li></ul> <p> Las acciones de corrección se pueden realizar automáticamente en archivos o archivos ejecutables que se encuentran en carpetas temporales. <p> Las acciones pendientes de archivos o ejecutables que no están en carpetas temporales se pueden ver y aprobar en el Centro de [acciones, en](auto-investigation-action-center.md) la **pestaña** Pendiente. <p> Las acciones realizadas en archivos o ejecutables en carpetas temporales se pueden ver y aprobar en el Centro de [acciones, en](auto-investigation-action-center.md) la **pestaña** Historial.|
|**Sin respuesta automatizada** <br> (también se conoce como *sin automatización*)|Sin automatización, la investigación automatizada no se ejecuta en los dispositivos de la organización. Como resultado, no se toman medidas de corrección ni están pendientes como resultado de una investigación automatizada. Sin embargo, otras características de protección contra amenazas, como la protección contra aplicaciones potencialmente no deseadas [, pueden](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) estar en vigor, en función de cómo se configuren el antivirus y las características de protección de próxima generación. <p> ***No se *recomienda usar* la opción sin** automatización, ya que reduce la posición de seguridad de los dispositivos de la organización. [Considere la posibilidad de configurar el nivel de automatización en la automatización completa (o al menos la semi automatización).](/microsoft-365/security/defender-endpoint/machine-groups).|
|

## <a name="important-points-about-automation-levels"></a>Puntos importantes sobre los niveles de automatización

- La automatización completa ha demostrado ser confiable, eficiente y segura, y se recomienda para todos los clientes. La automatización completa libera los recursos de seguridad críticos para que puedan centrarse más en sus iniciativas estratégicas.

- Los nuevos inquilinos (que incluyen los inquilinos que se crearon el 16 de agosto de 2020 o después de él) con Microsoft Defender para endpoint se establecen en automatización completa de forma predeterminada.

- Si el equipo de seguridad ha definido grupos de dispositivos con un nivel de automatización, la nueva configuración predeterminada que se está implementando no cambia esa configuración.

- Puedes mantener la configuración de automatización predeterminada o cambiarla según tus necesidades organizativas. Para cambiar la configuración, [establece el nivel de automatización](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups).

## <a name="next-steps"></a>Pasos siguientes

- [Configurar las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint](configure-automated-investigations-remediation.md)
- [Visitar el Centro de acciones](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
