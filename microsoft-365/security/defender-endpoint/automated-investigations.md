---
title: Usar investigaciones automatizadas para investigar y corregir amenazas
description: Comprender el flujo de investigación automatizado en Microsoft Defender para endpoint.
keywords: automatizado, investigación, detección, atp de defensa
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: d2effb44c145a4fbf1006446685dbcd703754e6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166214"
---
# <a name="overview-of-automated-investigations"></a>Información general sobre las investigaciones automatizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


¿Quiere ver cómo funciona? Vea el siguiente vídeo: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

La tecnología de la investigación automatizada usa varios algoritmos de inspección y se basa en procesos que usan los analistas de seguridad. Las capacidades de AIR están diseñadas para examinar alertas y tomar medidas inmediatas para resolver infracciones. Las capacidades de AIR reducen significativamente el volumen de alertas, lo que permite que las operaciones de seguridad se centren en amenazas más sofisticadas y otras iniciativas de alto valor. Todas las acciones de corrección, ya sean pendientes o completadas, se realiza un seguimiento en el [Centro de acciones.](auto-investigation-action-center.md) En el Centro de acciones, las acciones pendientes se aprueban (o rechazan) y las acciones completadas se pueden deshacer si es necesario.

En este artículo se proporciona información general sobre AIR e incluye vínculos a los siguientes pasos y recursos adicionales.

> [!TIP]
> ¿Desea experimentar Microsoft Defender para endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).

## <a name="how-the-automated-investigation-starts"></a>Cómo se inicia la investigación automatizada

Una investigación automatizada puede iniciarse cuando se desencadena una alerta o cuando un operador de seguridad inicia la investigación.

|Situación  |Qué ocurre  |
|---------|---------|
|Se desencadena una alerta     | En general, una investigación automatizada se inicia cuando se [desencadena una](review-alerts.md) alerta y [se crea](view-incidents-queue.md) un incidente. Por ejemplo, supongamos que un archivo malintencionado reside en un dispositivo. Cuando se detecta ese archivo, se desencadena una alerta y se crea un incidente. Comienza un proceso de investigación automatizado en el dispositivo. Como otras alertas se generan debido al mismo archivo en otros dispositivos, se agregan al incidente asociado y a la investigación automatizada.         |
|Una investigación se inicia manualmente     | El equipo de operaciones de seguridad puede iniciar manualmente una investigación automatizada. Por ejemplo, supongamos que un operador de seguridad está revisando una lista de dispositivos y observa que un dispositivo tiene un nivel de riesgo alto. El operador de seguridad puede seleccionar el dispositivo en la lista para abrir su control remoto y, a continuación, seleccionar **Iniciar investigación automatizada**. |

## <a name="how-an-automated-investigation-expands-its-scope"></a>Cómo una investigación automatizada expande su ámbito

Mientras se ejecuta una investigación, cualquier otra alerta generada desde el dispositivo se agrega a una investigación automatizada en curso hasta que se complete esa investigación. Además, si se ve la misma amenaza en otros dispositivos, estos dispositivos se agregan a la investigación.

Si se ve una entidad incriminada en otro dispositivo, el proceso de investigación automatizado amplía su ámbito para incluir ese dispositivo y se inicia un libro de juegos de seguridad general en ese dispositivo. Si se encuentran 10 o más dispositivos durante este proceso de expansión desde la misma entidad, esa acción de expansión requiere una aprobación y está visible en la pestaña **Acciones pendientes.**

## <a name="how-threats-are-remediated"></a>Cómo se corrigen las amenazas

A medida que se desencadenan las alertas y se ejecuta una investigación automatizada, se genera un veredicto para cada parte de prueba investigada. Verdicts can be 
- *Malintencionada*;
- *Sospechoso*; o 
- *No se han encontrado amenazas*. 

A medida que se alcanzan los veredictos, las investigaciones automatizadas pueden dar lugar a una o más acciones de corrección. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo a la cuarentena, la detención de un servicio, la eliminación de una tarea programada y mucho más. Para obtener más información, vea [Acciones de corrección](manage-auto-investigation.md#remediation-actions).  

Según el nivel [de](automation-levels.md) automatización establecido para su organización, así como otras opciones de configuración de seguridad, las acciones de corrección pueden producirse automáticamente o solo tras la aprobación del equipo de operaciones de seguridad. La configuración de seguridad adicional que puede afectar a la corrección automática incluye [la protección de aplicaciones potencialmente no deseadas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA). 

Todas las acciones de corrección, ya sean pendientes o completadas, se realiza un seguimiento en el [Centro de acciones.](auto-investigation-action-center.md) Si es necesario, el equipo de operaciones de seguridad puede deshacer una acción de corrección. Para obtener más información, vea [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).

> [!TIP]
> Consulte la nueva página de investigación unificada en el Centro de seguridad de Microsoft 365. Para obtener más información, vea [(¡NUEVO!) Página de investigación unificada](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).


## <a name="requirements-for-air"></a>Requisitos para AIR

Su organización debe tener Defender para endpoint (consulte [Requisitos mínimos de Microsoft Defender para endpoint](minimum-requirements.md)).

Actualmente, AIR solo admite las siguientes versiones del sistema operativo:
- Windows Server 2019
- Windows 10, versión 1709 (compilación del sistema operativo 16299.1085 con [KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)o posterior
- Windows 10, versión 1803 (compilación del sistema operativo 17134.704 con [KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)o posterior
- Windows 10, versión [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) o posterior

## <a name="next-steps"></a>Pasos siguientes

- [Más información sobre los niveles de automatización](automation-levels.md)
- [Consulta la guía interactiva: Investigar y corregir amenazas con Microsoft Defender para endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Configurar las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Ver también

- [Protección de LA PUA](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Investigación y respuesta automatizadas en Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-air)
- [Investigación y respuesta automatizadas en Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
