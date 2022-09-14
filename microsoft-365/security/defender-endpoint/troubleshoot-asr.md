---
title: Solución de problemas con las reglas de reducción de superficie expuesta a ataques
description: Recursos y código de ejemplo para solucionar problemas con las reglas de reducción de superficie expuesta a ataques en Microsoft Defender para punto de conexión.
keywords: troubleshooting, error, fix, windows defender, por ejemplo, asr, rules, hips, troubleshooting, audit, exclusion, false positive, broken, blocking, Microsoft Defender para punto de conexión
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.subservice: mde
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: ae7cd1e07ff4f8814b54c00a28d23d674b3dbd26
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689171"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Solución de problemas de reglas de reducción de superficie expuesta a ataques

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Al usar [reglas de reducción de superficie expuesta a ataques](attack-surface-reduction.md) , es posible que se pliquen problemas, como los siguientes:

- Una regla bloquea un archivo, procesa o realiza alguna otra acción que no debería (falso positivo)
- Una regla no funciona como se describe o no bloquea un archivo o proceso que debe (falso negativo)

Hay cuatro pasos para solucionar estos problemas:

1. [Confirmación de los requisitos previos](#confirm-prerequisites)
2. [Uso del modo de auditoría para probar la regla](#use-audit-mode-to-test-the-rule)
3. [Agregar exclusiones para la regla especificada](#add-exclusions-for-a-false-positive) (para falsos positivos)
4. [Envío de registros de soporte técnico](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Confirmación de los requisitos previos

Las reglas de reducción de superficie expuesta a ataques solo funcionarán en dispositivos con las condiciones siguientes:

- Los puntos de conexión ejecutan Windows 10 Enterprise, versión 1709 (también conocida como Fall Creators Update).

- Los puntos de conexión usan antivirus de Microsoft Defender como única aplicación de protección antivirus. [El uso de cualquier otra aplicación antivirus hará que Antivirus de Microsoft Defender se deshabilite](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).

- [La protección en tiempo real](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.

- El modo de auditoría no está habilitado. Use directiva de grupo para establecer la regla en **Deshabilitada** (valor: **0**), como se describe en [Habilitar reglas de reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md).

Si se cumplen todos estos requisitos previos, continúe con el paso siguiente para probar la regla en modo de auditoría.

## <a name="use-audit-mode-to-test-the-rule"></a>Uso del modo de auditoría para probar la regla

Siga estas instrucciones en [Uso de la herramienta de demostración para ver cómo funcionan las reglas de reducción de superficie expuesta a ataques](evaluate-attack-surface-reduction.md) para probar la regla específica con la que tiene problemas.

1. Habilite el modo de auditoría para la regla específica que desea probar. Use directiva de grupo para establecer la regla en **Modo de auditoría** (valor: **2**) como se describe en [Habilitar reglas de reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md). El modo auditoría permite que la regla informe del archivo o proceso, pero seguirá permitiendo que se ejecute.

2. Realice la actividad que está causando un problema (por ejemplo, abra o ejecute el archivo o proceso que se debe bloquear pero que se permite).

3. [Revise los registros de eventos de la regla de reducción de la superficie expuesta a ataques](attack-surface-reduction.md) para ver si la regla habría bloqueado el archivo o el proceso si la regla se hubiera establecido en **Habilitado**.

Si una regla no bloquea un archivo o proceso que espera que se bloquee, compruebe primero si el modo de auditoría está habilitado.

Es posible que el modo de auditoría se haya habilitado para probar otra característica, o mediante un script de PowerShell automatizado, y es posible que no se haya deshabilitado una vez completadas las pruebas.

Si ha probado la regla con la herramienta de demostración y con el modo de auditoría, y las reglas de reducción de superficie expuesta a ataques funcionan en escenarios preconfigurados, pero la regla no funciona según lo esperado, vaya a cualquiera de las secciones siguientes en función de su situación:

1. Si la regla de reducción de superficie expuesta a ataques bloquea algo que no debe bloquear (también conocido como falso positivo), [primero puede agregar una exclusión de regla de reducción de superficie expuesta a ataques](#add-exclusions-for-a-false-positive).

2. Si la regla de reducción de la superficie expuesta a ataques no bloquea algo que debería bloquear (también conocido como falso negativo), puede continuar inmediatamente al último paso, [recopilando datos de diagnóstico y enviándonos el problema](#collect-diagnostic-data-for-file-submissions).

## <a name="add-exclusions-for-a-false-positive"></a>Adición de exclusiones para un falso positivo

Si la regla de reducción de superficie expuesta a ataques bloquea algo que no debe bloquear (también conocido como falso positivo), puede agregar exclusiones para evitar que las reglas de reducción de la superficie expuesta a ataques evalúen los archivos o carpetas excluidos.

Para agregar una exclusión, consulta [Personalizar la reducción de la superficie expuesta a ataques](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules).

> [!IMPORTANT]
> Puede especificar archivos y carpetas individuales que se van a excluir, pero no puede especificar reglas individuales.
> Esto significa que los archivos o carpetas que se excluyen se excluirán de todas las reglas de ASR.

## <a name="report-a-false-positive-or-false-negative"></a>Notificar un falso positivo o un falso negativo

Use el [formulario de envío basado en web de Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/support/report-exploit-guard) para notificar un falso negativo o falso positivo para la protección de red. Con una suscripción a Windows E5, también puede [proporcionar un vínculo a cualquier alerta asociada](alerts-queue.md).

## <a name="collect-diagnostic-data-for-file-submissions"></a>Recopilación de datos de diagnóstico para envíos de archivos

Al informar de un problema con las reglas de reducción de superficie expuesta a ataques, se le pide que recopile y envíe datos de diagnóstico que puedan usar los equipos de ingeniería y soporte técnico de Microsoft para ayudar a solucionar problemas.

1. Abra un símbolo del sistema con privilegios elevados y cambie al directorio Windows Defender:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Ejecute este comando para generar los registros de diagnóstico:

   ```console
   mpcmdrun -getfiles
   ```

3. De forma predeterminada, se guardan en `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`. Adjunte el archivo al formulario de envío.

## <a name="related-articles"></a>Artículos relacionados

- [Reglas de la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
- [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
- [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
