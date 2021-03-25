---
title: Solucionar problemas con la protección de red
description: Recursos y código de ejemplo para solucionar problemas con la protección de red en Microsoft Defender para endpoint.
keywords: troubleshoot, error, fix, windows defender, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, microsoft defender for endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 34bebddcf052a643529f1d2b8a8a869a0ffe4a91
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183829"
---
# <a name="troubleshoot-network-protection"></a>Solucionar problemas de protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Cuando usa la [protección de red,](network-protection.md) puede encontrar problemas, como:

- La protección de red bloquea un sitio web seguro (falso positivo)
- La protección de red no puede bloquear un sitio web malintencionado sospechoso o conocido (falso negativo)

Hay cuatro pasos para solucionar estos problemas:

1. Confirmar requisitos previos
2. Usar el modo de auditoría para probar la regla
3. Agregar exclusiones para la regla especificada (para falsos positivos)
4. Enviar registros de soporte técnico

## <a name="confirm-prerequisites"></a>Confirmar requisitos previos

La protección de red solo funcionará en dispositivos con las siguientes condiciones:

>[!div class="checklist"]
> - Los puntos de conexión ejecutan Windows 10 Pro o Enterprise edition, versión 1709 o posterior.
> - Los puntos de conexión usan Antivirus de Microsoft Defender como única aplicación de protección antivirus. [Vea lo que sucede cuando usa una solución antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)que no sea de Microsoft .
> - [La protección en tiempo real](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.
> - [La protección entregada en la nube](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) está habilitada.
> - El modo auditoría no está habilitado. Use [la directiva de](enable-network-protection.md#group-policy) grupo para establecer la regla en **Deshabilitado** (valor: **0**).

## <a name="use-audit-mode"></a>Usar el modo de auditoría

Puede habilitar la protección de red en modo auditoría y, a continuación, visitar un sitio web que hemos creado para realizar una demostración de la característica. La protección de red permitirá todas las conexiones de sitios web, pero se registrará un evento para indicar cualquier conexión que se hubiera bloqueado si la protección de red estaba habilitada.

1. Establezca la protección de red en **modo auditoría**.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Realice la actividad de conexión que está causando un problema (por ejemplo, intentar visitar el sitio o conectarse a la dirección IP que hace o no desea bloquear).

3. [Revise los registros de](network-protection.md#review-network-protection-events-in-windows-event-viewer) eventos de protección de red para ver si la característica hubiera bloqueado la conexión si se hubiera establecido en **Enabled**.
   
   Si la protección de red no bloquea una conexión que espera que se bloquee, habilite la característica.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Informar de un falso positivo o falso negativo

Si ha probado la característica con el sitio de demostración y con el modo de auditoría, y la protección de red funciona en escenarios preconfigurados, pero no funciona como se esperaba para una conexión específica, use el formulario de envío basado en web de inteligencia de seguridad de [Windows Defender](https://www.microsoft.com/wdsi/filesubmission) para informar de un falso negativo o falso positivo para la protección de red. Con una suscripción A5, también puede proporcionar [un vínculo a cualquier alerta asociada.](alerts-queue.md)

Consulta [Dirección de falsos positivos/negativos en Microsoft Defender para Endpoint](defender-endpoint-false-positives-negatives.md).

## <a name="exclude-website-from-network-protection-scope"></a>Excluir sitio web del ámbito de protección de red

Para permitir el sitio web que se está bloqueando (falso positivo), agregue su dirección URL a la [lista de sitios de confianza](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/). Los recursos web de esta lista omiten la comprobación de protección de red.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Recopilar datos de diagnóstico para envíos de archivos

Cuando informe de un problema con la protección de red, se le pedirá que recopile y envíe datos de diagnóstico que puedan usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas.

1. Abra un símbolo del sistema con privilegios elevados y cambie al Windows Defender:

   ```console
   cd c:\program files\windows defender
   ```

2. Ejecute este comando para generar los registros de diagnóstico:

   ```console
   mpcmdrun -getfiles
   ```

3. De forma predeterminada, se guardan en C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab. Adjunte el archivo al formulario de envío.

## <a name="related-topics"></a>Temas relacionados

- [Protección de red](network-protection.md)
- [Evaluar la protección de red](evaluate-network-protection.md)
- [Habilitar la protección de red](enable-network-protection.md)
- [Dirección de falsos positivos/negativos en Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
