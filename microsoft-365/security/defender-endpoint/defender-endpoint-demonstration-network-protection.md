---
title: demostraciones de protección de red de Microsoft Defender para punto de conexión
description: Muestra cómo la protección de red impide que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet.
keywords: protección de red, protección contra estafas de phishing, protección contra vulnerabilidades de seguridad, protección contra contenido malintencionado, demostración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
- demo
ms.topic: article
ms.subservice: mde
ms.date: 10/21/2022
ms.openlocfilehash: 41a1a023fbfdc71ceec060dda84349ff6776175d
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68732765"
---
# <a name="network-protection-demonstrations"></a>Demostraciones de protección de red

Protección de red ayuda a reducir la superficie expuesta a ataques de los dispositivos a partir de eventos basados en Internet. Impide que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10 1709, compilación 16273, Windows 11
- Antivirus de Microsoft Defender

## <a name="powershell-command"></a>Comando de PowerShell

```powershell
Set-MpPreference -EnableNetworkProtection Enabled
```

## <a name="rule-states"></a>Estados de regla

|Estado | Modo| Valor numérico |
|:---|:---|:---|
| Deshabilitada | = Desactivado | 0 |
| Habilitado | = Modo de bloque | 1 |
| Auditoría | = Modo auditoría | 2 |

## <a name="verify-configuration"></a>Comprobación de la configuración

```powershell
Get-MpPreference
```

## <a name="scenario"></a>Escenario

1. Active Protección de red mediante el comando de PowerShell:

   ```powershell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

2. Con el explorador que prefiera (no Microsoft Edge*), vaya a la [prueba del sitio web de Protección de red](https://smartscreentestratings2.net/). Microsoft Edge tiene otras medidas de seguridad para protegerse de esta vulnerabilidad (SmartScreen).

## <a name="expected-results"></a>Resultados esperados

La navegación al sitio web debe estar bloqueada y debería ver una notificación **de conexión bloqueada** .

## <a name="clean-up"></a>Limpiar

```powershell
Set-MpPreference -EnableNetworkProtection Disabled
```

## <a name="see-also"></a>Vea también

[Protección de red](network-protection.md)

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
