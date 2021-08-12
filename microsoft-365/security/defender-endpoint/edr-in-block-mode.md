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
ms.date: 07/20/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 822d0cb12aa42d62fde3df1ec3632e400019d2e1
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53591228"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Detección y respuesta de puntos de conexión (EDR) en modo de bloqueo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>¿Qué EDR en modo de bloqueo?

[La detección](overview-endpoint-detection-response.md) y respuesta de puntos de conexión (EDR) en modo de bloqueo proporciona protección adicional contra artefactos malintencionados cuando Antivirus de Microsoft Defender no es el producto antivirus principal y se ejecuta en modo pasivo. EDR en modo de bloqueo funciona en segundo plano para corregir artefactos malintencionados detectados por EDR funcionalidades. Es posible que el producto antivirus principal que no es Microsoft no haya perdido estos artefactos. 

> [!IMPORTANT]
> EDR en modo de bloqueo no proporciona toda la protección disponible cuando Antivirus de Microsoft Defender la protección en tiempo real está habilitada. Todas las características que dependen de Antivirus de Microsoft Defender para ser la solución antivirus activa no funcionarán, incluidos los siguientes ejemplos clave: 
> 
> - La protección en tiempo real, incluido el examen en tiempo real, no está disponible cuando Antivirus de Microsoft Defender está en modo pasivo. Para obtener más información acerca de las opciones de directiva de protección en tiempo real, vea Habilitar y configurar Antivirus de Microsoft Defender **[protección siempre activa.](configure-real-time-protection-microsoft-defender-antivirus.md)**
> - Las características como **[la protección de](network-protection.md)** red y las reglas **[de](attack-surface-reduction.md)** reducción de superficie de ataque solo están disponibles cuando Antivirus de Microsoft Defender se ejecuta en modo activo. 
> 
> Se espera que la solución antivirus que no sea de Microsoft proporciona estas funcionalidades. 

EDR en modo de bloque se integra con [la amenaza & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md). El equipo de seguridad de [](tvm-security-recommendation.md) la organización recibirá una recomendación de seguridad para activar EDR en modo de bloqueo si aún no está habilitado. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="recomendación de activar el EDR en modo de bloqueo":::

> [!TIP]
> Para obtener la mejor protección, asegúrese de implementar Las líneas base de **[Microsoft Defender para endpoint .](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>¿Qué sucede cuando se detecta algo?

Cuando EDR en modo de bloque está activado y se detecta un artefacto malintencionado, Microsoft Defender para endpoint bloquea y corrige ese artefacto. El equipo de operaciones de seguridad verá el estado de detección como **Bloqueado** o **Impedido** en el Centro de [acciones,](respond-machine-alerts.md#check-activity-details-in-action-center)que aparece como acciones completadas.

La siguiente imagen muestra una instancia de software no deseado que se detectó y bloqueó a través EDR en modo de bloqueo:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR en modo de bloque detectó algo":::


## <a name="enable-edr-in-block-mode"></a>Habilitar EDR en modo de bloque

> [!TIP]
> Asegúrese de que se [cumplen](#requirements-for-edr-in-block-mode) los requisitos antes de activar EDR en modo de bloque.

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com/](https://security.microsoft.com/) ) e inicie sesión. 

2. Elija **Configuración**  >  **endpoints**  >  **General**  >  **Advanced .**

3. Desplácese hacia abajo y, a continuación, active **Habilitar EDR en modo de bloque**.


> [!NOTE]
> EDR en modo de bloque solo se puede desactivar en el portal de Microsoft 365 Defender ( ) o en el [https://security.microsoft.com](https://security.microsoft.com) antiguo Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). No puede usar claves del Registro, Microsoft Intune o directiva de grupo para habilitar o deshabilitar EDR en modo de bloque.

## <a name="requirements-for-edr-in-block-mode"></a>Requisitos para EDR en modo de bloque

| Requisito  | Detalles  |
|---------|---------|
| Permisos | Debe tener asignado el rol Administrador global o Administrador de seguridad en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Para obtener más información, vea [Basic permissions](basic-permissions.md). |
| Sistema operativo     | Los dispositivos deben ejecutar una de las siguientes versiones de Windows: <br/>- Windows 10 (todas las versiones) <br/>- Windows server, versión 1803 o posterior <br/>- Windows Server 2019 <br/>- Windows Server 2016 (solo cuando Antivirus de Microsoft Defender está en modo activo)     |
| Microsoft Defender para punto de conexión     | Los dispositivos deben incorporarse a Defender for Endpoint. Consulte [Requisitos mínimos de Microsoft Defender para endpoint](minimum-requirements.md).       |
| Antivirus de Microsoft Defender  | Los dispositivos deben Antivirus de Microsoft Defender instalados y en ejecución en modo activo o en modo pasivo. [Confirme Antivirus de Microsoft Defender está en modo activo o pasivo](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode). |
| Protección entregada en la nube | Antivirus de Microsoft Defender debe configurarse de modo que [la protección entregada en la nube esté habilitada.](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Antivirus de Microsoft Defender plataforma | Los dispositivos deben estar actualizados. Para confirmar, con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. En la **línea AMProductVersion,** debería ver **4.18.2001.10** o posterior. <p> Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md). |
| Antivirus de Microsoft Defender motor | Los dispositivos deben estar actualizados. Para confirmar, con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. En la **línea AMEngineVersion,** debería ver **1.1.16700.2** o posterior. <p> Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md). |

> [!IMPORTANT]
> Para obtener el mejor valor de protección, asegúrese de que la solución antivirus está configurada para recibir actualizaciones periódicas y características esenciales y de que las [exclusiones están configuradas.](configure-exclusions-microsoft-defender-antivirus.md) EDR en modo de bloque respeta las exclusiones que se definen para Antivirus de Microsoft Defender, pero no los indicadores [definidos](manage-indicators.md) para Microsoft Defender para endpoint.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>¿Necesito activar el EDR en modo de bloqueo si tengo Antivirus de Microsoft Defender en dispositivos?

El objetivo principal de EDR en modo de bloqueo es corregir las detecciones posteriores a la infracción que no se han detectado en un producto antivirus que no es de Microsoft. Sin embargo, se recomienda mantener EDR en modo de bloque activado, tanto si Antivirus de Microsoft Defender se ejecuta en modo pasivo como en modo activo. 

- Cuando Antivirus de Microsoft Defender está en modo pasivo, EDR en modo de bloque proporciona otra capa de defensa junto con Microsoft Defender para endpoint. 
- Cuando Antivirus de Microsoft Defender está en modo activo, EDR en modo de bloqueo no proporciona análisis adicional, pero sí permite a Defender for Endpoint realizar acciones automáticas en detecciones de EDR comportamiento posteriores a la infracción.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>¿EDR en modo de bloqueo afectará a la protección antivirus de un usuario? 

EDR en modo de bloqueo no afecta a la protección antivirus de terceros que se ejecuta en los dispositivos de los usuarios. EDR en modo de bloqueo funciona si la solución antivirus principal falla algo o si hay una detección posterior a la infracción. EDR en modo de bloque funciona igual que Antivirus de Microsoft Defender en modo pasivo, excepto que EDR en modo de bloque también bloquea y corrige artefactos o comportamientos malintencionados detectados.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>¿Por qué necesito mantener la Antivirus de Microsoft Defender actualizada? 

Dado Antivirus de Microsoft Defender detecta y corrige elementos malintencionados, es importante mantenerlo actualizado. Para EDR modo de bloqueo sea eficaz, usa los modelos de aprendizaje de dispositivos más recientes, detecciones de comportamiento y heurística. La [pila de funcionalidades](microsoft-defender-endpoint.md) de Defender for Endpoint funciona de forma integrada. Para obtener el mejor valor de protección, debe mantener Antivirus de Microsoft Defender actualizado. Consulte [Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md). 

### <a name="why-do-we-need-cloud-protection-maps-on"></a>¿Por qué necesitamos protección en la nube (MAPS) en? 

Se necesita protección en la nube para activar la característica en el dispositivo. La protección en la nube permite a [Defender for Endpoint](microsoft-defender-endpoint.md) ofrecer la protección más reciente y la mejor basada en nuestra amplitud y profundidad de inteligencia de seguridad, junto con modelos de aprendizaje de dispositivos y comportamiento.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>¿Cuál es la diferencia entre el modo activo y el pasivo?

Para los puntos de conexión que ejecutan Windows 10, Windows Server, versión 1803 o posterior, o Windows Server 2019, cuando Antivirus de Microsoft Defender está en modo activo, se usa como el antivirus principal del dispositivo. Cuando se ejecuta en modo pasivo, Antivirus de Microsoft Defender no es el producto antivirus principal. En este caso, las amenazas no se corrigen Antivirus de Microsoft Defender en tiempo real.

> [!NOTE]
> Antivirus de Microsoft Defender puede ejecutarse en modo pasivo solo cuando el dispositivo está incorporado a Microsoft Defender para Endpoint.

Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md).

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>¿Cómo confirmo Antivirus de Microsoft Defender está en modo activo o pasivo?

Para confirmar si Antivirus de Microsoft Defender se está ejecutando en modo activo o pasivo, puede usar el símbolo del sistema o PowerShell en un dispositivo que se Windows.

|Método  |Procedure  |
|---------|---------|
| PowerShell     | 1. Seleccione el menú Inicio, empiece a escribir y, a continuación, `PowerShell` abra Windows PowerShell en los resultados. <p>2. Escriba `Get-MpComputerStatus` . <p>3. En la lista de resultados, en la fila **AMRunningMode,** busque uno de los siguientes valores: <br/>- `Normal` <br/>- `Passive Mode` <p>Para obtener más información, [vea Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).        |
|Símbolo del sistema     | 1. Seleccione el menú Inicio, empiece a escribir y, a continuación, abra Windows símbolo del `Command Prompt` sistema en los resultados. <p>2. Escriba `sc query windefend` . <p>3. En la lista de resultados, en la fila **STATE,** confirme que el servicio se está ejecutando.         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>¿Cómo confirmo que el EDR en modo de bloque está activado con Antivirus de Microsoft Defender en modo pasivo?

Puede usar PowerShell para confirmar que el EDR en modo de bloque está activado Antivirus de Microsoft Defender en modo pasivo.

1. Seleccione el menú Inicio, empiece a escribir y, a `PowerShell` continuación, abra Windows PowerShell en los resultados. 

2. Tipo `Get-MPComputerStatus | select AMRunningMode`.

3. Confirme que se muestra `EDR Block Mode` el resultado, , .

   > [!TIP]
   > Si Antivirus de Microsoft Defender está en modo activo, verá `Normal` en lugar de `EDR Block Mode` . Para obtener más información, [vea Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>¿EDR en modo de bloque se admite en Windows Server 2016?

Si Antivirus de Microsoft Defender se ejecuta en modo activo o pasivo, EDR en modo de bloque se admite de las siguientes versiones de Windows:

- Windows 10 (todas las versiones)
- Windows Servidor, versión 1803 o posterior 
- Windows Server 2019 

#### <a name="what-about-windows-server-2016"></a>¿Qué hay Windows Server 2016? 

Si Windows Server 2016 se Antivirus de Microsoft Defender en modo activo y el extremo se incorpora a Defender para endpoint, se admite técnicamente EDR en modo de bloqueo. Sin embargo, EDR en modo de bloqueo está pensado para ser una protección adicional cuando Antivirus de Microsoft Defender no es la solución antivirus principal en un extremo. En esos casos, Antivirus de Microsoft Defender se ejecuta en modo pasivo. 

Actualmente, la ejecución Antivirus de Microsoft Defender en modo pasivo no se admite en Windows Server 2016. Para obtener más información, vea Antivirus de Microsoft Defender antivirus y soluciones antimalware que no son [de Microsoft.](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>¿Cuánto tiempo se necesita para deshabilitar EDR en modo de bloque?

Si decide deshabilitar EDR en modo de bloqueo, el sistema puede tardar hasta 30 minutos en deshabilitar esta funcionalidad.

## <a name="see-also"></a>Vea también

- [Blog Community tech: Introducción a EDR en modo de bloque: Detener ataques en sus pistas](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)

