---
title: Configuración de dispositivos
description: Obtenga información sobre las directivas predeterminadas que se aplican a los dispositivos de escritorio administrados por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a080c044939dfde223c231dfebdd248861d5f9f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278629"
---
# <a name="device-configuration"></a>Configuración de dispositivos


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Cuando se aprovisiona un nuevo dispositivo de escritorio administrado por Microsoft, garantizamos que la configuración correcta, optimizada para el escritorio administrado por Microsoft, esté en su ubicación. Esto incluye un conjunto de directivas predeterminadas que se establecen como parte del proceso de incorporación. Para evitar conflictos, estas directivas no deben modificarse. 

Los dispositivos llegarán con una imagen de firma y, a continuación, se unirán al dominio de Active Directory de Azure cuando el primer usuario inicie sesión. El dispositivo instalará automáticamente las directivas y aplicaciones necesarias sin necesidad de que intervenga la TI.

## <a name="why-mdm-over-group-policy"></a>Por qué MDM sobre la Directiva de grupo

Hay algunas razones para usar la administración de dispositivos móviles (MDM) en lugar de la Directiva de Grupo:

- Seguridad: las directivas de MDM son más seguras en el mundo moderno. La Directiva de grupo está diseñada para funcionar mejor con la identidad local mientras que MDM diseñada para funcionar mejor con la administración de identidades en la nube (Azure Active Directory).
- Confiabilidad: las directivas MDM proporcionan una implementación de directivas más fiable. Además, la configuración de MDM sobrescribe las directivas de objetos de directiva de grupo (GPO). A partir de Windows 10, versión 1803, la configuración de MDM se priorizará a través de los valores de la Directiva de grupo, lo que permite a los clientes cambiar a la administración moderna. 
- Alineación con Microsoft manAged Desktop Vision: proporciona supervisión más completa sobre la implementación de directivas y admite el método basado en grupos para implementar gradualmente los cambios de directiva con la capacidad de pausar o reanudar la implementación cuando sea necesario.

Para obtener más información, vea [Administración de dispositivos móviles](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Directivas predeterminadas

En esta tabla se resaltan las directivas predeterminadas que se aplican a todos los dispositivos de escritorio administrados por Microsoft durante el aprovisionamiento de dispositivos. Se revertirán todos los cambios detectados no aprobados por el equipo de operaciones de escritorio administrado por Microsoft para objetos administrados por el escritorio administrado por Microsoft.

Directiva | Descripción
--- | ---
Línea de base de seguridad | [Microsoft Security Baseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM está configurado para todos los dispositivos de escritorio administrados por Microsoft. Esta línea base es la configuración estándar del sector. Se publica, se prueba de forma pública y los expertos en seguridad de Microsoft lo han revisado para mantener seguras los dispositivos de escritorio y las aplicaciones administrados por Microsoft en el lugar de trabajo moderno. <br><br>Para mitigar las amenazas en el panorama constante de la amenaza de seguridad, la línea base de seguridad de Microsoft se actualizará e implementará en los dispositivos de escritorio administrados por Microsoft con cada actualización de características de Windows 10.<br><br>Para obtener más información, consulte [Baseline Security para Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Plantilla de seguridad recomendada para escritorio administrado de Microsoft | Un conjunto de cambios recomendados en la línea de base de seguridad que optimizan la experiencia del usuario.  Estos cambios se documentan en [el apéndice de seguridad](#security-addendum). Las actualizaciones del anexo de Directiva se producen según sea necesario.  
Cumplimiento de dispositivos | Estas directivas se configuran de forma predeterminada para todos los dispositivos de escritorio administrados por Microsoft. Se notifica que un dispositivo no es compatible Si no se cumple alguna de las condiciones de seguridad siguientes:<br>-Habilitación del cifrado de dispositivos BitLocker, para proteger los datos en los dispositivos. Para obtener más información, vea [información general sobre el cifrado de dispositivos de BitLocker en Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Arranque seguro habilitado y aplicado para validar imágenes de firmware en dispositivos antes de que se puedan ejecutar. Para obtener más información, vea información [General sobre el cifrado de dispositivos y de inicio seguro.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-El dispositivo de escritorio administrado de Microsoft requiere contraseña para iniciar sesión.
Implementación de la actualización | Use Windows Update para empresas (WUfB) para realizar la implementación gradual de las actualizaciones de software. Los administradores de ti no pueden modificar la configuración de las directivas de grupo de implementación. Para obtener más información sobre la implementación basada en grupos, vea [cómo se administran las actualizaciones](../working-with-managed-desktop/updates.md).
Datos de diagnóstico | Los dispositivos se configurarán para proporcionar datos de diagnóstico mejorados a Microsoft en un identificador comercial conocido. Como parte del escritorio administrado de Microsoft, los administradores de ti no pueden cambiar esta configuración. Para los clientes de las regiones generales del Reglamento de protección de datos (RGPD), los usuarios finales pueden reducir el nivel de datos de diagnóstico que se proporciona, pero habrá una reducción del servicio. Por ejemplo, el escritorio administrado de Microsoft no podrá recopilar los datos necesarios para iterar en las configuraciones y directivas que mejor se adapten a las necesidades de rendimiento y seguridad. Para obtener más información, vea [Configure Windows Diagnostic Data in your Organization.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Apéndice de seguridad

 En esta sección se describen las directivas que se implementarán como adicionales a las directivas de escritorio administradas estándar de Microsoft. Las directivas estándar se muestran en [las directivas](#default-policies)predeterminadas. Esta configuración se ha diseñado teniendo en cuenta los servicios financieros y las industrias altamente reguladas: la optimización de la postura más segura, a la vez que mantiene la productividad del usuario.

 ### <a name="additional-security-policies"></a>Directivas de seguridad adicionales

 Estas directivas se agregan para aumentar la seguridad de las industrias altamente reguladas. 
 - **Lista**de permitidos de aplicaciones: la organización debe confiar en las aplicaciones para que se ejecuten en dispositivos de escritorio administrados por Microsoft. Esto proporciona un entorno bloqueado. Todas las aplicaciones que deban incorporarse deben comunicarse al equipo de operaciones de escritorio administrado de Microsoft. Para obtener más información, consulta [protección de dispositivos de Windows Defender](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Supervisión de seguridad**: Microsoft supervisará los dispositivos con la [protección contra amenazas avanzada de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Si se detecta una amenaza, Microsoft le notificará al cliente, aislará el dispositivo y rectificará el problema de forma remota. 

