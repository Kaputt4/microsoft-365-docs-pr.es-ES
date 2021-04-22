---
title: Niveles de automatización en la investigación y corrección automatizadas
description: Obtenga información general sobre los niveles de automatización y cómo funcionan en Microsoft Defender para endpoint
keywords: automated, investigation, level, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 10/22/2020
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 013e01e9f84cae01258afc6ba139b7b5ada5912f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934122"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Niveles de automatización en capacidades automatizadas de investigación y corrección

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Las capacidades de investigación y corrección automatizadas (AIR) en Microsoft Defender para endpoint se pueden configurar en uno de los varios niveles de automatización. El nivel de automatización afecta a si las acciones de corrección siguientes a las investigaciones de AIR se toman automáticamente o solo después de su aprobación.  
- *La automatización completa* (recomendada) significa que las acciones de corrección se toman automáticamente en artefactos determinados como malintencionados.
- *Semi-automation* means some remediation actions are taken automatically, but other remediation actions await approval before being taken. (Vea la tabla niveles [de automatización](#levels-of-automation).)
- Todas las acciones de corrección, ya sean pendientes o completadas, se realiza un seguimiento en el Centro de acciones ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 

> [!TIP]
> Para obtener mejores resultados, se recomienda usar la automatización completa al [configurar AIR](configure-automated-investigations-remediation.md). Los datos recopilados y analizados durante el año pasado muestran que los clientes que usan la automatización completa han quitado un 40 % más de muestras de malware de elevada confianza que los clientes que usan niveles de automatización más bajos. La automatización completa puede ayudar a liberar los recursos de las operaciones de seguridad para centrarse más en sus iniciativas estratégicas.

## <a name="levels-of-automation"></a>Niveles de automatización

En la tabla siguiente se describe cada nivel de automatización y cómo funciona.

|Nivel de automatización | Descripción|
|:---|:---|
|**Completa: corregir las amenazas automáticamente** <br/>(también denominada automatización *completa*)| Con la automatización completa, las acciones de corrección se realizan automáticamente. Todas las acciones de corrección que se toman se pueden ver en el [Centro de acciones](auto-investigation-action-center.md) de la **pestaña** Historial. Si es necesario, se puede deshacer una acción de corrección.<br/><br/>**_Se recomienda_* la automatización completa y se selecciona de forma predeterminada para los inquilinos que se crearon el 16 de agosto de 2020 o después de él con Microsoft Defender para endpoint, sin que aún se haya definido ningún grupo de dispositivos.*  |
|**Semi: requerir aprobación para cualquier corrección** <br/>(también denominada *semiauto* automatización )| Con este nivel de semi automatización, se requiere la aprobación para *cualquier* acción de corrección. Estas acciones pendientes se pueden ver y aprobar en el [Centro de acciones](auto-investigation-action-center.md), en la **pestaña** Pendiente.<br/><br/>*Este nivel de semi automatización está seleccionado de forma predeterminada para los inquilinos que se crearon antes del 16 de agosto de 2020 con Microsoft Defender para endpoint, sin que se haya definido ningún grupo de dispositivos.*|
|**Semi: requerir aprobación para la corrección de carpetas principales** <br/>(también un tipo de *semi automatización)*  | Con este nivel de semiautomización, se requiere la aprobación para las acciones de corrección necesarias en archivos o ejecutables que se encuentran en carpetas principales. Las carpetas principales incluyen directorios del sistema operativo, como **Windows** ( `\windows\*` ).<br/><br/>Las acciones de corrección se pueden realizar automáticamente en archivos o archivos ejecutables que se encuentran en otras carpetas (no principales). <br/><br/>Las acciones pendientes de archivos o ejecutables en carpetas principales se pueden ver y aprobar en el [Centro](auto-investigation-action-center.md)de acciones , en la **pestaña** Pendiente. <br/><br/>Las acciones realizadas en archivos o ejecutables de otras carpetas se pueden ver en el Centro de acciones [,](auto-investigation-action-center.md)en la **pestaña** Historial. |
|**Semi: requerir aprobación para la corrección de carpetas no temporales** <br/>(también un tipo de *semi automatización)*| Con este nivel de semiautomización, se requiere la aprobación para las acciones de corrección necesarias en archivos o ejecutables que *no* se encuentran en carpetas temporales. <br/><br/>Las carpetas temporales pueden incluir los siguientes ejemplos: <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>Las acciones de corrección se pueden realizar automáticamente en archivos o archivos ejecutables que se encuentran en carpetas temporales. <br/><br/>Las acciones pendientes de archivos o ejecutables que no están en carpetas temporales se pueden ver y aprobar en el Centro de [acciones,](auto-investigation-action-center.md)en la **pestaña** Pendiente.<br/><br/>Las acciones realizadas en archivos o ejecutables en carpetas temporales se pueden ver y aprobar en el Centro de acciones [,](auto-investigation-action-center.md)en la **pestaña** Historial.   |
|**Sin respuesta automatizada** <br/>(también se conoce como *sin automatización*) | Sin automatización, la investigación automatizada no se ejecuta en los dispositivos de la organización. Como resultado, no se toman medidas de corrección ni están pendientes como resultado de una investigación automatizada. Sin embargo, otras características [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)de protección contra amenazas, como la protección contra aplicaciones potencialmente no deseadas, pueden estar en vigor, en función de cómo se configuren el antivirus y las características de protección de próxima generación.<br/><br/>***No se *recomienda usar* la opción sin** automatización, ya que reduce la posición de seguridad de los dispositivos de la organización. [Considere la posibilidad de configurar el nivel de automatización en automatización completa (o](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups)al menos semi automatización) *. |

## <a name="important-points-about-automation-levels"></a>Puntos importantes sobre los niveles de automatización

- La automatización completa ha demostrado ser confiable, eficiente y segura, y se recomienda para todos los clientes. La automatización completa libera los recursos de seguridad críticos para que puedan centrarse más en sus iniciativas estratégicas.

- Los nuevos inquilinos (que incluyen los inquilinos que se crearon el 16 de agosto de 2020 o después de él) con Microsoft Defender para endpoint se establecen en automatización completa de forma predeterminada.

- Si el equipo de seguridad ha definido grupos de dispositivos con un nivel de automatización, la nueva configuración predeterminada que se está implementando no cambia esa configuración. 

- Puedes mantener la configuración de automatización predeterminada o cambiarla según tus necesidades organizativas. Para cambiar la configuración, [establezca el nivel de automatización](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups).

## <a name="next-steps"></a>Siguientes pasos

- [Configurar las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint](configure-automated-investigations-remediation.md)

- [Visitar el Centro de acciones](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
