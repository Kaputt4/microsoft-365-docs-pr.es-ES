---
title: Implementar, administrar e informar sobre Antivirus de Microsoft Defender
description: Puede implementar y administrar Antivirus de Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, PowerShell o WMI
keywords: implementar, administrar, actualizar, proteger Antivirus de Microsoft Defender
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 049c7a772c4c8dcf986efd310e4613423f33dcc9
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419140"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Implementar, administrar e informar sobre Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender 

**Plataformas**
- Windows

Puede implementar, administrar e informar sobre Antivirus de Microsoft Defender de varias maneras.

Dado que el cliente de Antivirus de Microsoft Defender se instala como parte principal de Windows 10 y Windows 11, no se aplica la implementación tradicional de un cliente en los puntos de conexión.

Sin embargo, en la mayoría de los casos seguirá teniendo que habilitar el servicio de protección en los puntos de conexión con Microsoft Intune, Microsoft Endpoint Configuration Manager, Microsoft Defender for Cloud o directiva de grupo  Objetos, que se describe en la tabla siguiente.

También verá vínculos adicionales para:

- Administración de Antivirus de Microsoft Defender protección, incluida la administración de actualizaciones de productos y protección
- Generación de informes sobre la protección de Antivirus de Microsoft Defender

> [!IMPORTANT]
> En la mayoría de los casos, Windows 10 o Windows 11 deshabilitarán Antivirus de Microsoft Defender si encuentra otro producto antivirus que esté en ejecución y actualizado. Debe deshabilitar o desinstalar productos antivirus de terceros antes de que funcione Antivirus de Microsoft Defender. Si vuelve a habilitar o instalar productos antivirus de terceros, Windows 10 o Windows 11 deshabilita automáticamente Antivirus de Microsoft Defender.

Herramienta|Opciones de implementación (<a href="#fn2" id="ref2">2</a>)|Opciones de administración (configuración de toda la red y implementación de directivas o líneas base) ([3](#fn3))|Opciones de informes
---|---|---|---
Microsoft Intune|[Adición de la configuración de Endpoint Protection en Intune](/intune/endpoint-protection-configure)|[Configuración de la restricción de dispositivos en Intune](/intune/device-restrictions-configure)| [Uso de la consola de Intune para administrar dispositivos](/intune/device-management)
Microsoft Endpoint Manager ([1](#fn1))|Use el [rol de sistema de sitio de punto Endpoint Protection][] y [habilitar Endpoint Protection con la configuración de cliente personalizada][]|Con [directivas antimalware predeterminadas y personalizadas][] y [administración de cliente][]|Con el valor predeterminado [Configuration Manager área de trabajo supervisión][] y [alertas de correo electrónico][]
directiva de grupo y Active Directory (unidos a un dominio)|Use un objeto directiva de grupo para implementar los cambios de configuración y asegurarse de que Antivirus de Microsoft Defender está habilitado.|Use objetos directiva de grupo (GPO) para [Configurar opciones de actualización para Antivirus de Microsoft Defender][] y [Configurar características de Windows Defender][]|Los informes de punto de conexión no están disponibles con directiva de grupo. Puede generar una lista de [Directivas de grupo para determinar si no se aplica ninguna configuración o directiva][]
PowerShell|Implemente con directiva de grupo, Microsoft Endpoint Configuration Manager o manualmente en puntos de conexión individuales.|Use los cmdlets [Set-MpPreference] y [Update-MpSignature] disponibles en el módulo de Defender.|Use los cmdlets [Get- adecuados disponibles en el módulo de Defender][]
Instrumentación de administración de Windows|Implemente con directiva de grupo, Microsoft Endpoint Configuration Manager o manualmente en puntos de conexión individuales.|Use el [método Set de la clase MSFT_MpPreference][] y el [método Update de la clase MSFT_MpSignature][]|Use la clase [MSFT_MpComputerStatus][] y el método get de las clases asociadas en el [Windows Defender proveedor WMIv2][]
Microsoft Azure|Implemente Microsoft Antimalware para Azure en el [Azure Portal, mediante Visual Studio configuración de máquina virtual o mediante cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios). También puede [instalar Endpoint Protection en Microsoft Defender for Cloud*](/azure/security-center/security-center-install-endpoint-protection)|Configuración [de Microsoft Antimalware para Virtual Machines y Cloud Services con cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) o [uso de ejemplos de código](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Use [Microsoft Antimalware para Virtual Machines y Cloud Services con cmdlets de Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) para habilitar la supervisión. También puede revisar los informes de uso de Azure Active Directory para determinar la actividad sospechosa, incluido el informe [Posiblemente dispositivos infectados][], configurar una herramienta SIEM para informar sobre [eventos de Antivirus de Microsoft Defender][] y agregar esa herramienta como una aplicación en AAD.

1. <span id="fn1" />La disponibilidad de algunas funciones y características, especialmente relacionadas con la protección proporcionada en la nube, difiere entre Microsoft Endpoint Manager (rama actual) y System Center Configuration Manager de 2012. En esta biblioteca, nos hemos centrado en Windows 10, Windows 11, Windows Server 2016 y Microsoft Endpoint Manager (rama actual). Consulte [Uso de la protección proporcionada por la nube de Microsoft en Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) para obtener una tabla que describa las principales diferencias. [(Volver a la tabla)](#ref2)

2. <span id="fn2" />En Windows 10 y Windows 11, Antivirus de Microsoft Defender es un componente disponible sin instalación ni implementación de un cliente o servicio adicional. Se habilitará automáticamente cuando los productos antivirus de terceros se desinstalen o no estén actualizados (excepto en Windows Server 2016). Por lo tanto, no es necesaria la implementación tradicional. La implementación aquí se refiere a asegurarse de que el componente Antivirus de Microsoft Defender está disponible y habilitado en los puntos de conexión o servidores. [(Volver a la tabla)](#ref2)

3. <span id="fn3" />La configuración de características y protección, incluida la configuración de actualizaciones de productos y protección, se describe más adelante en la sección [Configurar características Antivirus de Microsoft Defender](configure-notifications-microsoft-defender-antivirus.md) de esta biblioteca. [(Volver a la tabla)](#ref2)

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
---|---
[Implementación y habilitación de la protección Antivirus de Microsoft Defender](deploy-microsoft-defender-antivirus.md) | Aunque el cliente está instalado como parte principal de Windows 10 o Windows 11, y la implementación tradicional no se aplica, deberá habilitar el cliente en los puntos de conexión con Microsoft Endpoint Configuration Manager, Microsoft Intune o directiva de grupo Objetos.
[Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.](manage-updates-baselines-microsoft-defender-antivirus.md) | Hay dos partes para actualizar Antivirus de Microsoft Defender: actualizar el cliente en puntos de conexión (actualizaciones de productos) y actualizar inteligencia de seguridad (actualizaciones de protección). Puede actualizar la inteligencia de seguridad de varias maneras mediante Microsoft Endpoint Configuration Manager, directiva de grupo, PowerShell y WMI.
[Supervisión e informe sobre la protección Antivirus de Microsoft Defender](report-monitor-microsoft-defender-antivirus.md) | Puede usar Microsoft Intune, Microsoft Endpoint Configuration Manager, el complemento Update Compliance para Microsoft Operations Management Suite o un producto SIEM de terceros (mediante el consumo de registros de eventos de Windows) para supervisar el estado de la protección y crear informes sobre endpoint protection.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
    
