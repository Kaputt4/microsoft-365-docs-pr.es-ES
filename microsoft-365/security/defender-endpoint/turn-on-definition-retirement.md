---
title: Activar la retirada de definiciones Antivirus de Microsoft Defender
description: Active la retirada de definiciones Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensa, retiro de definiciones
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: dd9cd313dec962547acef85c6da326d3b6e5c58f
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167639"
---
# <a name="turn-on-definition-retirement"></a>Activar la retirada de definiciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Puede configurar la retirada de definiciones mediante la directiva de grupo. La definición de retirada comprueba si un equipo tiene las actualizaciones de seguridad necesarias para protegerlo contra una vulnerabilidad determinada. Si el sistema no es vulnerable a la vulnerabilidad detectada por una definición, esa definición se "retirará". Si se retira toda la inteligencia de seguridad de un protocolo determinado, ese protocolo ya no se analiza. Habilitar esta característica ayuda a mejorar el rendimiento. En un equipo actualizado con todas las actualizaciones de seguridad más recientes, la protección de red no tendrá ningún impacto en el rendimiento de la red.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Usar la directiva de grupo para configurar la retirada de definiciones

1. En el extremo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Vaya a **Configuración del equipo** Plantillas administrativas \> **Windows** componentes \>  \> **Antivirus de Microsoft Defender** sistema de \> **inspección de red**.

3. Seleccione **Activar la retirada de definiciones**. Esta directiva está habilitada de modo predeterminado. Si se establece **No configurado,** la retirada de definiciones está habilitada.

4. Para editar la directiva, seleccione el vínculo **Editar configuración de** directiva.

5. Seleccione **Habilitado** y, a continuación, **seleccione Aceptar**.

6. Implemente el objeto de directiva de grupo actualizado. Consulte [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy).

> [!TIP]
> ¿Usa objetos de directiva de grupo local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa .
