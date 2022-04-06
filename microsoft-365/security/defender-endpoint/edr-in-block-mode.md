---
title: Detección y respuesta de puntos de conexión en modo de bloqueo
description: Obtenga información sobre detección y respuesta de puntos de conexión en modo de bloque
keywords: Microsoft Defender para endpoint, mde, EDR en modo de bloqueo, bloqueo de modo pasivo
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
- admindeeplinkDEFENDER
ms.date: 03/18/2022
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: 151fb8de088531b9a9f053fc2b5d3c433055e21f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473131"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Detección y respuesta de Endpoint (EDR) en el modo bloqueo

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>¿Qué EDR en modo de bloque?

[La detección](overview-endpoint-detection-response.md) y respuesta de puntos de conexión (EDR) en modo de bloqueo proporciona protección adicional contra artefactos malintencionados cuando Antivirus de Microsoft Defender no es el producto antivirus principal y se ejecuta en modo pasivo. EDR en modo de bloqueo funciona en segundo plano para corregir artefactos malintencionados detectados por EDR funciones. Es posible que el producto antivirus principal que no es Microsoft no haya perdido estos artefactos. Para los dispositivos que ejecutan Antivirus de Microsoft Defender como su antivirus principal, EDR en modo de bloqueo proporciona una capa adicional de defensa al permitir que Antivirus de Microsoft Defender tome acciones automáticas en detecciones de EDR comportamiento posteriores a la infracción.

> [!IMPORTANT]
> EDR en modo de bloqueo no proporciona toda la protección disponible cuando Antivirus de Microsoft Defender la protección en tiempo real está habilitada. Todas las características que dependen de Antivirus de Microsoft Defender para ser la solución antivirus activa no funcionarán, incluidos los siguientes ejemplos clave:
>
> - La protección en tiempo real, incluido el examen en tiempo real, no está disponible cuando Antivirus de Microsoft Defender está en modo pasivo. Para obtener más información acerca de la configuración de directivas de protección en tiempo real, **[consulte Habilitar y configurar Antivirus de Microsoft Defender protección siempre activa](configure-real-time-protection-microsoft-defender-antivirus.md)**.
>
> - Las características como **[la protección de](network-protection.md)** red y las reglas **[de](attack-surface-reduction.md)** reducción de superficie de ataque solo están disponibles cuando Antivirus de Microsoft Defender se ejecuta en modo activo.
>
> Se espera que la solución antivirus que no sea de Microsoft proporciona estas funcionalidades.

EDR en modo de bloqueo se integra con [la amenaza & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md). El equipo de seguridad de la organización recibirá una [](tvm-security-recommendation.md) recomendación de seguridad para activar EDR en modo de bloqueo si aún no está habilitada.

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="La recomendación de activar el EDR en modo de bloqueo" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> Para obtener la mejor protección, asegúrese de implementar **[Las líneas base de Microsoft Defender para puntos de conexión](configure-machines-security-baseline.md)**.

## <a name="what-happens-when-something-is-detected"></a>¿Qué sucede cuando se detecta algo?

Cuando EDR en modo de bloque está activado y se detecta un artefacto malintencionado, Microsoft Defender para endpoint bloquea y corrige ese artefacto. El equipo de operaciones de seguridad verá el estado de detección como **Bloqueado** o **Impedido** en el Centro [de](respond-machine-alerts.md#check-activity-details-in-action-center) acciones, enumerado como acciones completadas.

La siguiente imagen muestra una instancia de software no deseado que se detectó y bloqueó a través EDR en modo de bloqueo:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="La detección por EDR en modo de bloque" lightbox="images/edr-in-block-mode-detection.png":::


## <a name="enable-edr-in-block-mode"></a>Habilitar EDR en modo de bloque

> [!IMPORTANT]
> A partir de la versión 4.18.2202.X de la plataforma, ahora puedes establecer EDR en modo de bloqueo para que se alope a grupos de dispositivos específicos mediante LOSP de Intune. Puede seguir configurando los EDR en modo de bloque en todo el espacio empresarial en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>. EDR en modo de bloqueo se recomienda principalmente para dispositivos que ejecutan Antivirus de Microsoft Defender en modo pasivo (una solución antivirus que no es de Microsoft está instalada y activa en el dispositivo). 

> [!TIP]
> Asegúrese de que se [cumplen](#requirements-for-edr-in-block-mode) los requisitos antes de activar EDR en modo de bloque.

### <a name="security-portal"></a>Portal de seguridad 

1. Vaya al portal Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) e inicie sesión.

2. Elija **Configuración** \> **de extremos generales** \>  \> **avanzados**.

3. Desplácese hacia abajo y, a continuación, active **Habilitar EDR en modo de bloque**.

### <a name="intune"></a>Intune

Para crear una directiva personalizada en Intune, [consulte Deploy OMA-URIs to target a CSP through Intune y a comparison to on-premises](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune).

Para obtener más información sobre el CSP de Defender que se EDR en modo de bloque, consulta "Configuración/PassiveRemediation" en [CSP de Defender](/windows/client-management/mdm/defender-csp).


## <a name="requirements-for-edr-in-block-mode"></a>Requisitos para EDR en modo de bloque

En la tabla siguiente se enumeran los requisitos EDR en modo de bloque:

|Requisito|Detalles|
|---|---|
|Permisos|Debe tener asignado el rol Administrador global o Administrador de seguridad [en Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Para obtener más información, vea [Basic permissions](basic-permissions.md).|
|Sistema operativo|Los dispositivos deben ejecutar una de las siguientes versiones de Windows: <br/>- Windows 11 <br/>- Windows 10 (todas las versiones)<br/>- Windows Server 2022 <br/>- Windows Server 2019<br/>- Windows server, versión 1803 o posterior<br/>- Windows Server 2016 y Windows Server 2012 R2 (con la [nueva solución de cliente unificada](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview))<sup>[[1](#fn1)]</sup>  |
|Microsoft Defender para punto de conexión|Los dispositivos deben incorporarse a Defender for Endpoint. Consulte los siguientes artículos: <br/>- [Requisitos mínimos para Microsoft Defender para endpoint](minimum-requirements.md)<br/>- [Incorporar dispositivos y configurar las capacidades de Microsoft Defender para puntos de conexión](onboard-configure.md)<br/>- [Incorporación Windows servidores al servicio Defender for Endpoint](configure-server-endpoints.md)<br/>- [Nuevas Windows Server 2012 R2 y 2016 en la solución unificada moderna (versión preliminar)](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) |
|Antivirus de Microsoft Defender|Los dispositivos deben Antivirus de Microsoft Defender instalados y en ejecución en modo activo o en modo pasivo. [Confirme Antivirus de Microsoft Defender está en modo activo o pasivo](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).|
|Protección entregada en la nube|Antivirus de Microsoft Defender debe configurarse de modo que [la protección entregada en la nube esté habilitada](enable-cloud-protection-microsoft-defender-antivirus.md).|
|Antivirus de Microsoft Defender plataforma|Los dispositivos deben estar actualizados. Para confirmar, con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. En la **línea AMProductVersion** , debería ver **4.18.2001.10** o posterior. <p> Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md).|
|Antivirus de Microsoft Defender motor|Los dispositivos deben estar actualizados. Para confirmar, con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. En la **línea AMEngineVersion** , debería ver **1.1.16700.2** o posterior. <p> Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md).|

(<a id="fn1">1</a>) Vea [¿se EDR en modo de bloque en Windows Server 2016 y Windows Server 2012 R2?](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2)

> [!IMPORTANT]
> Para obtener el mejor valor de protección, asegúrese de que la solución antivirus está configurada para recibir actualizaciones periódicas y características esenciales, y que las [exclusiones están configuradas](configure-exclusions-microsoft-defender-antivirus.md). EDR en modo de bloque respeta las exclusiones que se definen para Antivirus de Microsoft Defender, pero no los indicadores [definidos](manage-indicators.md) para Microsoft Defender para endpoint.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>¿Puedo especificar exclusiones para EDR en modo de bloque?

En el caso de obtener un falso positivo, puede enviar el archivo para su análisis en el [Inteligencia de seguridad de Microsoft de envío](https://www.microsoft.com/en-us/wdsi/filesubmission).

También puede definir una exclusión para Antivirus de Microsoft Defender. Consulte [Configure and validate exclusions for Antivirus de Microsoft Defender scans](configure-exclusions-microsoft-defender-antivirus.md).

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>¿Necesito activar el EDR en modo de bloqueo si tengo Antivirus de Microsoft Defender en dispositivos?

El objetivo principal de EDR en modo de bloqueo es corregir las detecciones posteriores a la infracción que no se han detectado en un producto antivirus que no es de Microsoft. Sin embargo, se recomienda mantener EDR en modo de bloque activado, tanto si Antivirus de Microsoft Defender se ejecuta en modo pasivo como en modo activo.

- Cuando Antivirus de Microsoft Defender está en modo pasivo, EDR en modo de bloque proporciona otra capa de defensa junto con Microsoft Defender para Endpoint.

- Cuando Antivirus de Microsoft Defender está en modo activo, EDR en modo de bloqueo no proporciona análisis adicional, pero permite a Antivirus de Microsoft Defender realizar acciones automáticas en detecciones posteriores a la infracción y de EDR comportamiento.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>¿EDR en modo de bloqueo afectará a la protección antivirus de un usuario?

EDR en modo de bloqueo no afecta a la protección antivirus de terceros que se ejecuta en los dispositivos de los usuarios. EDR en modo de bloqueo funciona si la solución antivirus principal falla algo o si hay una detección posterior a la infracción. EDR en modo de bloque funciona igual que Antivirus de Microsoft Defender en modo pasivo, excepto que EDR en modo de bloque también bloquea y corrige artefactos o comportamientos malintencionados detectados.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>¿Por qué necesito mantener la Antivirus de Microsoft Defender actualizada?

Dado Antivirus de Microsoft Defender detecta y corrige elementos malintencionados, es importante mantenerlo actualizado. Para EDR modo de bloqueo sea eficaz, usa los modelos de aprendizaje de dispositivos más recientes, detecciones de comportamiento y heurística. La [pila de funcionalidades de Defender for Endpoint](microsoft-defender-endpoint.md) funciona de forma integrada. Para obtener el mejor valor de protección, debe mantener Antivirus de Microsoft Defender actualizado. Consulte [Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

### <a name="why-do-we-need-cloud-protection-maps-on"></a>¿Por qué necesitamos protección en la nube (MAPS) en?

Se necesita protección en la nube para activar la característica en el dispositivo. La protección en la nube permite a [Defender for Endpoint](microsoft-defender-endpoint.md) ofrecer la protección más reciente y la mejor basada en nuestra amplitud y profundidad de inteligencia de seguridad, junto con modelos de aprendizaje de dispositivos y comportamiento.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>¿Cuál es la diferencia entre el modo activo y el pasivo?

Para los puntos de conexión que ejecutan Windows 10, Windows 11, Windows Server, versión 1803 o posterior, Windows Server 2019 o Windows Server 2022 cuando Antivirus de Microsoft Defender está en modo activo, se usa como el antivirus principal del dispositivo. Cuando se ejecuta en modo pasivo, Antivirus de Microsoft Defender no es el producto antivirus principal. En este caso, las amenazas no se corrigen Antivirus de Microsoft Defender en tiempo real.

> [!NOTE]
> Antivirus de Microsoft Defender puede ejecutarse en modo pasivo solo cuando el dispositivo está incorporado a Microsoft Defender para Endpoint.

Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad.](microsoft-defender-antivirus-compatibility.md)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>¿Cómo confirmo Antivirus de Microsoft Defender está en modo activo o pasivo?

Para confirmar si Antivirus de Microsoft Defender se está ejecutando en modo activo o pasivo, puede usar el símbolo del sistema o PowerShell en un dispositivo que ejecute Windows.

|Método|Procedure|
|---|---|
|PowerShell|1. Seleccione el menú Inicio, empiece a escribir `PowerShell`y, a continuación, abra Windows PowerShell en los resultados.<br/><br/>2. Escriba `Get-MpComputerStatus`.<br/><br/>3. En la lista de resultados, en la fila **AMRunningMode** , busque uno de los siguientes valores:<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>Para obtener más información, [vea Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).|
|Símbolo del sistema|1. Seleccione el menú Inicio, empiece a escribir `Command Prompt`y, a continuación, abra Windows símbolo del sistema en los resultados.<br/><br/>2. Escriba `sc query windefend`.<br/><br/>3. En la lista de resultados, en la fila **STATE** , confirme que el servicio se está ejecutando. |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>¿Cómo confirmo que EDR modo de bloqueo está activado con Antivirus de Microsoft Defender en modo pasivo?

Puede usar PowerShell para confirmar que el EDR en modo de bloque está activado Antivirus de Microsoft Defender en modo pasivo.

1. Seleccione el menú Inicio, empiece a escribir `PowerShell`y, a continuación, abra Windows PowerShell en los resultados.

2. Tipo `Get-MPComputerStatus|select AMRunningMode`.

3. Confirme que se muestra el resultado, `EDR Block Mode`, .

   > [!TIP]
   > Si Antivirus de Microsoft Defender está en modo activo, verá en lugar `Normal` de `EDR Block Mode`. Para obtener más información, [vea Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>¿EDR en modo de bloque se admite en Windows Server 2016 y Windows Server 2012 R2?

Si Antivirus de Microsoft Defender se ejecuta en modo activo o pasivo, EDR en modo de bloque es compatible con las siguientes versiones de Windows:

- Windows 11
- Windows 10 (todas las versiones)
- Windows server, versión 1803 o posterior 
- Windows Server 2022
- Windows Server 2019 
- Windows Server 2016 y Windows Server 2012 R2 (con la [nueva solución de cliente unificada](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview))

Con la [nueva solución](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) de cliente unificada para Windows Server 2016 y Windows Server 2012 R2, puede ejecutar EDR en modo de bloqueo en modo pasivo o en modo activo.

> [!NOTE]
> Windows Server 2016 y Windows Server 2012 R2 deben incorporarse con las instrucciones de [Onboard Windows servers](configure-server-endpoints.md) para que esta característica funcione. 

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>¿Cuánto tiempo se necesita para deshabilitar EDR modo de bloque?

Si decide deshabilitar EDR en modo de bloqueo, el sistema puede tardar hasta 30 minutos en deshabilitar esta funcionalidad.

## <a name="see-also"></a>Vea también

- [Blog Community tech: Introducción a EDR en modo de bloque: Detener ataques en sus pistas](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)
