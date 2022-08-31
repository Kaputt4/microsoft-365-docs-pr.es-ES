---
title: Implementación, administración e informe sobre el Antivirus de Microsoft Defender
description: Puede implementar y administrar antivirus de Microsoft Defender con Intune, Configuration Manager de punto de conexión de Microsoft, directiva de grupo, PowerShell o WMI
keywords: implementar, administrar, actualizar, proteger, Antivirus de Microsoft Defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 08/05/2022
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- M365-security-compliance
ms.openlocfilehash: f1c013c5104ab49f8ae5a7053b2a4b0d273c5867
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67468953"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Implementación, administración e informe sobre el Antivirus de Microsoft Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender 

**Plataformas**

- Windows

Puede implementar, administrar e informar sobre el Antivirus de Microsoft Defender de varias maneras.

Dado que el cliente antivirus de Microsoft Defender está instalado como parte principal de Windows 10 y Windows 11, no se aplica la implementación tradicional de un cliente en los puntos de conexión.

Sin embargo, en la mayoría de los casos seguirá teniendo que habilitar el servicio de protección en los puntos de conexión con Microsoft Intune, Microsoft Endpoint Configuration Manager, Microsoft Defender for Cloud o directiva de grupo Objects, que se describe en la tabla siguiente.

También verá vínculos adicionales para:

- Administración de la protección antivirus de Microsoft Defender, incluida la administración de actualizaciones de productos y protección
- Generación de informes sobre la protección antivirus de Microsoft Defender

> [!IMPORTANT]
> En la mayoría de los casos, Windows 10 o Windows 11 deshabilitarán el Antivirus de Microsoft Defender si encuentra otro producto antivirus que esté en ejecución y actualizado. Debe deshabilitar o desinstalar productos antivirus de terceros antes de que el Antivirus de Microsoft Defender funcione. Si vuelve a habilitar o instalar productos antivirus de terceros, Windows 10 o Windows 11 deshabilita automáticamente el Antivirus de Microsoft Defender.

Herramienta|Opciones de implementación (<a href="#fn2" id="ref2">2</a>)|Opciones de administración (configuración de toda la red y implementación de directivas o líneas base) ([3](#fn3))|Opciones de informes
---|---|---|---
Microsoft Intune|[Adición de la configuración de Endpoint Protection en Intune](/intune/endpoint-protection-configure)|[Configuración de la restricción de dispositivos en Intune](/intune/device-restrictions-configure)| [Uso de la consola de Intune para administrar dispositivos](/intune/device-management)
Microsoft Endpoint Manager ([1](#fn1))|Use el [rol de sistema de sitio de punto de Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-site-role) y [habilite Endpoint Protection con la configuración de cliente personalizada](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client).|Con [directivas antimalware predeterminadas y personalizadas](/microsoft-365/security/office-365-security/configure-anti-malware-policies) y administración de clientes.|Con las alertas de correo electrónico y [el área de trabajo de supervisión de Configuration Manager](/mem/configmgr/apps/deploy-use/monitor-applications-from-the-console) predeterminadas.
directiva de grupo y Active Directory (unidos a un dominio)|Use un objeto directiva de grupo para implementar los cambios de configuración y asegurarse de que antivirus de Microsoft Defender está habilitado.|Use objetos de directiva de grupo (GPO) para [configurar las opciones de actualización del Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/manage-protection-update-schedule-microsoft-defender-antivirus) y [configurar las características de Windows Defender](/microsoft-365/security/defender-endpoint/configure-microsoft-defender-antivirus-features).|Los informes de punto de conexión no están disponibles con directiva de grupo. Puede generar una lista de directivas de grupo para determinar si no se aplica ninguna configuración o directiva.
PowerShell|Implemente con directiva de grupo, punto de conexión de Microsoft Configuration Manager o manualmente en puntos de conexión individuales.|Use los cmdlets [Set-MpPreference] y [Update-MpSignature] disponibles en el módulo de Defender.|Use los [cmdlets Get- adecuados disponibles en el módulo de Defender](/powershell/module/defender).
Instrumental de administración de Windows|Implemente con directiva de grupo, punto de conexión de Microsoft Configuration Manager o manualmente en puntos de conexión individuales.|Use el [método Set de la clase MSFT_MpPreference](/previous-versions/windows/desktop/defender/set-msft-mppreference) y el [método Update de la clase MSFT_MpSignature](/previous-versions/windows/desktop/defender/update-msft-mpsignature).|Use la clase [MSFT_MpComputerStatus](/previous-versions/windows/desktop/defender/msft-mpcomputerstatus) y el método get de las clases asociadas en el [proveedor Windows Defender WMIv2](/windows/win32/wmisdk/wmi-providers).
Microsoft Azure|Implemente Microsoft Antimalware para Azure en el [Azure Portal, mediante la configuración de máquinas virtuales de Visual Studio o mediante cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios). También puede [instalar Endpoint Protection en Microsoft Defender for Cloud](/azure/defender-for-cloud/endpoint-protection-recommendations-technical).|Configure [Microsoft Antimalware para Virtual Machines y Cloud Services con cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) o [use ejemplos de código](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe).|Use [Microsoft Antimalware para Virtual Machines y Cloud Services con cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) para habilitar la supervisión. También puede revisar los informes de uso en Azure Active Directory para determinar la actividad sospechosa, incluido el informe de dispositivos posiblemente infectados, y configurar una herramienta SIEM para informar sobre [eventos del Antivirus de Microsoft Defender][/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus] y agregar esa herramienta como una aplicación en AAD.

1. <span id="fn1" />La disponibilidad de algunas funciones y características, especialmente relacionadas con la protección proporcionada en la nube, difiere entre Microsoft Endpoint Manager (rama actual) y System Center 2012 Configuration Manager. En esta biblioteca, nos hemos centrado en Windows 10, Windows 11, Windows Server 2016 y Microsoft Endpoint Manager (rama actual). Consulte [Uso de la protección proporcionada por la nube de Microsoft en el Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) para obtener una tabla que describa las principales diferencias. [(Volver a la tabla)](#ref2)

2. <span id="fn2" />En Windows 10 y Windows 11, Antivirus de Microsoft Defender es un componente disponible sin instalación ni implementación de un cliente o servicio adicional. Se habilitará automáticamente cuando los productos antivirus de terceros se desinstalen o no estén actualizados (excepto en Windows Server 2016). Por lo tanto, no es necesaria la implementación tradicional. La implementación aquí se refiere a garantizar que el componente Antivirus de Microsoft Defender está disponible y habilitado en los puntos de conexión o servidores. [(Volver a la tabla)](#ref2)

3. <span id="fn3" />La configuración de características y protección, incluida la configuración de actualizaciones de productos y protección, se describe más adelante en la sección [Configurar características del Antivirus de Microsoft Defender](configure-notifications-microsoft-defender-antivirus.md) de esta biblioteca. [(Volver a la tabla)](#ref2)

## <a name="in-this-section"></a>En esta sección

Artículo | Descripción
---|---
[Implementación y habilitación de la protección antivirus de Microsoft Defender](deploy-microsoft-defender-antivirus.md) | Aunque el cliente está instalado como parte principal de Windows 10 o Windows 11, y la implementación tradicional no se aplica, deberá habilitar el cliente en los puntos de conexión con Microsoft Endpoint Configuration Manager, Microsoft Intune o directiva de grupo Objetos.
[Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.](manage-updates-baselines-microsoft-defender-antivirus.md) | Hay dos partes para actualizar el Antivirus de Microsoft Defender: actualizar el cliente en puntos de conexión (actualizaciones de productos) y actualizar inteligencia de seguridad (actualizaciones de protección). Puede actualizar la inteligencia de seguridad de varias maneras mediante microsoft endpoint Configuration Manager, directiva de grupo, PowerShell y WMI.
[Supervisión e informe sobre la protección antivirus de Microsoft Defender](report-monitor-microsoft-defender-antivirus.md) | Puede usar Microsoft Intune, microsoft endpoint Configuration Manager, el complemento Update Compliance para Microsoft Operations Management Suite o un producto SIEM de terceros (mediante el consumo de registros de eventos de Windows) para supervisar el estado de la protección y crear informes sobre endpoint protection.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
    
