---
title: Activar la retirada de definiciones para el Antivirus de Microsoft Defender
description: Active la retirada de definiciones para el Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, retirada de definiciones
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
ms.topic: article
ms.collection: m365-security-compliance
search.appverid: met150
ms.openlocfilehash: 1401c9b58ee91d51fbf4a37463fb1f75c542d154
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67684285"
---
# <a name="turn-on-definition-retirement"></a>Activar la retirada de definiciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Puede configurar la retirada de definiciones mediante directiva de grupo. La retirada de definiciones comprueba si un equipo tiene las actualizaciones de seguridad necesarias para protegerlo frente a una vulnerabilidad determinada. Si el sistema no es vulnerable a la vulnerabilidad de seguridad detectada por una definición, esa definición se "retirará". Si se retira toda la inteligencia de seguridad de un protocolo determinado, ese protocolo ya no se analiza. Habilitar esta característica ayuda a mejorar el rendimiento. En un equipo que esté actualizado con todas las actualizaciones de seguridad más recientes, la protección de red no tendrá ningún impacto en el rendimiento de la red.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Uso de directiva de grupo para configurar la retirada de definiciones

1. En el punto de conexión de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Vaya a **Configuración** \> del equipo **Plantillas** \> administrativas **Componentes de** \> Windows Sistema de **inspección de red** antivirus \> de **Microsoft Defender**.

3. Seleccione **Activar la retirada de definiciones**. Esta directiva está habilitada de modo predeterminado. Si se establece **No configurado**, se habilita la retirada de definiciones.

4. Para editar la directiva, seleccione el vínculo **editar configuración de directiva** .

5. Seleccione **Habilitado** y, después, **Aceptar**.

6. Implemente el objeto directiva de grupo actualizado. Consulte [directiva de grupo Consola de administración](/windows/win32/srvnodes/group-policy).

> [!TIP]
> ¿Usa directiva de grupo Objetos en el entorno local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante directiva de grupo análisis en Microsoft Endpoint Manager - Versión preliminar](/mem/intune/configuration/group-policy-analytics).
