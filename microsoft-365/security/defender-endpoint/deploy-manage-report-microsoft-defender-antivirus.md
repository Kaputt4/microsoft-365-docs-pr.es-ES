---
title: Implementar, administrar e informar sobre antivirus de Microsoft Defender
description: Puede implementar y administrar Antivirus de Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, PowerShell o WMI
keywords: implementar, administrar, actualizar, proteger, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a9cd04300e67f956b50f07c02f3dc00c515f02eb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691512"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Implementar, administrar e informar sobre antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puedes implementar, administrar e informar sobre antivirus de Microsoft Defender de varias maneras.

Dado que el cliente antivirus de Microsoft Defender está instalado como parte principal de Windows 10, no se aplica la implementación tradicional de un cliente en los puntos de conexión.

Sin embargo, en la mayoría de los casos, tendrá que habilitar el servicio de protección en los puntos de conexión con Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender o objetos de directiva de grupo, que se describe en la tabla siguiente.

También verá vínculos adicionales para:

- Administración de la protección antivirus de Microsoft Defender, incluida la administración de actualizaciones de productos y protección
- Informes sobre la protección antivirus de Microsoft Defender

> [!IMPORTANT]
> En la mayoría de los casos, Windows 10 deshabilitará Antivirus de Microsoft Defender si encuentra otro producto antivirus que esté en ejecución y actualizado. Debe deshabilitar o desinstalar productos antivirus de terceros antes de que antivirus de Microsoft Defender funcione. Si vuelves a habilitar o instalar productos antivirus de terceros, Windows 10 deshabilita automáticamente Antivirus de Microsoft Defender.

Herramienta|Opciones de implementación (<a href="#fn2" id="ref2">2</a>)|Opciones de administración (configuración de toda la red y directiva o implementación de línea base) ([3](#fn3))|Opciones de informes  
---|---|---|---  
Microsoft Intune|[Agregar configuración de protección de puntos de conexión en Intune](/intune/endpoint-protection-configure)|[Configurar la configuración de restricción de dispositivos en Intune](/intune/device-restrictions-configure)| [Usar la consola de Intune para administrar dispositivos](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Usar el rol del sistema [de sitio de punto][] de Endpoint Protection y habilitar Endpoint Protection con la configuración de cliente [personalizada][]|Con [directivas de antimalware predeterminadas y personalizadas][] y [administración de clientes][]|Con el área de [trabajo de supervisión predeterminada de Configuration Manager y][] las [alertas de correo electrónico][]  
Directiva de grupo y Active Directory (unido a dominio)|Use un objeto de directiva de grupo para implementar cambios de configuración y asegurarse de que Antivirus de Microsoft Defender está habilitado.|Usar objetos de directiva de grupo (GPO) para configurar las opciones de actualización para Antivirus de [Microsoft Defender][] y configurar Windows Defender [características][]|Los informes de extremo no están disponibles con la directiva de grupo. Puede generar una lista de directivas [de grupo para determinar si no][] se aplica ninguna configuración o directiva
PowerShell|Implemente con directiva de grupo, Microsoft Endpoint Configuration Manager o manualmente en puntos de conexión individuales.|Use los [cmdlets Set-MpPreference] y [Update-MpSignature] disponibles en el módulo Defender.|Usar los [cmdlets Get- adecuados disponibles en el módulo Defender][]
Instrumental de administración de Windows|Implemente con directiva de grupo, Microsoft Endpoint Configuration Manager o manualmente en puntos de conexión individuales.|Use el [método Set de la clase MSFT_MpPreference y][] el método Update de la MSFT_MpSignature [clase][]|Use la [MSFT_MpComputerStatus][] y el método get de las clases asociadas en el [Windows Defender WMIv2 Provider][]
Microsoft Azure|Implemente Microsoft Antimalware para Azure en Azure Portal, mediante Visual Studio configuración de máquina [virtual o mediante cmdlets de PowerShell de Azure](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios). También puede instalar [la protección de extremo en Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|Configurar [Microsoft Antimalware para máquinas virtuales y servicios en la nube con cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) o [usar ejemplos de código](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Use [Microsoft Antimalware para máquinas virtuales y servicios en la nube con cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) para habilitar la supervisión. También puede revisar los informes de uso en Azure [][] Active Directory para determinar la actividad sospechosa, incluido el informe posiblemente infectados de dispositivos y configurar una herramienta SIEM para informar sobre los eventos del Antivirus de [Microsoft Defender][] y agregar esa herramienta como una aplicación en AAD.

1. <span id="fn1" />La disponibilidad de algunas funciones y características, especialmente relacionadas con la protección entregada en la nube, difiere entre Microsoft Endpoint Manager (rama actual) y System Center 2012 Configuration Manager. En esta biblioteca, nos hemos centrado en Windows 10, Windows Server 2016 y Microsoft Endpoint Manager (rama actual). Consulta [Usar la protección proporcionada por la nube](cloud-protection-microsoft-defender-antivirus.md) de Microsoft en Antivirus de Microsoft Defender para obtener una tabla que describe las principales diferencias. [(Volver a la tabla)](#ref2)
  
2.  <span id="fn2" />En Windows 10, Antivirus de Microsoft Defender es un componente disponible sin instalación o implementación de un cliente o servicio adicional. Se habilitará automáticamente cuando los productos antivirus de terceros se desinstalen o no estén actualizados ( excepto[en Windows Server 2016](microsoft-defender-antivirus-on-windows-server.md)). Por lo tanto, la implementación tradicional no es necesaria. La implementación aquí se refiere a garantizar que el componente antivirus de Microsoft Defender esté disponible y habilitado en los puntos de conexión o servidores. [(Volver a la tabla)](#ref2)

3. <span id="fn3" />La configuración de características y protección, incluida la configuración de actualizaciones de productos y protección, se describe más adelante en la sección Configurar características de Antivirus de [Microsoft Defender](configure-notifications-microsoft-defender-antivirus.md) en esta biblioteca. [(Volver a la tabla)](#ref2)

[Rol del sistema de sitio de punto de Endpoint Protection]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[directivas antimalware predeterminadas y personalizadas]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[administración de clientes]:  /configmgr/core/clients/manage/manage-clients
[habilitar Endpoint Protection con la configuración de cliente personalizada]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Área de trabajo de supervisión de Configuration Manager]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[alertas de correo electrónico]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Set (método) de la MSFT_MpPreference clase]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Update (método) de la MSFT_MpSignature clase]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2 Provider]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Get- cmdlets disponibles en el módulo Defender]: /powershell/module/defender/
[Configurar opciones de actualización para Antivirus de Microsoft Defender]: manage-updates-baselines-microsoft-defender-antivirus.md
[Configurar Windows Defender características]: configure-microsoft-defender-antivirus-features.md
[Directivas de grupo para determinar si no se aplica ninguna configuración o directiva]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Posiblemente dispositivos infectados]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Eventos de Antivirus de Microsoft Defender]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
---|---
[Implementar y habilitar la protección antivirus de Microsoft Defender](deploy-microsoft-defender-antivirus.md) | Aunque el cliente está instalado como parte principal de Windows 10 y la implementación tradicional no se aplica, deberá habilitar el cliente en los puntos de conexión con Microsoft Endpoint Configuration Manager, Microsoft Intune o objetos de directiva de grupo. 
[Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md) | Hay dos partes para actualizar Antivirus de Microsoft Defender: actualizar el cliente en puntos de conexión (actualizaciones del producto) y actualizar la inteligencia de seguridad (actualizaciones de protección). Puede actualizar la inteligencia de seguridad de varias maneras, con Microsoft Endpoint Configuration Manager, la directiva de grupo, PowerShell y WMI.
[Supervisar e informar sobre la protección antivirus de Microsoft Defender](report-monitor-microsoft-defender-antivirus.md) | Puede usar Microsoft Intune, Microsoft Endpoint Configuration Manager, el complemento Update Compliance para Microsoft Operations Management Suite o un producto SIEM de terceros (mediante el consumo de registros de eventos de Windows) para supervisar el estado de la protección y crear informes sobre la protección de puntos de conexión.