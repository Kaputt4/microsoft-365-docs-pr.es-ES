---
title: Detección y respuesta de puntos de conexión en modo de bloque
description: Más información sobre detección y respuesta de puntos de conexión en modo de bloque
keywords: Microsoft Defender para punto de conexión, mde, EDR en modo de bloque, bloqueo de modo pasivo
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
ms.date: 04/04/2022
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: c8b3016517393b473bcae664a6044098e04ebf6d
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623597"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Detección y respuesta de Endpoint (EDR) en el modo bloqueo

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>¿Qué es EDR en modo de bloque?

[La detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) (EDR) en modo de bloque proporciona protección adicional contra artefactos malintencionados cuando Antivirus de Microsoft Defender no es el producto antivirus principal y se ejecuta en modo pasivo. EDR en modo de bloque funciona en segundo plano para corregir artefactos malintencionados detectados por las funcionalidades de EDR. Es posible que el producto antivirus principal que no es de Microsoft haya perdido estos artefactos. En el caso de los dispositivos que ejecutan Antivirus de Microsoft Defender como antivirus principal, EDR en modo de bloque proporciona una capa adicional de defensa, ya que permite a Antivirus de Microsoft Defender realizar acciones automáticas en detecciones posteriores a la vulneración, comportamiento EDR.

> [!IMPORTANT]
> EDR en modo de bloque no proporciona toda la protección disponible cuando Antivirus de Microsoft Defender protección en tiempo real está habilitada. Todas las características que dependen de Antivirus de Microsoft Defender ser la solución antivirus activa no funcionarán, incluidos los siguientes ejemplos clave:
>
> - La protección en tiempo real, incluido el examen a acceso, no está disponible cuando Antivirus de Microsoft Defender está en modo pasivo. Para más información sobre la configuración de directivas de protección en tiempo real, consulte **[Habilitación y configuración de Antivirus de Microsoft Defender protección always-on](configure-real-time-protection-microsoft-defender-antivirus.md)**.
>
> - Las características como la **[protección de red](network-protection.md)** y **[las reglas de reducción de superficie expuesta a ataques](attack-surface-reduction.md)** solo están disponibles cuando Antivirus de Microsoft Defender se ejecuta en modo activo.
>
> Se espera que la solución antivirus que no es de Microsoft proporcione estas funcionalidades.

EDR en modo de bloque se integra con [& administración de vulnerabilidades de amenazas](next-gen-threat-and-vuln-mgt.md). El equipo de seguridad de la organización recibirá una [recomendación de seguridad](tvm-security-recommendation.md) para activar EDR en modo de bloque si aún no está habilitada.

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="La recomendación de activar EDR en modo de bloque" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> Para obtener la mejor protección, asegúrese de **[implementar Microsoft Defender para punto de conexión líneas base](configure-machines-security-baseline.md)**.

Vea este vídeo para obtener información sobre por qué y cómo activar detección y respuesta de puntos de conexión (EDR) en modo de bloque, habilitar el bloqueo de comportamiento y la contención en cada fase, desde la vulneración previa hasta la posterior a la vulneración. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HjW2]

## <a name="what-happens-when-something-is-detected"></a>¿Qué ocurre cuando se detecta algo?

Cuando se activa EDR en modo de bloque y se detecta un artefacto malintencionado, Microsoft Defender para punto de conexión bloquea y corrige ese artefacto. El equipo de operaciones de seguridad verá el estado de detección como **Bloqueado** o **Impedido** en el [Centro](respond-machine-alerts.md#check-activity-details-in-action-center) de acciones, que aparece como acciones completadas.

En la imagen siguiente se muestra una instancia de software no deseado que se detectó y bloqueó a través de EDR en modo de bloque:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="Detección por EDR en modo de bloque" lightbox="images/edr-in-block-mode-detection.png":::


## <a name="enable-edr-in-block-mode"></a>Habilitar EDR en modo de bloque

> [!IMPORTANT]
> A partir de la versión de plataforma 4.18.2202.X, ahora puede establecer EDR en modo de bloque para dirigirse a grupos de dispositivos específicos mediante Intune CSP. Puede seguir estableciendo EDR en modo de bloque para todo el inquilino en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. EDR en modo de bloque se recomienda principalmente para los dispositivos que ejecutan Antivirus de Microsoft Defender en modo pasivo (se instala una solución antivirus que no es de Microsoft y está activa en el dispositivo). 

> [!TIP]
> Asegúrese de que se cumplen los [requisitos](#requirements-for-edr-in-block-mode) antes de activar EDR en modo de bloque.

### <a name="security-portal"></a>Portal de seguridad 

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) e inicie sesión.

2. Elija **Configuración** \> características **avanzadas** **generales** \> **de puntos** \> de conexión.

3. Desplácese hacia abajo y, a continuación, active **Habilitar EDR en modo de bloque**.

### <a name="intune"></a>Intune

Para crear una directiva personalizada en Intune, consulte [Implementación de OMA-URIs para dirigirse a un CSP a través de Intune y una comparación con el entorno local](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune).

Para obtener más información sobre el CSP de Defender que se usa para EDR en modo de bloque, vea "Configuration/PassiveRemediation" en [CSP de Defender](/windows/client-management/mdm/defender-csp).


## <a name="requirements-for-edr-in-block-mode"></a>Requisitos para EDR en modo de bloque

En la tabla siguiente se enumeran los requisitos de EDR en modo de bloque:

|Requisito|Detalles|
|---|---|
|Permisos|Debe tener asignado el rol Administrador global o Administrador de seguridad en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Para obtener más información, consulte [Permisos básicos](basic-permissions.md).|
|Sistema operativo|Los dispositivos deben ejecutar una de las siguientes versiones de Windows: <br/>- Windows 11 <br/>- Windows 10 (todas las versiones)<br/>- Windows Server 2022 <br/>- Windows Server 2019<br/>- Windows Server, versión 1803 o posterior<br/>- Windows Server 2016 y Windows Server 2012 R2 (con la [nueva solución de cliente unificada](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution))<sup>[[1](#fn1)]</sup>  |
|Microsoft Defender para punto de conexión|Los dispositivos deben incorporarse a Defender para punto de conexión. Consulte los siguientes artículos: <br/>- [Requisitos mínimos para Microsoft Defender para punto de conexión](minimum-requirements.md)<br/>- [Incorporación de dispositivos y configuración de funcionalidades de Microsoft Defender para punto de conexión](onboard-configure.md)<br/>- [Incorporación de servidores Windows al servicio Defender para punto de conexión](configure-server-endpoints.md)<br/>- [Nuevas funciones de Windows Server 2012 R2 y 2016 en la solución unificada moderna (versión preliminar)](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) |
|Antivirus de Microsoft Defender|Los dispositivos deben tener Antivirus de Microsoft Defender instalados y en ejecución en modo activo o pasivo. [Confirme que Antivirus de Microsoft Defender está en modo activo o pasivo](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).|
|Protección entregada en la nube|Antivirus de Microsoft Defender debe configurarse de forma que [la protección entregada en la nube esté habilitada](enable-cloud-protection-microsoft-defender-antivirus.md).|
|plataforma de Antivirus de Microsoft Defender|Los dispositivos deben estar actualizados. Para confirmar que, con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. En la línea **AMProductVersion** , debería ver **la versión 4.18.2001.10** o posterior. <p> Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md).|
|motor de Antivirus de Microsoft Defender|Los dispositivos deben estar actualizados. Para confirmar que, con PowerShell, ejecute el cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. En la línea **AMEngineVersion** , debería ver **1.1.16700.2** o superior. <p> Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md).|

<a id="fn1">(1</a>) Consulte [¿Se admite EDR en modo de bloque en Windows Server 2016 y Windows Server 2012 R2?](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2)

> [!IMPORTANT]
> Para obtener el mejor valor de protección, asegúrese de que la solución antivirus está configurada para recibir actualizaciones periódicas y características esenciales, y de que [las exclusiones están configuradas](configure-exclusions-microsoft-defender-antivirus.md). EDR en modo de bloque respeta las exclusiones definidas para Antivirus de Microsoft Defender, pero no [los indicadores definidos](manage-indicators.md) para Microsoft Defender para punto de conexión.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes.

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>¿Puedo especificar exclusiones para EDR en modo de bloque?

Si obtiene un falso positivo, puede enviar el archivo para su análisis en el [sitio de envío de Inteligencia de seguridad de Microsoft](https://www.microsoft.com/en-us/wdsi/filesubmission).

También puede definir una exclusión para Antivirus de Microsoft Defender. Consulte [Configuración y validación de exclusiones para exámenes de Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md).

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>¿Tengo que activar EDR en modo de bloque si tengo Antivirus de Microsoft Defender ejecutándose en dispositivos?

El propósito principal de EDR en modo de bloque es corregir las detecciones posteriores a la infracción que un producto antivirus que no es de Microsoft ha perdido. Hay una ventaja mínima en la habilitación de EDR en modo de bloque cuando Antivirus de Microsoft Defender está en modo activo, ya que se espera que la protección en tiempo real detecte y corrija primero las detecciones. Se recomienda habilitar EDR en modo de bloque en puntos de conexión en los que Microsoft Defender for Antivirus se ejecuta en modo pasivo. EDR detecciones se pueden corregir automáticamente mediante la [protección de PUA](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) o mediante [una investigación automatizada & funcionalidades de corrección](automated-investigations.md) en modo de bloque.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>¿Afectará EDR en modo de bloque a la protección antivirus de un usuario?

EDR en modo de bloque no afecta a la protección antivirus de terceros que se ejecuta en los dispositivos de los usuarios. EDR en modo de bloque funciona si la solución antivirus principal pierde algo o si hay una detección posterior a la vulneración. EDR en modo de bloque funciona igual que Antivirus de Microsoft Defender en modo pasivo, salvo que EDR en modo de bloque también bloquea y corrige los artefactos o comportamientos malintencionados que se detectan.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>¿Por qué tengo que mantener Antivirus de Microsoft Defender actualizado?

Dado que Antivirus de Microsoft Defender detecta y corrige elementos malintencionados, es importante mantenerlo actualizado. Para que EDR en modo de bloque sea eficaz, usa los modelos de aprendizaje de dispositivos más recientes, las detecciones de comportamiento y la heurística. La pila de funcionalidades de [Defender para punto de conexión](microsoft-defender-endpoint.md) funciona de forma integrada. Para obtener el mejor valor de protección, debe mantener Antivirus de Microsoft Defender actualizado. Consulte [Administración de actualizaciones Antivirus de Microsoft Defender y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

### <a name="why-do-we-need-cloud-protection-maps-on"></a>¿Por qué necesitamos protección en la nube (MAPS) activada?

La protección en la nube es necesaria para activar la característica en el dispositivo. La protección en la nube permite a [Defender para punto de conexión](microsoft-defender-endpoint.md) ofrecer la protección más reciente y más grande en función de nuestra amplitud y profundidad de inteligencia de seguridad, junto con los modelos de comportamiento y aprendizaje de dispositivos.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>¿Cuál es la diferencia entre el modo activo y pasivo?

Para los puntos de conexión que ejecutan Windows 10, Windows 11, Windows Server, versión 1803 o posterior, Windows Server 2019 o Windows Server 2022 cuando Antivirus de Microsoft Defender está en modo activo, se usa como antivirus principal en el dispositivo. Cuando se ejecuta en modo pasivo, Antivirus de Microsoft Defender no es el producto antivirus principal. En este caso, las amenazas no se corrigen Antivirus de Microsoft Defender en tiempo real.

> [!NOTE]
> Antivirus de Microsoft Defender solo se puede ejecutar en modo pasivo cuando el dispositivo se incorpora a Microsoft Defender para punto de conexión.

Para obtener más información, consulte [compatibilidad Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Cómo confirmar Antivirus de Microsoft Defender está en modo activo o pasivo?

Para confirmar si Antivirus de Microsoft Defender se ejecuta en modo activo o pasivo, puede usar el símbolo del sistema o PowerShell en un dispositivo que ejecuta Windows.

|Método|Procedure|
|---|---|
|PowerShell|1. Seleccione el menú Inicio, empiece a escribir `PowerShell`y, a continuación, abra Windows PowerShell en los resultados.<br/><br/>2. Escriba `Get-MpComputerStatus`.<br/><br/>3. En la lista de resultados, en la fila **AMRunningMode** , busque uno de los siguientes valores:<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>Para obtener más información, consulte [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).|
|Símbolo del sistema|1. Seleccione el menú Inicio, empiece a escribir `Command Prompt`y, a continuación, abra Windows símbolo del sistema en los resultados.<br/><br/>2. Escriba `sc query windefend`.<br/><br/>3. En la lista de resultados, en la fila **STATE** , confirme que el servicio se está ejecutando. |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>Cómo confirmar que EDR en modo de bloque está activado con Antivirus de Microsoft Defender en modo pasivo?

Puede usar PowerShell para confirmar que EDR en modo de bloque está activado con Antivirus de Microsoft Defender que se ejecutan en modo pasivo.

1. Seleccione el menú Inicio, empiece a escribir `PowerShell`y, a continuación, abra Windows PowerShell en los resultados.

2. Tipo `Get-MPComputerStatus|select AMRunningMode`.

3. Confirme que se muestra el resultado, `EDR Block Mode`, .

   > [!TIP]
   > Si Antivirus de Microsoft Defender está en modo activo, verá `Normal` en lugar de `EDR Block Mode`. Para obtener más información, consulte [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>¿Se admite EDR en modo de bloque en Windows Server 2016 y Windows Server 2012 R2?

Si Antivirus de Microsoft Defender se ejecuta en modo activo o pasivo, se admiten EDR en modo de bloque de las siguientes versiones de Windows:

- Windows 11
- Windows 10 (todas las versiones)
- Windows Server, versión 1803 o posterior 
- Windows Server 2022
- Windows Server 2019 
- Windows Server 2016 y Windows Server 2012 R2 (con la [nueva solución de cliente unificada](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution))

Con la [nueva solución de cliente unificada](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) para Windows Server 2016 y Windows Server 2012 R2, puede ejecutar EDR en modo de bloque en modo pasivo o en modo activo.

> [!NOTE]
> Windows Server 2016 y Windows Server 2012 R2 deben incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md) para que esta característica funcione. 

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>¿Cuánto tiempo tarda en deshabilitarse EDR en modo de bloque?

Si decide deshabilitar EDR en modo de bloque, el sistema puede tardar hasta 30 minutos en deshabilitar esta funcionalidad.

## <a name="see-also"></a>Consulte también

- [Blog de tech Community: Introducción a EDR en modo de bloque: Detener ataques en sus pistas](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [Bloqueo y contención de comportamientos](behavioral-blocking-containment.md)
