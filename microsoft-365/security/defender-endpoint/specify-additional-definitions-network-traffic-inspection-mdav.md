---
title: Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red para Microsoft Defender Antivirus
description: Especifique conjuntos de definiciones adicionales para la inspección del tráfico de red para Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, seguridad, defender, inspección de tráfico de red
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.topic: conceptual
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 25a1fcc55a564d734f64b587474ff6a5610ffaaf
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68646141"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

Puede especificar conjuntos de definiciones adicionales para la inspección del tráfico de red mediante समूह नीति.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Use समूह नीति para especificar conjuntos de definiciones adicionales para la inspección del tráfico de red.

1. En el punto de conexión de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Vaya a **Componentes** \> de Windows Microsoft Defender **Sistema de inspección de red** **antivirus**\>.

3. Seleccione **Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red**. De forma predeterminada, esta directiva se establece en **No configurada**.

4. Para editar la directiva, seleccione el vínculo **editar configuración de directiva** .

5. Seleccione **Habilitado** y, a continuación, en la sección **Opciones** , seleccione **Mostrar...**.

6. Agregue entradas a la lista y, a continuación, seleccione **Aceptar**.

   Cada entrada debe aparecer como un par nombre-valor, donde el nombre es una representación de cadena de un GUID de conjunto de definiciones. Por ejemplo, el GUID del conjunto de definiciones para habilitar la inteligencia de seguridad de prueba se define como: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`. No se usa el valor, por lo que se recomienda establecerlo `0`en .

7. Seleccione **Aceptar** e implemente el objeto समूह नीति actualizado. Consulte [समूह नीति Consola de administración](/windows/win32/srvnodes/group-policy).

> [!TIP]
> ¿Usa समूह नीति Objetos en el entorno local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis de समूह नीति en Microsoft Endpoint Manager : versión preliminar](/mem/intune/configuration/group-policy-analytics).

## <a name="related-articles"></a>Artículos relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Creación e implementación de directivas antimalware: servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)