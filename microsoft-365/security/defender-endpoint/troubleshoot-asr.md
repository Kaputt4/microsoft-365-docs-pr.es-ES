---
title: Solucionar problemas con reglas de reducción de superficie de ataque
description: Recursos y código de ejemplo para solucionar problemas con reglas de reducción de superficie de ataque en Microsoft Defender para endpoint.
keywords: troubleshoot, error, fix, windows defender, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c5c76553ff3f0b32def5fbafbf2c8f010e49eeb2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845428"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Solucionar problemas de reglas de reducción de superficie de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Cuando usas [reglas de reducción de](attack-surface-reduction.md) superficie de ataque, puedes encontrar problemas, como:

- Una regla bloquea un archivo, proceso o realiza alguna otra acción que no debería (falso positivo)

- Una regla no funciona como se describe o no bloquea un archivo o proceso que debe (falso negativo)

Hay cuatro pasos para solucionar estos problemas:

1. [Confirmar requisitos previos](#confirm-prerequisites)

2. [Usar el modo de auditoría para probar la regla](#use-audit-mode-to-test-the-rule)

3. [Agregar exclusiones para la regla especificada](#add-exclusions-for-a-false-positive) (para falsos positivos)

4. [Enviar registros de soporte técnico](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Confirmar requisitos previos

Las reglas de reducción de superficie de ataque solo funcionarán en dispositivos con las siguientes condiciones:

- Los puntos de conexión Windows 10 Enterprise, versión 1709 (también conocida como fall Creators Update).

- Los puntos de conexión usan Antivirus de Microsoft Defender como la única aplicación de protección antivirus. [El uso de cualquier otra aplicación antivirus hará que Microsoft Defender AV se deshabilite a sí mismo.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

- [La protección en tiempo real](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.

- El modo auditoría no está habilitado. Use la directiva de grupo para establecer la regla en **Deshabilitado** (valor: **0**) como se describe en Habilitar reglas de reducción [de superficie de ataque](enable-attack-surface-reduction.md).

Si se han cumplido todos estos requisitos previos, continúe con el siguiente paso para probar la regla en modo auditoría.

## <a name="use-audit-mode-to-test-the-rule"></a>Usar el modo de auditoría para probar la regla

Puedes visitar el sitio web de prueba de Windows Defender en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las reglas de reducción de superficie de ataques suelen funcionar para escenarios y procesos preconfigurados en un dispositivo, o puedes usar el modo de auditoría, que permite reglas solo para informes.

Sigue estas instrucciones en [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.

1. Habilite el modo de auditoría para la regla específica que desea probar. Use la directiva de grupo para establecer la regla en **modo auditoría** (valor: **2**) como se describe en Habilitar reglas de reducción de [superficie de ataque](enable-attack-surface-reduction.md). El modo auditoría permite que la regla informe del archivo o proceso, pero aún así le permitirá ejecutarse.

2. Realice la actividad que está causando un problema (por ejemplo, abra o ejecute el archivo o proceso que se debe bloquear pero que se está permitido).

3. [Revise los registros de eventos](attack-surface-reduction.md) de la regla de reducción de superficie de ataque para ver si la regla habría bloqueado el archivo o el proceso si la regla se hubiera establecido en **Enabled**.

Si una regla no bloquea un archivo o proceso que espera que se bloquee, compruebe primero si el modo de auditoría está habilitado.

Es posible que el modo auditoría se haya habilitado para probar otra característica, o mediante un script de PowerShell automatizado, y puede que no se haya deshabilitado después de que se hayan completado las pruebas.

Si ha probado la regla con la herramienta de demostración y con el modo de auditoría, y las reglas de reducción de superficie de ataque funcionan en escenarios preconfigurados, pero la regla no funciona como se esperaba, continúe con cualquiera de las siguientes secciones en función de su situación:

1. Si la regla de reducción de superficie de ataque bloquea algo que no debe bloquear (también conocido como falso positivo), primero puedes agregar una exclusión de regla de reducción de superficie [de ataque.](#add-exclusions-for-a-false-positive)

2. Si la regla de reducción de superficie de ataque no bloquea algo que debería bloquear (también conocido como falso negativo), puede continuar inmediatamente con el último [paso,](#collect-diagnostic-data-for-file-submissions)recopilando datos de diagnóstico y enviando el problema a nosotros .

## <a name="add-exclusions-for-a-false-positive"></a>Agregar exclusiones para un falso positivo

Si la regla de reducción de superficie de ataque bloquea algo que no debe bloquear (también conocido como falso positivo), puedes agregar exclusiones para evitar que las reglas de reducción de superficie de ataque evalúen los archivos o carpetas excluidos.

Para agregar una exclusión, consulta [Personalizar reducción de superficie de ataque](customize-attack-surface-reduction.md).

>[!IMPORTANT]
>Puede especificar archivos y carpetas individuales que se excluirán, pero no puede especificar reglas individuales.
>Esto significa que los archivos o carpetas que se excluyen se excluirán de todas las reglas ASR.

## <a name="report-a-false-positive-or-false-negative"></a>Informar de un falso positivo o falso negativo

Use el [Windows Defender de](https://www.microsoft.com/wdsi/filesubmission) envío basado en web de Inteligencia de seguridad para informar de un falso negativo o falso positivo para la protección de red. Con una Windows de E5, también puede proporcionar [un vínculo a cualquier alerta asociada](alerts-queue.md).

## <a name="collect-diagnostic-data-for-file-submissions"></a>Recopilar datos de diagnóstico para envíos de archivos

Cuando informes de un problema con las reglas de reducción de superficie de ataque, se te pedirá que recopile y envíe datos de diagnóstico que puedan usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas.

1. Abra un símbolo del sistema con privilegios elevados y cambie al Windows Defender directorio:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Ejecute este comando para generar los registros de diagnóstico:

   ```console
   mpcmdrun -getfiles
   ```

3. De forma predeterminada, se guardan en `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . Adjunte el archivo al formulario de envío.

## <a name="related-articles"></a>Artículos relacionados

- [Reglas de la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)

- [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)

- [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
