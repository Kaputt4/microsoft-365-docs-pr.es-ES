---
title: Configuración de dispositivos
description: Obtenga información sobre las directivas predeterminadas aplicadas a los dispositivos de Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7086774c046ac28ffa467168e3b5b1affb508ec8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840337"
---
# <a name="device-configuration"></a>Configuración de dispositivos


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Cuando se configura un nuevo dispositivo de Escritorio administrado de Microsoft, nos aseguramos de que tiene la configuración correcta optimizada para escritorio administrado de Microsoft. Esta configuración incluye un conjunto de directivas predeterminadas que se establecen como parte del proceso de incorporación. Estas directivas se entregan con administración de dispositivos móviles (MDM) siempre que sea posible. Para obtener más información, vea [Administración de dispositivos móviles.](https://docs.microsoft.com/windows/client-management/mdm/) 

>[!NOTE]
>Para evitar conflictos, no modifique estas directivas.

Los dispositivos llegarán con una imagen de firma y, a continuación, se unirán al dominio de Azure Active Directory cuando el primer usuario inicia sesión. El dispositivo instalará automáticamente las directivas y aplicaciones necesarias sin intervención del personal de TI.

## <a name="default-policies"></a>Directivas predeterminadas

En esta tabla se resaltan las directivas predeterminadas que se aplican a todos los dispositivos de Escritorio administrado de Microsoft durante el aprovisionamiento de dispositivos. Se revertirán todos los cambios detectados no aprobados por Microsoft Managed Desktop Operations Team en objetos administrados por El escritorio administrado de Microsoft.

Directiva | Descripción
--- | ---
Línea base de seguridad | [La línea base de seguridad de Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM está configurada para todos los dispositivos de Escritorio administrado de Microsoft. Esta línea base es la configuración estándar del sector. Se ha publicado públicamente, está bien probado y ha sido revisado por expertos en seguridad de Microsoft para mantener seguros los dispositivos y aplicaciones de Escritorio administrado de Microsoft en el lugar de trabajo moderno. <br><br>Para mitigar las amenazas en el panorama de amenazas de seguridad en constante evolución, la línea base de seguridad de Microsoft se actualizará e implementará en dispositivos de Escritorio administrado de Microsoft con cada actualización de características de Windows 10.<br><br>Para obtener más información, vea Líneas [base de seguridad de Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)
Plantilla de seguridad recomendada de Escritorio administrado de Microsoft | Conjunto de cambios recomendados en la línea base de seguridad que optimizan la experiencia del usuario.  Estos cambios se documentan en [el anexo de seguridad](#security-addendum). Las actualizaciones del anexo de directiva se producen según sea necesario.  
Actualización de la implementación | Usa Windows Update para empresas para realizar la implementación gradual de actualizaciones de software. Los administradores de TI no pueden modificar la configuración de las directivas de grupo de implementación. Para obtener más información sobre la implementación basada en grupos, vea Cómo se controlan las actualizaciones [en el Escritorio administrado de Microsoft.](updates.md)
Conexiones de medición | De forma predeterminada, las actualizaciones a través de conexiones medidas (como redes LTE) están desactivadas, aunque cada usuario puede activar independientemente esta característica en Configuración > Actualizaciones > Opciones **avanzadas.** Si quieres permitir que todos los usuarios habiliten actualizaciones [a](../working-with-managed-desktop/admin-support.md)través de conexiones de uso medida, envía una solicitud de cambio, que activará esta configuración para todos los dispositivos.
| Cumplimiento de dispositivos | Estas directivas están configuradas para todos los dispositivos de Escritorio administrado de Microsoft. Un dispositivo se notifica como no compatible cuando se aleja de nuestra configuración de seguridad necesaria.

## <a name="windows-diagnostic-data"></a>Datos de diagnóstico de Windows

 Los dispositivos se configurarán para proporcionar datos de diagnóstico mejorados a Microsoft con un identificador comercial conocido. Como parte del Escritorio administrado de Microsoft, los administradores de TI no pueden cambiar esta configuración. Para los clientes de regiones del Reglamento general de protección de datos (RGPD), los usuarios pueden reducir el nivel de datos de diagnóstico proporcionado, pero habrá una reducción en el servicio. Por ejemplo, el Escritorio administrado de Microsoft no podrá recopilar los datos necesarios para iterar en configuraciones y directivas para satisfacer mejor las necesidades de rendimiento y seguridad. Para obtener más información, consulta [Configurar los datos de diagnóstico de Windows en la organización.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Anexo de seguridad

 En esta sección se describen las directivas que se implementarán además de las directivas estándar de Escritorio administrado de Microsoft enumeradas en [Directivas predeterminadas.](#default-policies) Esta configuración se ha diseñado pensando en los servicios financieros y en las industrias altamente reguladas, optimizando la seguridad más alta a la vez que se mantiene la productividad de los usuarios.

 ### <a name="additional-security-policies"></a>Directivas de seguridad adicionales

 Estas directivas se agregan para aumentar la seguridad de los sectores altamente regulados. 
 - **Supervisión de seguridad:** Microsoft supervisará los dispositivos [que usan Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Si se detecta una amenaza, Microsoft notificará al cliente, aislará el dispositivo y corregirá el problema de forma remota. 
 - **Deshabilitar PowerShell V2:** Microsoft quitó PowerShell V2 en agosto de 2017. Esta característica se ha deshabilitado en todos los dispositivos de Escritorio administrado de Microsoft. Para obtener más información sobre este cambio, [vea Windows PowerShell 2.0 Desuso.](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)
