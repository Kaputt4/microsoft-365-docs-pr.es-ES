---
title: Niveles de automatización en investigación y corrección automatizadas
description: Obtenga información general sobre los niveles de automatización y cómo funcionan en Microsoft Defender para punto de conexión
keywords: automated, investigation, level, Microsoft Defender para punto de conexión
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.prod: m365-security
ms.author: dansimp
ms.localizationpriority: medium
ms.date: 08/22/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
search.appverid: met150
ms.openlocfilehash: c01f9516e6c2a82c65fc2eb96773ff2bc4840f78
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67798789"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Niveles de automatización en las funcionalidades automatizadas de investigación y corrección

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

Las funcionalidades de investigación y corrección automatizadas (AIR) en Microsoft Defender para Empresas están preconfiguradas y no son configurables. En Microsoft Defender para punto de conexión, puede configurar AIR en uno de varios niveles de automatización. El nivel de automatización afecta a si las acciones de corrección después de las investigaciones de AIR se realizan automáticamente o solo tras la aprobación.

- *Automatización completa* (recomendada) significa que las acciones de corrección se realizan automáticamente en artefactos que se determina que son malintencionados. (*La automatización completa se establece de forma predeterminada en Defender para empresas*).
- *La automatización parcial* significa que algunas acciones de corrección se realizan automáticamente, pero otras acciones de corrección esperan la aprobación antes de realizarse. (Vea la tabla [en Niveles de automatización](#levels-of-automation)).
- Todas las acciones de corrección, ya sean pendientes o completadas, se realizan en el Centro de acciones ([https://security.microsoft.com](https://security.microsoft.com)).

> [!TIP]
> Para obtener los mejores resultados, se recomienda usar la automatización completa al [configurar AIR](configure-automated-investigations-remediation.md). Los datos recopilados y analizados durante el último año muestran que los clientes que usan la automatización completa han quitado un 40 % más muestras de malware de alta confianza que los clientes que usan niveles inferiores de automatización. La automatización completa puede ayudar a liberar los recursos de operaciones de seguridad para centrarse más en sus iniciativas estratégicas.

## <a name="levels-of-automation"></a>Niveles de automatización

|Nivel de automatización|Descripción|
|---|---|
|**Completo: corrección automática de amenazas** <br> (también conocido como *automatización completa*)|Con la automatización completa, las acciones de corrección se realizan automáticamente en entidades que se consideran malintencionadas. Todas las acciones de corrección que se realizan se pueden ver en el [Centro de acciones](auto-investigation-action-center.md) de la pestaña **Historial** . Si es necesario, se puede deshacer una acción de corrección. <p> **_Se recomienda la automatización completa_* y se selecciona de forma predeterminada para los inquilinos con Defender para punto de conexión que se crearon el 16 de agosto de 2020 o después, sin ningún grupo de dispositivos definido todavía.*<p>*La automatización completa se establece de forma predeterminada en Defender para empresas.*|
|**Semi: requiere aprobación para cualquier corrección.** <br> (también conocido como *semiautomatización*)|Con este nivel de automatización parcial, se requiere aprobación para *cualquier* acción de corrección. Estas acciones pendientes se pueden ver y aprobar en el [Centro de acciones](auto-investigation-action-center.md), en la pestaña **Pendiente** . <p> *Este nivel de automatización se selecciona de forma predeterminada para los inquilinos creados antes del 16 de agosto de 2020 con Microsoft Defender para punto de conexión, sin grupos de dispositivos definidos.*|
|**Semi: se requiere aprobación para la corrección de carpetas principales** <br> (también un tipo de *semiautomatización*)|Con este nivel de automatización parcial, se requiere aprobación para las acciones de corrección necesarias en archivos o ejecutables que se encuentran en carpetas principales. Las carpetas principales incluyen directorios del sistema operativo, como **Windows** (`\windows\*`). <p> Las acciones de corrección se pueden realizar automáticamente en archivos o ejecutables que se encuentran en otras carpetas (no principales). <p> Las acciones pendientes para archivos o ejecutables en carpetas principales se pueden ver y aprobar en el [Centro de acciones](auto-investigation-action-center.md), en la pestaña **Pendiente** . <p> Las acciones realizadas en archivos o ejecutables de otras carpetas se pueden ver en el Centro de [acciones](auto-investigation-action-center.md), en la pestaña **Historial** .|
|**Semi: se requiere aprobación para la corrección de carpetas no temporales** <br> (también un tipo de *semiautomatización*)|Con este nivel de automatización parcial, se requiere aprobación para las acciones de corrección necesarias en archivos o ejecutables que *no* están en carpetas temporales. <p> Las carpetas temporales pueden incluir los ejemplos siguientes: <ul><li>`\users\*\appdata\local\temp\*`</li><li>`\documents and settings\*\local settings\temp\*`</li><li>`\documents and settings\*\local settings\temporary\*`</li><li>`\windows\temp\*`</li><li>`\users\*\downloads\*`</li><li>`\program files\`</li><li>`\program files (x86)\*`</li><li>`\documents and settings\*\users\*`</li></ul> <p> Las acciones de corrección se pueden realizar automáticamente en archivos o ejecutables que se encuentran en carpetas temporales. <p> Las acciones pendientes para archivos o ejecutables que no están en carpetas temporales se pueden ver y aprobar en el [Centro de acciones](auto-investigation-action-center.md), en la pestaña **Pendiente** . <p> Las acciones que se realizaron en archivos o ejecutables en carpetas temporales se pueden ver y aprobar en el [Centro de acciones](auto-investigation-action-center.md), en la pestaña **Historial** .|
|**Sin respuesta automatizada** <br> (también conocido como *sin automatización*)|Sin automatización, la investigación automatizada no se ejecuta en los dispositivos de la organización. Como resultado, no se realizan acciones de corrección ni están pendientes como resultado de una investigación automatizada. Sin embargo, otras características de protección contra amenazas, como la [protección contra aplicaciones potencialmente no deseadas](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus), pueden estar en vigor, en función de cómo se configuren el antivirus y las características de protección de próxima generación. <p> ***No se recomienda usar la opción *sin automatización***, ya que reduce la posición de seguridad de los dispositivos de la organización. [Considere la posibilidad de configurar el nivel de automatización en automatización completa (o al menos semiautomatización).](/microsoft-365/security/defender-endpoint/machine-groups)|

## <a name="important-points-about-automation-levels"></a>Puntos importantes sobre los niveles de automatización

- La automatización completa ha demostrado ser confiable, eficiente y segura, y se recomienda para todos los clientes. La automatización completa libera los recursos de seguridad críticos para que puedan centrarse más en sus iniciativas estratégicas.

- Los nuevos inquilinos (que incluyen los inquilinos creados el 16 de agosto de 2020 o después de él) con Defender para punto de conexión se establecen en automatización completa de forma predeterminada.

- [Defender for Business](../defender-business/compare-mdb-m365-plans.md) usa la automatización completa de forma predeterminada. Defender for Business no usa grupos de dispositivos de la misma manera que Defender para punto de conexión. Por lo tanto, la automatización completa se activa y se aplica a todos los dispositivos de Defender para empresas.

- Si el equipo de seguridad ha definido grupos de dispositivos con un nivel de automatización, la nueva configuración predeterminada que se va a implementar no cambiará esa configuración.

- Puede mantener la configuración de automatización predeterminada o cambiarla según sus necesidades organizativas. Para cambiar la configuración, [establezca el nivel de automatización](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups).

## <a name="next-steps"></a>Pasos siguientes

- [Configuración de funcionalidades automatizadas de investigación y corrección en Defender para punto de conexión](configure-automated-investigations-remediation.md)
- [Visite el Centro de acciones.](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
