---
title: Detección y respuesta de puntos de conexión en modo de bloqueo
description: Obtenga información sobre detección y respuesta de puntos de conexión en modo de bloque
keywords: Microsoft Defender para endpoint, mde, EDR en modo de bloque, bloqueo de modo pasivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b0fe1da56c34cd0a79e1a41dba2fcb7a79c5a9f6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259586"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Detección y respuesta de puntos de conexión (EDR) en modo de bloqueo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>¿Qué EDR en modo de bloqueo?

[La detección y respuesta](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) de puntos de conexión (EDR) en modo de bloqueo proporciona protección contra artefactos malintencionados, incluso cuando Antivirus de Microsoft Defender se ejecuta en modo pasivo. Cuando está activado, EDR en modo de bloqueo bloquea los artefactos o comportamientos malintencionados que se detectan en un dispositivo. EDR en modo de bloqueo funciona en segundo plano para corregir artefactos malintencionados detectados después de la infracción. 

EDR en modo de bloque también se integra con [la amenaza & administración de vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt). El equipo de seguridad de [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) la organización recibirá una recomendación de seguridad para activar EDR en modo de bloqueo si aún no está habilitado. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="recomendación de activar el EDR en modo de bloqueo":::

> [!NOTE]
> Para obtener la mejor protección, asegúrese de implementar Las líneas base de **[Microsoft Defender para endpoint .](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>¿Qué sucede cuando se detecta algo?

Cuando EDR en modo de bloque está activado y se detecta un artefacto malintencionado, Microsoft Defender para endpoint bloquea y corrige ese artefacto. Verá el estado de detección como **Bloqueado** o **Impedido** como acciones completadas en el [Centro de acciones](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center).

La siguiente imagen muestra una instancia de software no deseado que se detectó y bloqueó a través EDR en modo de bloqueo:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR en modo de bloque detectó algo":::


## <a name="enable-edr-in-block-mode"></a>Habilitar EDR en modo de bloque

> [!IMPORTANT]
> Asegúrese de que se [cumplen](#requirements-for-edr-in-block-mode) los requisitos antes de activar EDR en modo de bloque.

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e inicie sesión. 

2. Elija **Configuración**  >  **características avanzadas**.

3. Activa la **EDR en modo de bloque**.

> [!NOTE]
> EDR en modo de bloque solo se puede desactivar en el Centro de seguridad de Microsoft Defender. No puede usar claves del Registro, Intune o directivas de grupo para habilitar o deshabilitar EDR en modo de bloque.

## <a name="requirements-for-edr-in-block-mode"></a>Requisitos para EDR en modo de bloque

|Requisito  |Detalles  |
|---------|---------|
|Permisos |Rol Administrador global o Administrador de seguridad asignado [en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Consulte [Basic permissions](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions). |
|Sistema operativo     |Una de las siguientes versiones: <br/>- Windows 10 (todas las versiones) <br/>- Windows server, versión 1803 o posterior <br/>- Windows Server 2019  <p>**NOTA:** EDR en modo de bloque no se admite en Windows Server 2016.       |
|Windows Inscripción en E5     |Windows E5 se incluye en las siguientes suscripciones: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 junto con la oferta de protección contra & identidad <br/><br/>Vea [Componentes](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) y [características y capacidades para cada plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).       |
|Antivirus de Microsoft Defender  |Antivirus de Microsoft Defender debe instalarse y ejecutarse en modo activo o en modo pasivo. (Puede usar Antivirus de Microsoft Defender junto con una solución antivirus que no es de Microsoft). [Confirme Antivirus de Microsoft Defender está en modo activo o pasivo](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode). |
|Protección entregada en la nube |Asegúrese de Antivirus de Microsoft Defender está configurado de modo que [la protección entregada en la nube esté habilitada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus). |
|Antivirus de Microsoft Defender cliente antimalware |Asegúrese de que el cliente está actualizado. Con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) como administrador. En la **línea AMProductVersion,** debería ver **4.18.2001.10** o posterior. |
|Antivirus de Microsoft Defender motor |Asegúrese de que el motor está actualizado. Con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) como administrador. En la **línea AMEngineVersion,** debería ver **1.1.16700.2** o posterior. |

> [!IMPORTANT]
> Para obtener el mejor valor de protección, asegúrese de que la solución antivirus está configurada para recibir actualizaciones periódicas y características esenciales y de que las [exclusiones están configuradas.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) EDR en modo de bloque respeta las exclusiones que se definen para Antivirus de Microsoft Defender.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>¿Necesito activar el EDR en modo de bloqueo incluso cuando tengo Antivirus de Microsoft Defender en dispositivos?

Se recomienda mantener EDR en modo de bloqueo, ya Antivirus de Microsoft Defender se ejecuta en modo pasivo o en modo activo. EDR en modo de bloque proporciona otra capa de defensa con Microsoft Defender para endpoint. Permite que Defender for Endpoint lleve a cabo acciones basadas en detecciones de comportamiento EDR infracciones. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>¿EDR modo de bloqueo tendrá algún impacto en la protección antivirus de un usuario? 

EDR en modo de bloqueo no afecta a la protección antivirus de terceros que se ejecuta en los dispositivos de los usuarios. EDR en modo de bloqueo funciona si la solución antivirus principal falla algo o si hay una detección posterior a la infracción. EDR en modo de bloque funciona igual que [Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)en modo pasivo, excepto que también bloquea y corrige artefactos o comportamientos malintencionados detectados. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>¿Por qué necesito mantener la Antivirus de Microsoft Defender actualizada? 

Dado Antivirus de Microsoft Defender detecta y corrige elementos malintencionados, es importante mantenerlo actualizado. Para EDR modo de bloqueo sea eficaz, usa los modelos de aprendizaje de dispositivos más recientes, detecciones de comportamiento y heurística. La [pila de funcionalidades](https://docs.microsoft.com/windows/security/threat-protection) de Defender for Endpoint funciona de forma integrada. Para obtener el mejor valor de protección, debe mantener Antivirus de Microsoft Defender actualizado.  

### <a name="why-do-we-need-cloud-protection-on"></a>¿Por qué necesitamos protección en la nube? 

Se necesita protección en la nube para activar la característica en el dispositivo. La protección en la nube permite a [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) ofrecer la protección más reciente y la mejor basada en nuestra amplitud y profundidad de inteligencia de seguridad, junto con modelos de aprendizaje de dispositivos y comportamiento.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>¿Cómo se establece Antivirus de Microsoft Defender en modo pasivo?

Consulte [Enable Antivirus de Microsoft Defender y confirm it's in passive mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>¿Cómo confirmo Antivirus de Microsoft Defender está en modo activo o pasivo?

Para confirmar si Antivirus de Microsoft Defender se está ejecutando en modo activo o pasivo, puede usar el símbolo del sistema o PowerShell en un dispositivo que se Windows.

#### <a name="use-powershell"></a>Usar PowerShell

1. Seleccione el menú Inicio, empiece a escribir y, a `PowerShell` continuación, Windows PowerShell en los resultados.

2. Tipo `Get-MpComputerStatus`.

3. En la lista de resultados, en la **fila AMRunningMode,** busque uno de los siguientes valores:
   - `Normal` - Servicio de defender que se ejecuta normalmente. No hay ningún modo especial habilitado.
   - `Passive Mode`- Si su organización usa Microsoft Defender para Endpoint junto con una solución antivirus o antimalware que no sea de Microsoft, Antivirus de Microsoft Defender automáticamente pasa al modo pasivo. (La protección en tiempo real y las amenazas no se corrigen Antivirus de Microsoft Defender).
   - `SxS Passive Mode`- Similar al modo pasivo, pero con la opción de activar el examen periódico limitado.
   
Para obtener más información, [vea Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).

#### <a name="use-command-prompt"></a>Usar símbolo del sistema

1. Seleccione el menú Inicio, empiece a escribir y, a continuación, abra Windows símbolo del `Command Prompt` sistema en los resultados.

2. Tipo `sc query windefend`.

3. En la lista de resultados, en la **fila STATE,** confirme que el servicio se está ejecutando.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>¿Cuánto tiempo se necesita para deshabilitar EDR en modo de bloque?

Si opta por deshabilitar EDR en modo de bloqueo, el sistema puede tardar hasta 30 minutos en deshabilitar esta funcionalidad.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>¿EDR en modo de bloque se admite en Windows Server 2016?

No. EDR en modo de bloque es compatible con las siguientes versiones de Windows:

- Windows 10 (todas las versiones)
- Windows Servidor, versión 1803 o posterior 
- Windows Server 2019 

## <a name="see-also"></a>Vea también

- [Blog Community tech: Introducción a EDR en modo de bloque: Detener ataques en sus pistas](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)
- [Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

