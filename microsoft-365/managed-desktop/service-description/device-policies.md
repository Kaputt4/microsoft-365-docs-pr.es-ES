---
title: Configuración de dispositivo
description: Obtenga información sobre las directivas predeterminadas que se aplican a los dispositivos de escritorio administrado de Microsoft.
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871606"
---
# <a name="device-configuration"></a>Configuración de dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Cuando se aprovisiona un nuevo dispositivo de escritorio de Microsoft administrado, se compruebe que la configuración correcta, optimizada para escritorio administrado de Microsoft, en su lugar. Esto incluye un conjunto de directivas predeterminadas que se han establecido como parte del proceso de incorporación. Para evitar conflictos, no se deben modificar estas directivas. 

Los dispositivos se llegan con una imagen de firma, a continuación, unirse al dominio de Active Directory de Azure cuando el primer usuario inicia sesión. El dispositivo instalará automáticamente sin la intervención de TI necesitada directivas necesarias y las aplicaciones.

## <a name="why-mdm-over-group-policy"></a>¿Por qué MDM a través de directiva de grupo

Hay algunas razones para usar Administración de dispositivos móviles (MDM) en lugar de directiva de grupo:

- Seguridad - directivas MDM son más seguras en el mundo moderno. Directiva de grupo está diseñada para funcionar mejor con identidad local mientras MDM diseñado para funcionar mejor con la administración de identidades en la nube (Azure Active Directory).
- Confiabilidad - las directivas MDM permiten la implementación de directiva de más confiable. Además, configuración de MDM sobrescribe las directivas de objeto de directiva de grupo (GPO). Iniciar con Windows 10, versión 1803, configuración MDM le dará prioridad sobre los valores de directiva de grupo, que es compatible con los clientes de pasar a la administración moderno. 
- Alinear con visión de escritorio administrado de Microsoft - proporciona supervisión más completa en la implementación de la directiva y es compatible con el enfoque basado en grupo para gradualmente los cambios de directiva de implantación con capacidad para pausar o reanudar la implementación cuando sea necesario.

Para obtener más información, vea [Administración de dispositivos móviles](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Directivas predeterminadas

Esta tabla destacan las directivas predeterminadas que se aplican a todos los dispositivos de escritorio de Microsoft administrado durante el aprovisionamiento de dispositivos. Todos los detectados cambios no aprobados por el equipo de operaciones de escritorio administrado de Microsoft para objetos administrados por Microsoft Desktop administradas se pueden revertir.

Directiva | Descripción
--- | ---
Línea de base de seguridad | [Línea de base de seguridad de Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM está configurado para todos los dispositivos de escritorio administrado de Microsoft. Esta línea de base es la configuración estándar del sector. Que se haya lanzado, bien probado y se ha revisado por expertos de seguridad de Microsoft para mantener los dispositivos de escritorio de Microsoft administrado y seguro de aplicaciones en el lugar de trabajo moderno.<br><br>Para mitigar las amenazas en el panorama de amenazas de seguridad en constante evolución, se actualiza la línea de base de seguridad de Microsoft e implementado en los dispositivos de escritorio administrado de Microsoft con cada actualización de la función 10 de Windows.<br><br>Para obtener más información, vea la [línea de base de seguridad para Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Recomendado plantilla de seguridad de escritorio administrado de Microsoft | Un conjunto de cambios recomendados en la línea de base de seguridad que optimizan la experiencia del usuario.  Estos cambios se documentan en [El apéndice de seguridad](#security-addendum). Las actualizaciones para el anexo de la directiva se produzcan según sea necesario.  
Cumplimiento de dispositivo | Estas directivas se configuran de forma predeterminada para todos los dispositivos de escritorio administrado de Microsoft. Un dispositivo se indica como no compatibles cuando no se cumple una de las siguientes condiciones de seguridad:<br>-Cifrado de dispositivos BitLocker habilitado, para proteger los datos en los dispositivos. Para obtener más información, vea [información general de dispositivo el cifrado BitLocker en Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Seguro inicio habilitado y exigen, para validar las imágenes de firmware en dispositivos antes de que éstos puedan ejecutar. Para obtener más información, vea [Introducción al cifrado de arranque y dispositivo seguro.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Dispositivo de escritorio de Microsoft administrado requiere contraseña para el inicio de sesión.
Implementación de la actualización | Utilice Windows Update para la empresa (WUfB) para realizar la implementación gradual de las actualizaciones de software. Los administradores de TI no pueden modificar la configuración de las directivas de grupo de distribución. Para obtener más información sobre la implementación basada en grupo, vea [cómo se controlan las actualizaciones](../working-with-managed-desktop/updates.md).
Telemetría | Los dispositivos se establecerá para proporcionar datos de diagnóstico mejorados a Microsoft en un identificador comercial conocido. Como parte del escritorio de Microsoft administrado, los administradores de TI no pueden cambiar esta configuración. Para los clientes en General regiones Reglamento de protección de datos (GDPR), los usuarios finales pueden reducir el nivel de datos de diagnóstico que se proporcionan, pero habrá una reducción en el servicio. Por ejemplo, Microsoft Managed Desktop será no se pueden recopilar los datos necesarios para realizar una iteración en directivas y configuración que sirva mejor las necesidades de rendimiento y seguridad. Para obtener más información, vea [datos de diagnóstico de configuración de Windows en su organización.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Apéndice de seguridad

 En esta sección se describe las directivas que se va a implementar como adicionales a las directivas de escritorio administrado de Microsoft estándares. Las directivas estándares se enumeran en [las directivas predeterminadas](#default-policies). Esta configuración está diseñada con servicios financieros y sectores altamente regulado en cuenta: optimización para la actitud más segura, mientras se mantiene la productividad del usuario.

 ### <a name="additional-security-policies"></a>Directivas de seguridad adicionales

 Estas directivas se agregan a aumentar la seguridad de industrias altamente regulado. 
 - **Lista de permitidos de la aplicación**: aplicaciones deben ser de confianza para la organización para que se ejecute en dispositivos de escritorio administrado de Microsoft. Esto proporciona un entorno bloqueado. Deben comunicarse cualquier aplicaciones que necesitan ser onboarded para el equipo de operaciones de escritorio administrado de Microsoft. Para obtener más información, vea [Windows Defender dispositivo Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Supervisión de la seguridad**: Microsoft va a supervisar los dispositivos mediante [La protección de amenaza avanzada de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Si se detecta una amenaza, Microsoft le notificará al cliente, aislar el dispositivo y corregir el problema de forma remota. 

