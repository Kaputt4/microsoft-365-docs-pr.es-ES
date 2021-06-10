---
title: Configuración de dispositivos
description: Obtenga información sobre las directivas predeterminadas aplicadas a Escritorio administrado de Microsoft dispositivos.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920497"
---
# <a name="device-configuration"></a>Configuración de dispositivos


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Cuando se configura un Escritorio administrado de Microsoft nuevo, nos aseguramos de que tenga la configuración adecuada optimizada para Escritorio administrado de Microsoft. Esta configuración incluye un conjunto de directivas predeterminadas que se establecen como parte del proceso de incorporación. Estas directivas se entregan con Administración de dispositivos móviles (MDM) siempre que sea posible. Para obtener más información, consulta [Administración de dispositivos móviles](/windows/client-management/mdm/). 

>[!NOTE]
>Para evitar conflictos, no modifique estas directivas.

Los dispositivos llegarán con una imagen de firma y, a continuación, se unirán al Azure Active Directory cuando el primer usuario inicia sesión. El dispositivo instalará automáticamente las directivas y aplicaciones necesarias sin intervención del personal de TI.

## <a name="default-policies"></a>Directivas predeterminadas

En esta tabla se resaltan las directivas predeterminadas que se aplican a todos los Escritorio administrado de Microsoft durante el aprovisionamiento de dispositivos. Todos los cambios detectados no aprobados por Escritorio administrado de Microsoft Operations Team en objetos administrados por Escritorio administrado de Microsoft se revertirán.

Directiva | Descripción
--- | ---
Línea base de seguridad | [La línea base de](/windows/device-security/windows-security-baselines) seguridad de Microsoft para MDM está configurada para todos Escritorio administrado de Microsoft dispositivos. Esta línea base es la configuración estándar del sector. Se ha publicado públicamente, está bien probado y ha sido revisado por expertos en seguridad de Microsoft para mantener Escritorio administrado de Microsoft dispositivos y aplicaciones seguros en el lugar de trabajo moderno. <br><br>Para mitigar las amenazas en el panorama de amenazas de seguridad en constante evolución, la línea base de seguridad de Microsoft se actualizará e implementará en Escritorio administrado de Microsoft dispositivos con cada actualización Windows 10 característica.<br><br>Para obtener más información, [vea Windows líneas base de seguridad](/windows/security/threat-protection/windows-security-baselines).
Escritorio administrado de Microsoft de seguridad recomendada | Un conjunto de cambios recomendados en la línea base de seguridad que optimizan la experiencia del usuario.  Estos cambios se documentan en [el Complemento de seguridad](#security-addendum). Las actualizaciones del addendum de directiva se producen según sea necesario.  
Actualización de la implementación | Use Windows Update for Business para realizar la implementación gradual de actualizaciones de software. Los administradores de TI no pueden modificar la configuración de las directivas de grupo de implementación. Para obtener más información sobre la implementación basada en grupos, vea [How updates are handled in Escritorio administrado de Microsoft](updates.md).
Conexiones medidas | De forma predeterminada, las actualizaciones sobre las conexiones medidas (como las redes LTE) están desactivadas, aunque cada usuario puede activar independientemente esta característica en Configuración > Actualizaciones > **Opciones avanzadas**. Si quieres permitir que todos los usuarios habiliten actualizaciones [a](../working-with-managed-desktop/admin-support.md)través de conexiones medidas, envía una solicitud de cambio , que activará esta configuración para todos los dispositivos.
| Cumplimiento de dispositivos | Estas directivas están configuradas para todos Escritorio administrado de Microsoft dispositivos. Un dispositivo se notifica como no compatible cuando se aleja de nuestra configuración de seguridad necesaria.

## <a name="windows-diagnostic-data"></a>Windows de diagnóstico

 Los dispositivos se establecerán para proporcionar datos de diagnóstico mejorados a Microsoft bajo un identificador comercial conocido. Como parte de Escritorio administrado de Microsoft, los administradores de TI no pueden cambiar esta configuración. Para los clientes de las regiones del Reglamento general de protección de datos (RGPD), los usuarios pueden reducir el nivel de datos de diagnóstico que se proporciona, pero habrá una reducción en el servicio. Por ejemplo, Escritorio administrado de Microsoft no podrá recopilar los datos necesarios para iterar en la configuración y las directivas para satisfacer mejor las necesidades de rendimiento y seguridad. Para obtener más información, vea [Configure Windows diagnostic data in your organization.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Addendum de seguridad

 En esta sección se describen las directivas que se implementarán además de las directivas Escritorio administrado de Microsoft estándar enumeradas en [Directivas predeterminadas.](#default-policies) Esta configuración se ha diseñado pensando en los servicios financieros y en las industrias altamente reguladas, optimizando la seguridad más alta al mismo tiempo que se mantiene la productividad de los usuarios.

 ### <a name="additional-security-policies"></a>Directivas de seguridad adicionales

 Estas directivas se agregan para aumentar la seguridad de las industrias altamente reguladas. 
 - **Supervisión de seguridad:** Microsoft supervisará los dispositivos [con Microsoft Defender para endpoint](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Si se detecta una amenaza, Microsoft notificará al cliente, aislará el dispositivo y corregirá el problema de forma remota. 
 - **Deshabilitar PowerShell V2:** Microsoft quitó PowerShell V2 en agosto de 2017. Esta característica se ha deshabilitado en todos los Escritorio administrado de Microsoft dispositivos. Para obtener más información sobre este cambio, [vea Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).