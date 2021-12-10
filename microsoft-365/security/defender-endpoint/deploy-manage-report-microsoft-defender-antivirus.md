---
title: Implementar, administrar e informar sobre Antivirus de Microsoft Defender
description: Puede implementar y administrar Antivirus de Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, PowerShell o WMI
keywords: implementar, administrar, actualizar, proteger, Antivirus de Microsoft Defender
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
ms.openlocfilehash: 1ce212bf01b8c464760192a4bbd6355498d19c3c
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164135"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Implementar, administrar e informar sobre Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Puede implementar, administrar e informar sobre Antivirus de Microsoft Defender de varias maneras.

Dado que Antivirus de Microsoft Defender cliente de Antivirus de Microsoft Defender se instala como una parte principal de Windows 10 y Windows 11, no se aplica la implementación tradicional de un cliente en los puntos de conexión.

Sin embargo, en la mayoría de los casos, deberá habilitar el servicio de protección en los puntos de conexión con Microsoft Intune, Microsoft Endpoint Configuration Manager, Microsoft Defender para la nube o objetos de directiva de grupo, que se describe en la tabla siguiente.

También verá vínculos adicionales para:

- Administración Antivirus de Microsoft Defender protección, incluida la administración de actualizaciones de productos y protección
- Informes sobre la Antivirus de Microsoft Defender protección

> [!IMPORTANT]
> En la mayoría de los casos, Windows 10 o Windows 11 deshabilitarán Antivirus de Microsoft Defender si encuentra otro producto antivirus en ejecución y actualizado. Debe deshabilitar o desinstalar productos antivirus de terceros antes de que Antivirus de Microsoft Defender funcione. Si vuelve a habilitar o instalar productos antivirus de terceros, Windows 10 o Windows 11 deshabilita automáticamente Antivirus de Microsoft Defender.

Herramienta|Opciones de implementación (<a href="#fn2" id="ref2">2</a>)|Opciones de administración (configuración de toda la red y directiva o implementación de línea base) ([3](#fn3))|Opciones de informes
---|---|---|---
Microsoft Intune|[Agregar configuración de protección de puntos de conexión en Intune](/intune/endpoint-protection-configure)|[Configurar la configuración de restricción de dispositivos en Intune](/intune/device-restrictions-configure)| [Usar la consola de Intune para administrar dispositivos](/intune/device-management)
Microsoft Endpoint Manager ([1](#fn1))|Use el [Endpoint Protection de sistema de sitio de puntos][] y [habilitar Endpoint Protection con la configuración de cliente personalizada][]|Con [directivas antimalware predeterminadas y personalizadas][] y [administración de cliente][]|Con el valor predeterminado [área de trabajo supervisión de Configuration Manager][] y [alertas de correo electrónico][]
Directiva de grupo y Active Directory (unido a dominio)|Use un objeto de directiva de grupo para implementar los cambios de configuración y asegurarse de Antivirus de Microsoft Defender está habilitado.|Usar objetos de directiva de grupo (GPO) para [Configurar opciones de actualización para Antivirus de Microsoft Defender][] y [Configurar Windows Defender características][]|Los informes de extremo no están disponibles con la directiva de grupo. Puede generar una lista de [Directivas de grupo para determinar si no se aplica ninguna configuración o directiva][]
PowerShell|Implemente con directiva de grupo, Microsoft Endpoint Configuration Manager o manualmente en puntos de conexión individuales.|Use los cmdlets [Set-MpPreference] y [Update-MpSignature] disponibles en el módulo Defender.|Usar los cmdlets [Get- adecuados disponibles en el módulo Defender][]
Windows instrumental de administración|Implemente con directiva de grupo, Microsoft Endpoint Configuration Manager o manualmente en puntos de conexión individuales.|Utilice el método [Set de la MSFT_MpPreference clase][] y el método [Update de la MSFT_MpSignature clase][]|Use la clase [MSFT_MpComputerStatus][] y el método get de las clases asociadas en el [Windows Defender WMIv2 Provider][]
Microsoft Azure|Implemente Microsoft Antimalware para Azure en Azure Portal, mediante Visual Studio configuración de máquina [virtual o mediante cmdlets Azure PowerShell](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios). También puede instalar [la protección de extremo en Microsoft Defender para la nube*](/azure/security-center/security-center-install-endpoint-protection)|Configurar Microsoft Antimalware para máquinas virtuales y servicios en la nube [con cmdlets](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) Azure PowerShell o [usar ejemplos de código](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Use Microsoft Antimalware para máquinas virtuales y servicios en la nube [con cmdlets Azure PowerShell para](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) habilitar la supervisión. También puedes revisar los informes de uso en Azure Active Directory para determinar la actividad sospechosa, incluido el informe [Posiblemente dispositivos infectados][] y configurar una herramienta SIEM para informar sobre [eventos de Antivirus de Microsoft Defender][] y agregar esa herramienta como una aplicación en AAD.

1. <span id="fn1" />La disponibilidad de algunas funciones y características, especialmente relacionadas con la protección entregada en la nube, difiere entre Microsoft Endpoint Manager (rama actual) y System Center Configuration Manager de 2012. En esta biblioteca, nos hemos centrado en Windows 10, Windows 11, Windows Server 2016 y Microsoft Endpoint Manager (rama actual). Consulte [Use Microsoft cloud-provided protection in Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) para obtener una tabla que describe las principales diferencias. [(Volver a la tabla)](#ref2)

2. <span id="fn2" />En Windows 10 y Windows 11, Antivirus de Microsoft Defender es un componente disponible sin la instalación o implementación de un cliente o servicio adicional. Se habilitará automáticamente cuando los productos antivirus de terceros se desinstale o no estén actualizados (excepto en Windows Server 2016). Por lo tanto, la implementación tradicional no es necesaria. La implementación aquí se refiere a garantizar que el Antivirus de Microsoft Defender está disponible y habilitado en los puntos de conexión o servidores. [(Volver a la tabla)](#ref2)

3. <span id="fn3" />La configuración de características y protección, incluida la configuración de actualizaciones de productos y protección, se describe más adelante en la sección [Configurar Antivirus de Microsoft Defender características de](configure-notifications-microsoft-defender-antivirus.md) esta biblioteca. [(Volver a la tabla)](#ref2)

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
---|---
[Implementar y habilitar la Antivirus de Microsoft Defender protección](deploy-microsoft-defender-antivirus.md) | Aunque el cliente está instalado como una parte principal de Windows 10 o Windows 11, y la implementación tradicional no se aplica, tendrá que habilitar el cliente en los puntos de conexión con Microsoft Endpoint Configuration Manager, Microsoft Intune o objetos de directiva de grupo.
[Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md) | Hay dos partes para actualizar Antivirus de Microsoft Defender: actualizar el cliente en puntos de conexión (actualizaciones de productos) y actualizar la inteligencia de seguridad (actualizaciones de protección). Puede actualizar la inteligencia de seguridad de varias maneras, mediante Microsoft Endpoint Configuration Manager, directiva de grupo, PowerShell y WMI.
[Supervisar e informar sobre la Antivirus de Microsoft Defender protección](report-monitor-microsoft-defender-antivirus.md) | Puede usar Microsoft Intune, Microsoft Endpoint Configuration Manager, el complemento Update Compliance para Microsoft Operations Management Suite o un producto SIEM de terceros (al consumir registros de eventos Windows) para supervisar el estado de la protección y crear informes sobre la protección de puntos de conexión.
