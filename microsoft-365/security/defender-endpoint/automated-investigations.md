---
title: Uso de investigaciones automatizadas para investigar y corregir amenazas
description: Comprenda el flujo de investigación automatizado en Microsoft Defender para punto de conexión.
keywords: automatizado, investigación, detección, Microsoft Defender para punto de conexión
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
ms.date: 08/31/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
search.appverid: met150
ms.openlocfilehash: ded37b41a4b4c4ec2245edc2a677cf1c0a891fbd
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67736792"
---
# <a name="overview-of-automated-investigations"></a>Introducción a las investigaciones automatizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

**Plataformas**
- Windows

¿Quiere ver cómo funciona? Vea el siguiente vídeo:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

La tecnología de investigación automatizada usa varios algoritmos de inspección y se basa en los procesos que usan los analistas de seguridad. Las funcionalidades de AIR están diseñadas para examinar alertas y tomar medidas inmediatas para resolver las infracciones. Las funcionalidades de AIR reducen significativamente el volumen de alertas, lo que permite que las operaciones de seguridad se centren en amenazas más sofisticadas y otras iniciativas de alto valor. Todas las acciones de corrección, ya sean pendientes o completadas, se realizan en el [Centro de acciones](auto-investigation-action-center.md). En el Centro de acciones, las acciones pendientes se aprueban (o rechazan) y las acciones completadas se pueden deshacer si es necesario.

En este artículo se proporciona información general sobre AIR e incluye vínculos a los pasos siguientes y recursos adicionales.

> [!TIP]
> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automated-investigations-abovefoldlink)

## <a name="how-the-automated-investigation-starts"></a>Cómo se inicia la investigación automatizada

Una investigación automatizada puede iniciarse cuando se desencadena una alerta o cuando un operador de seguridad inicia la investigación.

|Situación|Qué ocurre|
|---|---|
|Se desencadena una alerta|En general, se inicia una investigación automatizada cuando se desencadena una [alerta](review-alerts.md) y se crea un [incidente](view-incidents-queue.md) . Por ejemplo, supongamos que un archivo malintencionado reside en un dispositivo. Cuando se detecta ese archivo, se desencadena una alerta y se crea un incidente. Se inicia un proceso de investigación automatizado en el dispositivo. A medida que se generan otras alertas debido al mismo archivo en otros dispositivos, se agregan al incidente asociado y a la investigación automatizada.|
|Una investigación se inicia manualmente|El equipo de operaciones de seguridad puede iniciar manualmente una investigación automatizada. Por ejemplo, supongamos que un operador de seguridad está revisando una lista de dispositivos y observa que un dispositivo tiene un alto nivel de riesgo. El operador de seguridad puede seleccionar el dispositivo de la lista para abrir su control flotante y, a continuación, seleccionar **Iniciar investigación automatizada**.|

## <a name="how-an-automated-investigation-expands-its-scope"></a>Cómo expande su ámbito una investigación automatizada

Mientras se ejecuta una investigación, cualquier otra alerta generada desde el dispositivo se agrega a una investigación automatizada en curso hasta que se completa esa investigación. Además, si se ve la misma amenaza en otros dispositivos, esos dispositivos se agregan a la investigación.

Si se ve una entidad incriminada en otro dispositivo, el proceso de investigación automatizada amplía su ámbito para incluir ese dispositivo y se inicia un cuaderno de estrategias de seguridad general en ese dispositivo. Si se encuentran 10 o más dispositivos durante este proceso de expansión desde la misma entidad, esa acción de expansión requiere una aprobación y está visible en la pestaña **Acciones pendientes** .

## <a name="how-threats-are-remediated"></a>Cómo se corrigen las amenazas

A medida que se desencadenan alertas y se ejecuta una investigación automatizada, se genera un veredicto para cada parte de la evidencia investigada. Los veredictos pueden ser:

- *Malintencionada*;
- *Sospechoso*; O
- *No se encontraron amenazas*.

A medida que se alcanzan los veredictos, las investigaciones automatizadas pueden dar lugar a una o varias acciones de corrección. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo a la cuarentena, la detención de un servicio, la eliminación de una tarea programada y mucho más. Para obtener más información, consulte [Acciones de corrección](manage-auto-investigation.md#remediation-actions).

En función [del nivel de automatización](automation-levels.md) establecido para su organización, así como de otras configuraciones de seguridad, las acciones de corrección pueden producirse automáticamente o solo tras la aprobación del equipo de operaciones de seguridad. La configuración de seguridad adicional que puede afectar a la corrección automática incluye [la protección contra aplicaciones potencialmente no deseadas](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).

Todas las acciones de corrección, ya sean pendientes o completadas, se realizan en el [Centro de acciones](auto-investigation-action-center.md). Si es necesario, el equipo de operaciones de seguridad puede deshacer una acción de corrección. Para más información, consulte [Revisar y aprobar acciones de corrección después de una investigación automatizada](/microsoft-365/security/defender-endpoint/manage-auto-investigation).

> [!TIP]
> Consulte la nueva página de investigación unificada en el portal de Microsoft 365 Defender. Para obtener más información, consulte [la página De investigación unificada](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).

## <a name="requirements-for-air"></a>Requisitos de AIR

La suscripción debe incluir [Defender para punto de conexión](microsoft-defender-endpoint.md) o [Defender para empresas](../defender-business/mdb-overview.md).

> [!NOTE]
> La investigación y la respuesta automatizadas requieren antivirus de Microsoft Defender para ejecutarse en modo pasivo o en modo activo. Si antivirus de Microsoft Defender está deshabilitado o desinstalado, la investigación y la respuesta automatizadas no funcionarán correctamente.

Actualmente, AIR solo admite las siguientes versiones del sistema operativo:

- Windows Server 2012 R2 (versión preliminar)
- Windows Server 2016 (versión preliminar)
- Windows Server 2019
- Windows Server 2022
- Windows 10, versión 1709 (compilación del sistema operativo 16299.1085 con [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) o posterior
- Windows 10, versión 1803 (compilación del sistema operativo 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) o posterior
- Windows 10, versión [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) o posterior
- Windows 11

> [!NOTE]
> La investigación y respuesta automatizadas en Windows Server 2012 R2 y Windows Server 2016 requiere la instalación del [agente unificado](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution). 

## <a name="next-steps"></a>Pasos siguientes

- [Más información sobre los niveles de automatización](automation-levels.md)
- [Consulte la guía interactiva: Investigación y corrección de amenazas con Microsoft Defender para punto de conexión](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Configurar funcionalidades automatizadas de investigación y corrección en Microsoft Defender para punto de conexión](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Vea también

- [Protección PUA](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Investigación y respuesta automatizadas en Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/office-365-air)
- [Investigación y respuesta automatizadas en Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
