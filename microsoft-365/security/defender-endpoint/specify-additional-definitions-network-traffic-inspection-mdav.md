---
title: Especifique conjuntos de definiciones adicionales para la inspección del tráfico de red Antivirus de Microsoft Defender
description: Especifique conjuntos de definiciones adicionales para la inspección del tráfico de red Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensor, inspección de tráfico de red
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300260"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede especificar conjuntos de definiciones adicionales para la inspección del tráfico de red mediante la directiva de grupo.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Usar la directiva de grupo para especificar conjuntos de definiciones adicionales para la inspección del tráfico de red

1. En el extremo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Vaya a **Windows Components**  >  **Antivirus de Microsoft Defender**  >  **Network Inspection System**. 

3. Seleccione **Especificar conjuntos de definiciones adicionales para la inspección de tráfico de red.** De forma predeterminada, esta directiva se establece en **No configurado**. 

4. Para editar la directiva, seleccione el vínculo **Editar configuración de** directiva.

5. Seleccione **Habilitado** y, a continuación, en la **sección Opciones,** seleccione **Mostrar...**.

6. Agregue entradas a la lista y, a continuación, seleccione **Aceptar**. 

   Cada entrada debe aparecer como un par nombre-valor, donde el nombre es una representación de cadena de un GUID del conjunto de definiciones. Por ejemplo, el GUID del conjunto de definiciones para habilitar la inteligencia de seguridad de pruebas se define como: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` . El valor no se usa, por lo que se recomienda establecerlo en `0` . 

7. Seleccione **Aceptar** y, a continuación, implemente el objeto de directiva de grupo actualizado. Consulte [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy).

> [!TIP]
> ¿Usa objetos de directiva de grupo local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa . 
  
## <a name="related-articles"></a>Artículos relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Cómo crear e implementar directivas antimalware: Servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)