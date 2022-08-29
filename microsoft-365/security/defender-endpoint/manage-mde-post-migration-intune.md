---
title: Administración de Microsoft Defender para punto de conexión mediante Intune
description: Aprenda a administrar Microsoft Defender para punto de conexión con Intune
keywords: posterior a la migración, administración, operaciones, mantenimiento, uso, intune, Microsoft Defender para punto de conexión, edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.date: 07/01/2022
ms.reviewer: chventou
ms.openlocfilehash: c8a7b949118375fa10ac12a18ce82c4fadebd6f3
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327165"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Administración de Microsoft Defender para punto de conexión con Intune

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Se recomienda usar [Microsoft Endpoint Manager](/mem), que incluye Microsoft Intune (Intune) para administrar las características de protección contra amenazas de su organización para dispositivos (también conocidos como puntos de conexión). [Más información sobre Endpoint Manager](/mem/endpoint-manager-overview).

En este artículo se describe cómo buscar la configuración de Microsoft Defender para punto de conexión en Intune y se enumeran varias tareas que puede realizar.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Busque la configuración de Microsoft Defender para punto de conexión en Intune

> [!IMPORTANT]
> Debe tener asignado el rol de administrador global o administrador de servicios en Intune para configurar los valores descritos en este artículo. Para obtener más información, consulte **[Tipos de administradores (Intune)](/mem/intune/fundamentals/users-add#types-of-administrators)**.

1. Vaya a la Azure Portal ([https://portal.azure.com](https://portal.azure.com)) e inicie sesión.

2. En **Servicios de Azure**, elija **Intune**.

3. En el panel de navegación de la izquierda, elija **Configuración del dispositivo** y, a continuación, en **Administrar**, elija **Perfiles**.

4. Seleccione un perfil existente o cree uno nuevo.

> [!TIP]
> ¿Necesita ayuda? Consulte **[Uso de Microsoft Defender para punto de conexión con Intune](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**.

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Configuración de Microsoft Defender para punto de conexión con Intune

En la tabla siguiente se enumeran varias tareas que puede realizar para configurar Microsoft Defender para punto de conexión con Intune. No es necesario configurar todo a la vez; elija una tarea, lea los recursos correspondientes y, a continuación, continúe.

|Tarea|Recursos para obtener más información|
|---|---|
|**Administrar los dispositivos de la organización mediante Intune** para proteger esos dispositivos y datos almacenados en ellos|[Proteger los dispositivos con Microsoft Intune](/mem/intune/protect/device-protect)|
|**Integración de Microsoft Defender para punto de conexión con Intune** como solución de Mobile Threat Defense <br/>*(para dispositivos Android y dispositivos que ejecutan Windows 10 o Windows 11)*|[Exigir el cumplimiento mediante Microsoft Defender para punto de conexión con acceso condicional en Intune](/mem/intune/protect/advanced-threat-protection)|
|**Uso del acceso condicional** para controlar los dispositivos y aplicaciones que se pueden conectar a los recursos de correo electrónico y de la empresa|[Configuración del acceso condicional en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-conditional-access)|
|**Configuración de la configuración del Antivirus de Microsoft Defender** mediante el proveedor de servicios de configuración de directivas ([CSP de directivas](/windows/client-management/mdm/policy-configuration-service-provider))|[Restricciones de dispositivos: Antivirus de Microsoft Defender](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) <br/><br/> [CSP de directiva: Microsoft Defender para punto de conexión](/windows/client-management/mdm/policy-csp-defender)|
|**Si es necesario, especifique exclusiones para el Antivirus de Microsoft Defender.** <br/><br/> *Por lo general, no es necesario aplicar exclusiones. Antivirus de Microsoft Defender incluye una serie de exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos, como los que se usan en la administración empresarial, la administración de bases de datos y otros escenarios empresariales.*|[Recomendaciones de detección de virus para equipos enterprise que ejecutan versiones compatibles actualmente de Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers) <br/><br/> [Restricciones de dispositivos: Exclusiones del Antivirus de Microsoft Defender para dispositivos Windows 10 y Windows 11](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/> [Configuración de exclusiones del Antivirus de Microsoft Defender en Windows Server 2016 o 2019 o 2022](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Configurar las reglas de reducción de la superficie expuesta a ataques** para dirigirse a comportamientos de software que suelen ser objeto de abuso por parte de los atacantes <br/><br/> *Configure las reglas de reducción de la superficie expuesta a ataques en [el modo de auditoría](/microsoft-365/security/defender-endpoint/audit-windows-defender) al principio (durante al menos una semana y hasta dos meses). Puede supervisar el estado mediante Power BI ([obtenga nuestra plantilla](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)) y, a continuación, establecer esas reglas en modo activo cuando esté listo.*|[Modo de auditoría en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/audit-windows-defender) <br/><br/> [Endpoint Protection: Reducción de la superficie expuesta a ataques](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction) <br/><br/> [Más información sobre las reglas de reducción de superficie expuesta a ataques](/microsoft-365/security/defender-endpoint/attack-surface-reduction) <br/><br/> [Entrada de blog de tech community: Desmitificación de las reglas de reducción de superficie expuesta a ataques - Parte 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)|
|**Configuración del filtrado de red** para bloquear las conexiones salientes desde cualquier aplicación a direcciones IP o dominios con baja reputación  <br/><br/> *El filtrado de red también se conoce como [protección de red](/microsoft-365/security/defender-endpoint/network-protection).* <br/><br/> *Asegúrese de que los dispositivos Windows 10 y Windows 11 tengan instaladas las [últimas actualizaciones de la plataforma antimalware](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).*|[Endpoint Protection: Filtrado de red](/mem/intune/protect/endpoint-protection-windows-10#network-filtering) <br/><br/> [Revise los eventos de protección de red en Windows Visor de eventos](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer)|
|**Configuración del acceso controlado a carpetas** para protegerse frente a ransomware <br/><br/> *[El acceso controlado a carpetas](/microsoft-365/security/defender-endpoint/controlled-folders) también se conoce como protección contra antiransomware.*|[Endpoint Protection: acceso controlado a carpetas](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [Habilitar el acceso controlado a carpetas en Intune](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)|
|**Configurar la protección contra vulnerabilidades de seguridad** para proteger los dispositivos de la organización frente a malware que usa vulnerabilidades de seguridad para propagar e infectar otros dispositivos <br/><br/> *[Protección contra vulnerabilidades de seguridad](/microsoft-365/security/defender-endpoint/exploit-protection) también se conoce como Protección contra vulnerabilidades de seguridad.*|[Endpoint Protection: Protección contra vulnerabilidades de seguridad de Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/> [Habilitación de la protección contra vulnerabilidades de seguridad en Intune](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune)|
|**Configure SmartScreen de Microsoft Defender** para protegerse frente a sitios y archivos malintencionados en Internet. <br/><br/> *Microsoft Edge debe instalarse en los dispositivos de la organización. Para la protección en los exploradores Google Chrome y FireFox, configure la protección contra vulnerabilidades de seguridad.*|[SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/> [Restricciones de dispositivos: SmartScreen de Microsoft Defender](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen) <br/><br/> [Configuración de directiva para administrar SmartScreen en Intune](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)|
|**Configuración del firewall de Microsoft Defender** para bloquear el tráfico de red no autorizado que entra o sale de los dispositivos de la organización|[Endpoint protection: Microsoft Defender Firewall](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Firewall de Microsoft Defender con seguridad avanzada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)|
|**Configuración del cifrado y BitLocker** para proteger la información sobre los dispositivos de la organización que ejecutan Windows|[Endpoint Protection: Cifrado de Windows](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption) <br/><br/> [BitLocker para dispositivos Windows 10 y Windows 11](/windows/security/information-protection/bitlocker/bitlocker-overview)|
|**Configuración de Credential Guard de Microsoft Defender** para protegerse frente a ataques de robo de credenciales|Para obtener Windows 10, Windows 11, Windows Server 2016 y Windows Server 2019 y Windows Server 2022, consulte [Endpoint Protection: Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/> Para Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 y Windows Server 2012 R2, vea [Mitigación de ataques de paso a hash (PtH) y otros robos de credenciales, versiones 1 y 2](https://www.microsoft.com/download/details.aspx?id=36036).|
|**Configuración del control de aplicaciones de Microsoft Defender** para elegir si auditar o confiar en aplicaciones en los dispositivos de la organización <br/><br/> *El control de aplicaciones de Microsoft Defender también se conoce como [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview).*|[Implementación de directivas de Control de aplicaciones de Microsoft Defender mediante Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune) <br/><br/> [Endpoint Protection: Control de aplicaciones de Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control) <br/><br/> [CSP de AppLocker](/windows/client-management/mdm/applocker-csp)|
|**Configurar el control de dispositivos y el acceso a periféricos USB** para ayudar a evitar que las amenazas en periféricos no autorizados pongan en peligro los dispositivos|[Controlar dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión y Intune](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Configuración del portal de Microsoft 365 Defender

Si aún no lo ha hecho, configure el portal de Microsoft 365 Defender para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de la organización. Consulte [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). También puede configurar si y qué características pueden ver los usuarios finales en el portal de Microsoft 365 Defender.

- [Introducción a Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [Endpoint Protection: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Siguientes pasos

- [Obtenga información general sobre la administración de vulnerabilidades de Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Visite el panel de operaciones de seguridad del portal de Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
