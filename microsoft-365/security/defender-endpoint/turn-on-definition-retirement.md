---
title: Activar la retirada de definiciones para Microsoft Defender Antivirus
description: Active la retirada de definiciones para Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, seguridad, defender, retirada de definiciones
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.topic: conceptual
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: 279a5bc782803adc5bd26c8d0bceebbf03e68ad1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68635034"
---
# <a name="turn-on-definition-retirement"></a>Activar la retirada de definiciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Puede configurar la retirada de definiciones mediante समूह नीति. La retirada de definiciones comprueba si un equipo tiene las actualizaciones de seguridad necesarias para protegerlo frente a una vulnerabilidad determinada. Si el sistema no es vulnerable a la vulnerabilidad de seguridad detectada por una definición, esa definición se "retirará". Si se retira toda la inteligencia de seguridad de un protocolo determinado, ese protocolo ya no se analiza. Habilitar esta característica ayuda a mejorar el rendimiento. En un equipo que esté actualizado con todas las actualizaciones de seguridad más recientes, la protección de red no tendrá ningún impacto en el rendimiento de la red.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Uso de समूह नीति para configurar la retirada de definiciones

1. En el punto de conexión de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Vaya a **Configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> de Windows Microsoft Defender Sistema de **inspección de red** **antivirus**\>.

3. Seleccione **Activar la retirada de definiciones**. Esta directiva está habilitada de modo predeterminado. Si se establece **No configurado**, se habilita la retirada de definiciones.

4. Para editar la directiva, seleccione el vínculo **editar configuración de directiva** .

5. Seleccione **Habilitado** y, después, **Aceptar**.

6. Implemente el objeto समूह नीति actualizado. Consulte [समूह नीति Consola de administración](/windows/win32/srvnodes/group-policy).

> [!TIP]
> ¿Usa समूह नीति Objetos en el entorno local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis de समूह नीति en Microsoft Endpoint Manager : versión preliminar](/mem/intune/configuration/group-policy-analytics).
