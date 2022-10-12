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
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 200b390bfaac0777d6373ca5573a4118e580fe01
ms.sourcegitcommit: 4f8200453d347de677461f27eb5a3802ce5cc888
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68542681"
---
<!--- v-jweston resumes authorship and ms.authorship appx April-May 2023 ---> 

# <a name="network-protection-demonstrations"></a>Demostraciones de protección de red

Protección de red ayuda a reducir la superficie expuesta a ataques de los dispositivos a partir de eventos basados en Internet. Impide que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10 1709 compilación 16273
- Antivirus de Microsoft Defender

## <a name="powershell-command"></a>Comando de PowerShell

Set-MpPreference -EnableNetworkProtection habilitado

### <a name="states"></a>Estados
- Habilitado = Modo de bloque (1)
- AuditMode = Modo de auditoría (2)
- Disabled = Off (0)

## <a name="verify-configuration"></a>Comprobación de la configuración

Get-MpPreference

## <a name="scenario"></a>Escenario

1. Activar protección de red mediante el comando de PowerShell: Set-MpPreference -EnableNetworkProtection Enabled
2. Con el explorador que prefiera (no Microsoft Edge*), vaya a la [prueba del sitio web de Protección de red](https://smartscreentestratings2.net/) (Microsoft Edge tiene otras medidas de seguridad para protegerse de esta vulnerabilidad (SmartScreen)). 

## <a name="expected-results"></a>Resultados esperados

La navegación al sitio web debe estar bloqueada y debería ver una notificación "Conexión bloqueada".

## <a name="clean-up"></a>Limpiar

Set-MpPreference -EnableNetworkProtection Deshabilitado

## <a name="see-also"></a>Vea también

[Protección de red](network-protection.md)

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
