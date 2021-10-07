---
title: Solucionar problemas con la protección de red
description: Recursos y código de ejemplo para solucionar problemas con la protección de red en Microsoft Defender para endpoint.
keywords: troubleshoot, error, fix, windows defender, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: fce2366a155dca3f045497abf2a7a9892180710d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159323"
---
# <a name="troubleshoot-network-protection"></a>Solucionar problemas de protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

En este artículo se proporciona información de solución de problemas para la protección de [red,](network-protection.md)en casos como:

- La protección de red bloquea un sitio web seguro (falso positivo)
- La protección de red no puede bloquear un sitio web malintencionado sospechoso o conocido (falso negativo)

Hay cuatro pasos para solucionar estos problemas:

1. Confirmar requisitos previos
2. Usar el modo de auditoría para probar la regla
3. Agregar exclusiones para la regla especificada (para falsos positivos)
4. Enviar registros de soporte técnico

## <a name="confirm-prerequisites"></a>Confirmar requisitos previos

La protección de red solo funcionará en dispositivos con las siguientes condiciones:

> [!div class="checklist"]
>
> - Los puntos de conexión se Windows 10 Pro o Enterprise edición, versión 1709 o posterior.
> - Los puntos de conexión usan Antivirus de Microsoft Defender como la única aplicación de protección antivirus. [Vea lo que sucede cuando usa una solución antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)que no sea de Microsoft .
> - [La protección en tiempo real](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.
> - [La protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) está habilitada.
> - El modo auditoría no está habilitado. Use [la directiva de](enable-network-protection.md#group-policy) grupo para establecer la regla en **Deshabilitado** (valor: **0**).

## <a name="use-audit-mode"></a>Usar modo de auditoría

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

## <a name="add-exclusions"></a>Agregar exclusiones
Las opciones de exclusión actuales son:

1.  Configurar un indicador de permitir personalizado.
2.  Uso de exclusiones IP: `Add-MpPreference -Exclusion IpAddress 192.168.1.1`
3.  Excluyendo todo un proceso. Para obtener más información, [vea Antivirus de Microsoft Defender exclusiones](configure-exclusions-microsoft-defender-antivirus.md). 


## <a name="collect-diagnostic-data-for-file-submissions"></a>Recopilar datos de diagnóstico para envíos de archivos

Cuando informe de un problema con la protección de red, se le pedirá que recopile y envíe datos de diagnóstico que puedan usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas.

1. Abra un símbolo del sistema con privilegios elevados y cambie al Windows Defender directorio:

   ```console
   cd c:\program files\windows defender
   ```

2. Ejecute este comando para generar los registros de diagnóstico:

   ```console
   mpcmdrun -getfiles
   ```

3. Adjunte el archivo al formulario de envío. De forma predeterminada, los registros de diagnóstico se guardan en `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Resolver problemas de conectividad con la protección de red (para clientes de E5)

Debido al entorno donde se ejecuta la protección de red, Microsoft no puede ver la configuración de proxy del sistema operativo. En algunos casos, los clientes de protección de red no pueden llegar al servicio en la nube. Para resolver problemas de conectividad con la protección de red, configure una de las siguientes claves del Registro para que la protección de red tenga en cuenta la configuración de proxy:

```powershell
Set-MpPreference -ProxyServer <proxy IP address: Port>
```

---OR---

```powershell
Set-MpPreference -ProxyPacUrl <Proxy PAC url>
```

Puede configurar la clave del Registro mediante PowerShell, Microsoft Endpoint Manager o directiva de grupo. Estos son algunos recursos para ayudar:

- [Trabajar con claves del Registro](/powershell/scripting/samples/working-with-registry-keys)
- [Configurar opciones de cliente personalizadas para Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Usar la configuración de directiva de grupo para administrar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Vea también

- [Protección de red](network-protection.md)
- [Protección de red y el protocolo de enlace triple TCP](network-protection.md#network-protection-and-the-tcp-three-way-handshake)
- [Evaluar protección de red](evaluate-network-protection.md)
- [Habilitar la protección de red](enable-network-protection.md)
- [Dirección de falsos positivos/negativos en Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
