---
title: Administrar Microsoft Defender para endpoint con Intune
description: Obtenga información sobre cómo administrar Microsoft Defender para endpoint con Intune
keywords: post-migration, manage, operations, maintenance, utilization, intune, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: d8396c352e593f9922b11e23119f7d9718eaf752
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934230"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Administrar Microsoft Defender para endpoint con Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Se recomienda usar [Microsoft Endpoint Manager](https://docs.microsoft.com/mem), que incluye Microsoft Intune (Intune) para administrar las características de protección contra amenazas de la organización para dispositivos (también denominados puntos de conexión). [Obtenga más información sobre Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview).

En este artículo se describe cómo encontrar la configuración de Microsoft Defender para endpoints en Intune y se enumeran las distintas tareas que puede realizar.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Buscar la configuración de Microsoft Defender para puntos de conexión en Intune

> [!IMPORTANT]
> Debe ser administrador global o administrador de servicios en Intune para configurar las opciones descritas en este artículo. Para obtener más información, vea **[Tipos de administradores (Intune).](https://docs.microsoft.com/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Vaya a Azure Portal ( [https://portal.azure.com](https://portal.azure.com) ) e inicie sesión.

2. En **Servicios de Azure,** elija **Intune**.

3. En el panel de navegación de la izquierda, elija **Configuración del** dispositivo y, a continuación, en **Administrar**, elija **Perfiles**.

4. Seleccione un perfil existente o cree uno nuevo.

> [!TIP]
> ¿Necesita ayuda? Consulte **[Uso de Microsoft Defender para endpoint con Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**.  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Configurar Microsoft Defender para endpoint con Intune

En la tabla siguiente se enumeran varias tareas que puede realizar para configurar Microsoft Defender para endpoint con Intune. No es necesario configurar todo a la vez; elija una tarea, lea los recursos correspondientes y, a continuación, continúe.

|Tarea  |Recursos para obtener más información  |
|---------|---------|
|**Administrar los dispositivos de la** organización con Intune para proteger esos dispositivos y datos almacenados en ellos     |[Proteger los dispositivos con Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/device-protect)         |
|**Integrar Microsoft Defender para endpoint con Intune** como una solución de Mobile Threat Defense <br/>*(para dispositivos Android y dispositivos que ejecutan Windows 10 o posterior)*   |[Exigir el cumplimiento de Microsoft Defender para endpoint con acceso condicional en Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)         |
|**Usar el acceso condicional** para controlar los dispositivos y aplicaciones que se pueden conectar a los recursos de correo electrónico y empresa |[Configurar el acceso condicional en Microsoft Defender para el extremo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Configurar la configuración de Antivirus de Microsoft Defender** con el proveedor de servicios de configuración de directivas ( CSP de [directiva](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)) |[Restricciones de dispositivos: Antivirus de Microsoft Defender](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[CSP de directiva: Microsoft Defender para el punto de conexión](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)  | 
|**Si es necesario, especifique exclusiones para Antivirus de Microsoft Defender** <br/><br/>*Por lo general, no es necesario aplicar exclusiones. Antivirus de Microsoft Defender incluye una serie de exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos, como los que se usan en la administración empresarial, la administración de bases de datos y otros escenarios empresariales.* |[Recomendaciones de detección de virus para equipos enterprise que ejecutan versiones compatibles actualmente de Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Restricciones de dispositivos: Exclusiones de Antivirus de Microsoft Defender para dispositivos Windows 10](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Configurar exclusiones de Antivirus de Microsoft Defender en Windows Server 2016 o 2019](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Configurar las reglas de reducción de superficie de ataque** para dirigirse a comportamientos de software que suelen ser abusados por atacantes<br/><br/>*Configura al principio las reglas de reducción de superficie de ataque en modo [auditoría](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender) (durante al menos una semana y hasta dos meses). Puede supervisar el estado con Power BI ([obtener nuestra plantilla](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)) y, a continuación, establecer esas reglas en modo activo cuando esté listo.* |[Modo auditoría en Microsoft Defender para endpoint ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Protección de puntos de conexión: Reducción de superficie de ataque](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Más información sobre las reglas de reducción de superficie de ataque](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Entrada de blog de la Comunidad Tecnológica: Desmitificando reglas de reducción de superficie de ataque - Parte 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Configurar el filtrado de red para** bloquear las conexiones salientes de cualquier aplicación a direcciones IP o dominios con reputación baja  <br/><br/>*El filtrado de red también se conoce como [protección de red](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/network-protection).*<br/><br/>*Asegúrate de que los dispositivos Windows 10 tengan instaladas las últimas actualizaciones de la plataforma [antimalware.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)*|[Protección de puntos de conexión: filtrado de red](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Revisar eventos de protección de red en el Visor de eventos de Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Configurar el acceso controlado a carpetas** para proteger contra ransomware <br/><br/>*[El acceso controlado a](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) carpetas también se conoce como protección antiransomware.*  |[Protección de extremo: acceso controlado a carpetas](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Habilitar el acceso controlado a carpetas en Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Configurar la protección contra vulnerabilidades** de seguridad para proteger los dispositivos de la organización contra malware que usa vulnerabilidades para propagar e infectar otros dispositivos <br/><br/> *[La protección contra](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exploit-protection) vulnerabilidades de seguridad también se conoce como Protección contra vulnerabilidades de seguridad.* |[Protección de puntos de conexión: Protección contra vulnerabilidades de seguridad de Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Habilitar la protección contra vulnerabilidades en Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Configurar SmartScreen de Microsoft Defender para** proteger contra sitios y archivos malintencionados en Internet. <br/><br/> *Microsoft Edge debe instalarse en los dispositivos de la organización. Para obtener protección en los exploradores Google Chrome y FireFox, configure la protección contra vulnerabilidades de seguridad.*  |[Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Restricciones de dispositivos: SmartScreen de Microsoft Defender](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Configuración de directiva para administrar SmartScreen en Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Configurar Firewall de Microsoft Defender para** bloquear el tráfico de red no autorizado que entra o sale de los dispositivos de la organización  |[Protección de puntos de conexión: Firewall de Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Firewall de Microsoft Defender con seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Configurar el cifrado y BitLocker para** proteger la información en los dispositivos de la organización que ejecutan Windows |[Protección de extremo: cifrado de Windows](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker para dispositivos Windows 10](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Configurar Credential Guard de Microsoft Defender** para protegerse contra ataques de robo de credenciales |Para Windows 10, Windows Server 2016 y Windows Server 2019, consulta [Endpoint protection: Credential Guard de Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>Para Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 y Windows Server 2012 R2, consulta [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft, Versions 1 and 2](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**Configurar el control de aplicaciones de Microsoft Defender** para elegir si auditar o confiar en aplicaciones en los dispositivos de la organización <br/><br/>*El control de aplicaciones de Microsoft Defender también se conoce como [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview).*|[Implementar directivas de control de aplicaciones de Microsoft Defender mediante Microsoft Intune](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Protección de extremo: Control de aplicaciones de Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|
|**Configurar el control de dispositivos y** el acceso a periféricos USB para ayudar a evitar que las amenazas en periféricos no autorizados puedan poner en peligro los dispositivos |[Controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para Endpoint e Intune](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurar el Centro de seguridad de Microsoft Defender

Si aún no lo ha hecho, configure el Centro de seguridad de **Microsoft Defender** ( ) para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su [https://securitycenter.windows.com](https://securitycenter.windows.com) organización. 

También puede configurar si los usuarios finales pueden ver y qué características pueden ver en el Centro de seguridad de Microsoft Defender.

- [Información general del Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Protección de puntos de conexión: Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Siguientes pasos

- [Obtener información general sobre la administración de amenazas y vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite el panel de operaciones de seguridad del Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)
