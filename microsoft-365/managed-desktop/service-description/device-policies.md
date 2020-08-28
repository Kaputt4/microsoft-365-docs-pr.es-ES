---
title: Configuración de dispositivos
description: Obtenga información sobre las directivas predeterminadas que se aplican a los dispositivos de escritorio administrados por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 319b26261f623a7e19e5bb8fbcd0b5d8a50d10a8
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289714"
---
# <a name="device-configuration"></a>Configuración de dispositivos


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Cuando se está configurando un nuevo dispositivo de escritorio administrado por Microsoft, se asegura de que dispone de la configuración adecuada para el escritorio administrado de Microsoft. Esto incluye un conjunto de directivas predeterminadas que se establecen como parte del proceso de incorporación. Estas directivas se proporcionan con la administración de dispositivos móviles (MDM) siempre que sea posible. Para obtener más información, vea [Administración de dispositivos móviles](https://docs.microsoft.com/windows/client-management/mdm/). 

>[!NOTE]
>Para evitar conflictos, no modifique estas directivas.

Los dispositivos llegarán con una imagen de firma y, a continuación, se unirán al dominio de Active Directory de Azure cuando el primer usuario inicie sesión. El dispositivo instalará automáticamente las directivas y aplicaciones necesarias sin intervención del personal de ti.

## <a name="default-policies"></a>Directivas predeterminadas

En esta tabla se resaltan las directivas predeterminadas que se aplican a todos los dispositivos de escritorio administrados por Microsoft durante el aprovisionamiento de dispositivos. Se revertirán todos los cambios detectados no aprobados por el equipo de operaciones de escritorio administrado por Microsoft para objetos administrados por el escritorio administrado por Microsoft.

Policy | Descripción
--- | ---
Línea de base de seguridad | [Microsoft Security Baseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM está configurado para todos los dispositivos de escritorio administrados por Microsoft. Esta línea base es la configuración estándar del sector. Se publica, se prueba de forma pública y los expertos en seguridad de Microsoft lo han revisado para mantener seguras los dispositivos de escritorio y las aplicaciones administrados por Microsoft en el lugar de trabajo moderno. <br><br>Para mitigar las amenazas del panorama de la amenaza de seguridad en constante evolución, la línea base de seguridad de Microsoft se actualizará e implementará en los dispositivos de escritorio administrados por Microsoft con cada actualización de características de Windows 10.<br><br>Para obtener más información, vea [líneas de base de seguridad de Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines).
Plantilla de seguridad recomendada para escritorio administrado de Microsoft | Un conjunto de cambios recomendados en la línea de base de seguridad que optimizan la experiencia del usuario.  Estos cambios se documentan en [el apéndice de seguridad](#security-addendum). Las actualizaciones del anexo de Directiva se producen según sea necesario.  
Implementación de la actualización | Use Windows Update para empresas para realizar la implementación gradual de las actualizaciones de software. Los administradores de ti no pueden modificar la configuración de las directivas de grupo de implementación. Para obtener más información sobre la implementación basada en grupos, vea [cómo se administran las actualizaciones en el escritorio administrado por Microsoft](updates.md).
Conexiones de uso medido | De forma predeterminada, las actualizaciones en conexiones de uso medido (como las redes LTE) están desactivadas, aunque cada usuario puede activar de forma independiente esta característica en la **configuración > actualizaciones > opciones avanzadas**. Si desea permitir que todos los usuarios habiliten las actualizaciones a través de conexiones de uso medido, [envíe una solicitud de cambio](../working-with-managed-desktop/admin-support.md), que se activará en todos los dispositivos.
| Cumplimiento de dispositivos | Estas directivas se configuran para todos los dispositivos de escritorio administrados por Microsoft. Se notifica que un dispositivo no es compatible cuando se deriva de nuestra configuración de seguridad necesaria.

## <a name="diagnostic-data"></a>Datos de diagnóstico

 Los dispositivos se configurarán para proporcionar datos de diagnóstico mejorados a Microsoft en un identificador comercial conocido. Como parte del escritorio administrado de Microsoft, los administradores de ti no pueden cambiar esta configuración. Para los clientes de las regiones de la normativa general de protección de datos (RGPD), los usuarios pueden reducir el nivel de datos de diagnóstico que se proporciona, pero habrá una reducción del servicio. Por ejemplo, el escritorio administrado de Microsoft no podrá recopilar los datos necesarios para iterar en las configuraciones y directivas que mejor se adapten a las necesidades de rendimiento y seguridad. Para obtener más información, vea [Configure Windows Diagnostic Data in your Organization.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Apéndice de seguridad

 En esta sección se describen las directivas que se implementarán además de las directivas de escritorio administradas estándar de Microsoft que aparecen en [las directivas predeterminadas](#default-policies). Esta configuración se ha diseñado teniendo en cuenta los servicios financieros y las industrias altamente reguladas, lo que optimiza la máxima seguridad al tiempo que mantiene la productividad del usuario.

 ### <a name="additional-security-policies"></a>Directivas de seguridad adicionales

 Estas directivas se agregan para aumentar la seguridad de las industrias altamente reguladas. 
 - **Supervisión de seguridad**: Microsoft realizará un seguimiento de los dispositivos con la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Si se detecta una amenaza, Microsoft lo notifica al cliente, aísla el dispositivo y rectifica el problema de forma remota. 
 - **Deshabilitar PowerShell V2**: Microsoft quitó PowerShell V2 en agosto de 2017. Esta característica se ha deshabilitado en todos los dispositivos de escritorio administrados por Microsoft. Para obtener más información sobre este cambio, consulte [Windows PowerShell 2,0 deprecated](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).
