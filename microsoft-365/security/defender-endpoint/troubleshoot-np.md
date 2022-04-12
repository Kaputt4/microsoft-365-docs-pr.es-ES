---
title: Solución de problemas con la protección de red
description: Recursos y código de ejemplo para solucionar problemas con la protección de red en Microsoft Defender para punto de conexión.
keywords: troubleshooting, error, fix, windows defender, por ejemplo, asr, rules, hips, troubleshooting, audit, exclusion, false positive, broken, blocking, Microsoft Defender para punto de conexión
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: fbb3a9e038dcd9f342065d538762b41c0673f7e6
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783169"
---
# <a name="troubleshoot-network-protection"></a>Solución de problemas de protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

En este artículo se proporciona información de solución de problemas para [la protección de red](network-protection.md), en casos como:

- Protección de red bloquea un sitio web seguro (falso positivo)
- La protección de red no puede bloquear un sitio web malintencionado sospechoso o conocido (falso negativo)

Hay cuatro pasos para solucionar estos problemas:

1. Confirmación de los requisitos previos
2. Uso del modo de auditoría para probar la regla
3. Agregar exclusiones para la regla especificada (para falsos positivos)
4. Envío de registros de soporte técnico

## <a name="confirm-prerequisites"></a>Confirmación de los requisitos previos

La protección de red solo funcionará en dispositivos con las condiciones siguientes:

> [!div class="checklist"]
>
> - Los puntos de conexión ejecutan Windows 10 Pro o Enterprise edición, versión 1709 o posterior.
> - Los puntos de conexión usan Antivirus de Microsoft Defender como única aplicación de protección antivirus. [Vea lo que sucede cuando se usa una solución antivirus que no es de Microsoft](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).
> - [La protección en tiempo real](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.
> - [La protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) está habilitada.
> - El modo de auditoría no está habilitado. Use [directiva de grupo](enable-network-protection.md#group-policy) para establecer la regla en **Deshabilitado** (valor: **0**).

## <a name="use-audit-mode"></a>Usar modo de auditoría

Puede habilitar la protección de red en modo de auditoría y, a continuación, visitar un sitio web que hemos creado para probar la característica. La protección de red permitirá todas las conexiones del sitio web, pero se registrará un evento para indicar cualquier conexión que se hubiera bloqueado si se habilitase la protección de red.

1. Establezca protección de red en **Modo de auditoría**.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Realice la actividad de conexión que está causando un problema (por ejemplo, intentar visitar el sitio o conectarse a la dirección IP que realiza o no quiere bloquear).

3. [Revise los registros de eventos de protección de red](network-protection.md#review-network-protection-events-in-windows-event-viewer) para ver si la característica habría bloqueado la conexión si se hubiera establecido en **Habilitado**.

   Si la protección de red no bloquea una conexión que espera que se bloquee, habilite la característica.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Notificar un falso positivo o un falso negativo

Si ha probado la característica con el sitio de demostración y con el modo de auditoría, y la protección de red funciona en escenarios preconfigurados, pero no funciona según lo esperado para una conexión específica, use el [formulario de envío basado en web de Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) para notificar un falso positivo o falso positivo para la protección de red. Con una suscripción A5, también puede [proporcionar un vínculo a cualquier alerta asociada](alerts-queue.md).

Consulte [Dirección de falsos positivos o negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md).

## <a name="add-exclusions"></a>Agregar exclusiones

Las opciones de exclusión actuales son:

1. Configuración de un indicador de permiso personalizado.
2. Uso de exclusiones de IP: `Add-MpPreference -ExclusionIpAddress 192.168.1.1`
3. Excluir todo un proceso. Para obtener más información, consulte [exclusiones de Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md). 

## <a name="collect-diagnostic-data-for-file-submissions"></a>Recopilación de datos de diagnóstico para envíos de archivos

Cuando informe de un problema con la protección de red, se le pedirá que recopile y envíe datos de diagnóstico que puedan usar los equipos de ingeniería y soporte técnico de Microsoft para ayudar a solucionar problemas.

1. Abra un símbolo del sistema con privilegios elevados y cambie al directorio Windows Defender:

   ```console
   cd c:\program files\windows defender
   ```

2. Ejecute este comando para generar los registros de diagnóstico:

   ```console
   mpcmdrun -getfiles
   ```

3. Adjunte el archivo al formulario de envío. De forma predeterminada, los registros de diagnóstico se guardan en `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Resolución de problemas de conectividad con la protección de red (para clientes de E5)

Debido al entorno donde se ejecuta la protección de red, Microsoft no puede ver la configuración del proxy del sistema operativo. En algunos casos, los clientes de protección de red no pueden acceder al servicio en la nube. Para resolver problemas de conectividad con la protección de red, configure una de las siguientes claves del Registro para que la protección de red tenga en cuenta la configuración del proxy:

```powershell
Set-MpPreference -ProxyServer <proxy IP address: Port>
```

---OR---

```powershell
Set-MpPreference -ProxyPacUrl <Proxy PAC url>
```

Puede configurar la clave del Registro mediante PowerShell, Microsoft Endpoint Manager o directiva de grupo. Estos son algunos recursos que le ayudarán:

- [Trabajar con claves del Registro](/powershell/scripting/samples/working-with-registry-keys)
- [Configurar opciones de cliente personalizadas para Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Use la configuración de directiva de grupo para administrar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Vea también

- [Protección de red](network-protection.md)
- [Protección de red y protocolo de enlace de tres vías TCP](network-protection.md#network-protection-and-the-tcp-three-way-handshake)
- [Evaluar protección de red](evaluate-network-protection.md)
- [Habilitación de la protección de red](enable-network-protection.md)
- [Dirección de falsos positivos o negativos en Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
