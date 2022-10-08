---
title: Configuración de seguridad de la protección con protección contra alteraciones
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Use la protección contra alteraciones para evitar que las aplicaciones malintencionadas cambien la configuración de seguridad importante.
keywords: malware, defender, antivirus, protección contra alteraciones
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.date: 09/23/2022
audience: ITPro
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 5f2a87f1fa8ff8130e460f46c9ac94275ba0735d
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68221332"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Configuración de seguridad de la protección con protección contra alteraciones

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

La protección contra alteraciones está disponible para los dispositivos que ejecutan una de las siguientes versiones de Windows:

- Windows 11
- Sesión múltiple de Windows 11 Enterprise 
- Windows 10
- Sesión múltiple de Windows 10 Enterprise
- Windows Server 2022
- Windows Server 2019
- Windows Server, versión 1803 o posterior
- Windows Server 2016
- Windows Server 2012 R2

> [!NOTE]
> La protección contra alteraciones en Windows Server 2012 R2 está disponible para los dispositivos incorporados mediante el paquete de solución unificado moderno. Para obtener más información, vea [Incorporación de servidores Windows al servicio de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-server-endpoints).

## <a name="overview"></a>Información general

Durante algunos tipos de ciberataques, los actores malintencionados intentan deshabilitar las características de seguridad, como la protección antivirus, en las máquinas. A los actores incorrectos les gusta deshabilitar las características de seguridad para obtener un acceso más fácil a los datos, para instalar malware o para aprovechar los datos, la identidad y los dispositivos. La protección contra alteraciones ayuda a evitar que se produzcan este tipo de cosas. Con la protección contra alteraciones, se impide que las aplicaciones malintencionadas realicen acciones como:

- Deshabilitación de la protección contra virus y amenazas
- Deshabilitación de la protección en tiempo real
- Desactivar la supervisión del comportamiento
- Deshabilitación de la protección antivirus, como IOfficeAntivirus (IOAV)
- Deshabilitación de la protección entregada en la nube
- Eliminación de actualizaciones de inteligencia de seguridad
- Deshabilitación de acciones automáticas en amenazas detectadas
- Supresión de notificaciones en la aplicación Seguridad de Windows
- Deshabilitación del examen de archivos y archivos de red

> [!IMPORTANT]
> La protección integrada (versión preliminar) incluye activar la protección contra alteraciones de forma predeterminada. Para más información sobre la protección integrada, consulte:
> - [La protección integrada ayuda a protegerse contra ransomware](built-in-protection.md) (artículo)
> - [La protección contra alteraciones se activará para todos los clientes empresariales](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-will-be-turned-on-for-all-enterprise-customers/ba-p/3616478) (entrada de blog de Tech Community)

### <a name="how-it-works"></a>Cómo funciona

La protección contra alteraciones básicamente bloquea Microsoft Defender Antivirus a sus valores seguros y predeterminados e impide que la configuración de seguridad se cambie a través de aplicaciones y métodos como:

- Configuración de opciones en el Editor del Registro en el dispositivo Windows
- Cambio de la configuración mediante cmdlets de PowerShell
- Edición o eliminación de la configuración de seguridad a través de directiva de grupo

La protección contra alteraciones no impide que vea la configuración de seguridad. Además, la protección contra alteraciones no afecta al modo en que las aplicaciones antivirus que no son de Microsoft se registran con la aplicación Seguridad de Windows. Si su organización usa Windows 10 Enterprise E5, los usuarios individuales no pueden cambiar la configuración de protección contra alteraciones; en esos casos, el equipo de seguridad administra la protección contra alteraciones.

### <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

|Para realizar esta tarea...|Consulte esta sección...|
|---|---|
|Administración de la protección contra alteraciones en el inquilino <p> Uso del portal de Microsoft 365 Defender para activar o desactivar la protección contra alteraciones|[Administración de la protección contra alteraciones para la organización mediante Microsoft 365 Defender](manage-tamper-protection-microsoft-365-defender.md)|
|Ajuste de la configuración de protección contra alteraciones en la organización <p> Use Intune (Microsoft Endpoint Manager) para activar o desactivar la protección contra alteraciones. Puede configurar la protección contra alteraciones para algunos o todos los usuarios con este método.|[Administrar la protección contra alteraciones de su organización mediante Microsoft Endpoint Manager](manage-tamper-protection-microsoft-endpoint-manager.md)|
|Activar (o desactivar) la protección contra alteraciones para la organización con Configuration Manager|[Administración de la protección contra alteraciones de la organización mediante la asociación de inquilinos con Configuration Manager, versión 2006](manage-tamper-protection-configuration-manager.md)|
|Activar (o desactivar) la protección contra alteraciones para un dispositivo individual|[Administración de la protección contra alteraciones en un dispositivo individual](manage-tamper-protection-individual-device.md)|
|Ver detalles sobre los intentos de manipulación en dispositivos|[Visualización de información sobre intentos de manipulación](#view-information-about-tampering-attempts)|
|Revisión de las recomendaciones de seguridad|[Revisión de las recomendaciones de seguridad](#review-your-security-recommendations)|
|Revise la lista de preguntas más frecuentes (P+F)|[Examinar las preguntas más frecuentes](faqs-tamper-protection.md)|

## <a name="potential-dependency-on-cloud-protection"></a>Posible dependencia de la protección en la nube  
  
En función del método o la herramienta de administración que use para habilitar la protección contra alteraciones, puede haber una dependencia de la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube. La protección entregada en la nube también se conoce como protección en la nube o Servicio de protección avanzada de Microsoft (MAPS).

En la tabla siguiente se proporcionan detalles sobre los métodos, las herramientas y las dependencias.

| Cómo está habilitada la protección contra alteraciones | Dependencia de la protección en la nube |
|---|---|
|Microsoft Intune|No|
|Configuration Manager de punto de conexión de Microsoft con asociación de inquilinos|No|
|portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com))|Yes|

## <a name="are-you-using-windows-server-2012-r2-2016-or-windows-version-1709-1803-or-1809"></a>¿Usa Windows Server 2012 R2, 2016 o Windows, versión 1709, 1803 o 1809?

Si usa Windows Server 2012 R2 mediante la solución unificada moderna, Windows Server 2016, Windows 10 versión 1709, 1803 o [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), no verá **Protección contra alteraciones** en la aplicación Seguridad de Windows. En su lugar, puede usar PowerShell para determinar si está habilitada la protección contra alteraciones.

En Windows Server 2016, la aplicación Configuración no reflejará con precisión el estado de la protección en tiempo real cuando se habilita la protección contra alteraciones.

### <a name="use-powershell-to-determine-whether-tamper-protection-and-real-time-protection-are-turned-on"></a>Uso de PowerShell para determinar si la protección contra alteraciones y la protección en tiempo real están activadas

1. Abra la aplicación Windows PowerShell.

2. Use el cmdlet De PowerShell [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) .

3. En la lista de resultados, busque `IsTamperProtected` o `RealTimeProtectionEnabled`. (Un valor de *true* significa que la protección contra alteraciones está habilitada).

## <a name="view-information-about-tampering-attempts"></a>Visualización de información sobre intentos de manipulación

Los intentos de manipulación suelen indicar ciberataques más grandes. Los actores incorrectos intentan cambiar la configuración de seguridad como una manera de conservar y mantenerse sin ser detectados. Si forma parte del equipo de seguridad de su organización, puede ver información sobre estos intentos y, a continuación, realizar las acciones adecuadas para mitigar las amenazas.

Cuando se detecta un intento de manipulación, se genera una alerta en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/portal-overview) ([https://security.microsoft.com](https://security.microsoft.com)).

Con la [detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) y las funcionalidades [avanzadas de búsqueda](advanced-hunting-overview.md) en Microsoft Defender para punto de conexión, el equipo de operaciones de seguridad puede investigar y abordar estos intentos.

## <a name="review-your-security-recommendations"></a>Revisión de las recomendaciones de seguridad

La protección contra alteraciones se integra con [las funcionalidades de Administración de vulnerabilidades de Microsoft Defender](next-gen-threat-and-vuln-mgt.md). [Las recomendaciones de seguridad](tvm-security-recommendation.md) incluyen asegurarse de que la protección contra alteraciones está activada. Por ejemplo, puede buscar en *la manipulación*. En los resultados, puede seleccionar **Activar protección contra alteraciones** para obtener más información y activarla.

Para más información sobre Administración de vulnerabilidades de Microsoft Defender, consulte [Información del panel: Administración de vulnerabilidades de Defender](tvm-dashboard-insights.md#dashboard-insights---threat-and-vulnerability-management).


> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Ayuda a proteger equipos Windows con Endpoint Protection para Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Obtener información general de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint)
- [Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md)
- [Habilitación del modo de solución de problemas](enable-troubleshooting-mode.md)
- [Escenarios del modo de resolución de problemas](troubleshooting-mode-scenarios.md)
