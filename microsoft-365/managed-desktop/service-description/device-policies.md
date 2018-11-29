---
title: Configuración de dispositivo
description: Obtenga información sobre las directivas predeterminadas que se aplican a los dispositivos de escritorio administrado de Microsoft.
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 5a97f44641ac38a8785bde66819dbfffffee946d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871606"
---
# <a name="device-configuration"></a>Configuración de dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Cuando se aprovisiona un nuevo dispositivo de escritorio de Microsoft administrado, se compruebe que la configuración correcta, optimizada para escritorio administrado de Microsoft, en su lugar. Esto incluye un conjunto de directivas predeterminadas que están configurados como parte del proceso de incorporación. Para evitar conflictos, no se deben modificar estas directivas. 

Los dispositivos se llegan con una imagen de firma, a continuación, unirse al dominio de Active Directory de Azure cuando el primer usuario inicia sesión. El dispositivo instalará automáticamente sin la intervención de TI necesitada directivas necesarias y las aplicaciones.

## <a name="why-mdm-over-group-policy"></a>¿Por qué MDM a través de directiva de grupo

Hay algunas razones para usar Administración de dispositivos móviles (MDM) en lugar de directiva de grupo:

- Seguridad - directivas MDM son más seguras en el mundo moderno. Directiva de grupo diseñado para funcionar mejor con identidad local. MDM diseñado para funcionar mejor con la administración de identidades en la nube (Azure Active Directory (AD Azure)).
- Confiabilidad - las directivas MDM permiten la implementación de directiva de más confiable. Configuración del MDM sobrescribe las directivas de objeto de directiva de grupo (GPO). Iniciar con Windows 10, versión 1803, configuración de MDM le dará prioridad sobre los valores de directiva de grupo. Esto es compatible con los clientes de pasar a la administración moderno. 
- Alinear con visión de escritorio administrado de Microsoft - supervisión mejor en la implementación de la directiva. Admite el método basado en la llamada a gradualmente los cambios de directiva de implantación con capacidad para pausar o reanudar la implementación cuando sea necesario.

## <a name="default-policies"></a>Directivas predeterminadas

Esta tabla información importante el valor predeterminado las directivas que se aplica a todos los dispositivos de escritorio de Microsoft administrado durante el aprovisionamiento de dispositivos. Para evitar conflictos, no se deben modificar estas directivas. Todos los detectados cambios no aprobados por el equipo de operaciones de escritorio administrado de Microsoft para objetos administrados por Microsoft Desktop administradas se pueden revertir.

Directiva | Descripción
--- | ---
Línea de base de seguridad | [Línea de base de seguridad de Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM está configurado para todos los dispositivos de escritorio administrado de Microsoft. Esta línea de base es la configuración estándar del sector. Que se haya lanzado, bien probado y se ha revisado por expertos de seguridad de Microsoft para mantener los dispositivos de escritorio de Microsoft administrado y seguro de aplicaciones en el lugar de trabajo moderno.<br><br>Para mitigar las amenazas en el panorama de amenazas de seguridad en constante evolución, se actualiza la línea de base de seguridad de Microsoft e implementado en los dispositivos de escritorio administrado de Microsoft con cada actualización de la función 10 de Windows.<br><br>Para obtener más información, vea la [línea de base de seguridad para Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Recomendado plantilla de seguridad de escritorio administrado de Microsoft | Un conjunto de cambios recomendados en la línea de base de seguridad que optimizan la experiencia del usuario.  Estos cambios se documentan en [El apéndice de seguridad](#security-addendum). Las actualizaciones para el anexo de la directiva se produzcan según sea necesario.  
Cumplimiento de dispositivo | Estas directivas se configuran de forma predeterminada para todos los dispositivos de escritorio administrado de Microsoft. Un dispositivo se indica como no compatibles cuando no se cumple una de las siguientes condiciones de seguridad:<br>-Cifrado de dispositivos BitLocker habilitado, para proteger los datos en los dispositivos. Para obtener más información, vea [información general de dispositivo el cifrado BitLocker en Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Seguro inicio habilitado y exigen, para validar las imágenes de firmware en dispositivos antes de que éstos puedan ejecutar. Para obtener más información, vea [Introducción al cifrado de arranque y dispositivo seguro.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Contraseña requerida para obtener acceso a los dispositivos de escritorio administrado de Microsoft.
Implementación de la actualización | Utilice Windows Update para la empresa (WUfB) para realizar la implementación gradual de las actualizaciones de software. Los administradores de TI no pueden modificar la configuración de las directivas de anillo de implementación. Para obtener más información acerca de la implementación basada en anillo, vea [cómo se controlan las actualizaciones](../working-with-managed-desktop/updates.md).
Telemetría | Los dispositivos se establecerá para proporcionar datos de diagnóstico mejorada a Microsoft en un identificador comercial conocido. Para los clientes en General regiones Reglamento de protección de datos (GDPR), los usuarios finales pueden reducir el nivel de datos de diagnóstico que se proporcionan. Puede personalizar esta, pero habrá una reducción en el servicio. Para obtener más información, vea [datos de diagnóstico de configuración de Windows en su organización.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="advanced-policies"></a>Directivas avanzadas

 Estos son las directivas adicionales que se pueden configurar para un entorno más seguro y bloqueado, para sectores altamente regulado.

 Directiva | Descripción
 --- | ---
 Capacidades avanzadas | Protección de información de Windows (curso) & protección de información de Azure (AIP) se usan para proteger los datos de la empresa, por sólo permita el acceso a determinados individuos o un subconjunto de las aplicaciones o servicios. Para obtener más información, vea<br>- [Proteger los datos de empresa con protección de la información de Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)<br>- [Guía de administrador de cliente de protección de la información Azure](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)<br>- [Microsoft administrados Addendum de seguridad de escritorio](#security-addendum)

 ## <a name="security-addendum"></a>Apéndice de seguridad

 En esta sección se describe las directivas que se va a implementar como adicionales a las directivas de escritorio administrado de Microsoft estándares. Las directivas estándares se enumeran en [las directivas predeterminadas](#default-policies). Esta configuración está diseñada con servicios financieros y sectores altamente regulado en cuenta: optimización para la actitud más segura, mientras se mantiene la productividad del usuario.

Un cambio en la **línea de base de seguridad**de publicado, se deshabilitará la opción [**no mostrar la interfaz de usuario de selección de red**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowslogon#windowslogon-dontdisplaynetworkselectionui) .

 ### <a name="additional-security-policies"></a>Directivas de seguridad adicionales

 Estas directivas se agregan a aumentar la seguridad de industrias altamente regulado. 
 - **Lista de permitidos de la aplicación**: aplicaciones deben ser de confianza para la organización para que se ejecute en dispositivos de escritorio administrado de Microsoft. Esto proporciona un entorno bloqueado. Deben comunicarse cualquier aplicaciones que necesitan ser onboarded para el equipo de operaciones de escritorio administrado de Microsoft. Para obtener más información, vea [Windows Defender dispositivo Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Supervisión de la seguridad**: Microsoft va a supervisar los dispositivos mediante [La protección de amenaza avanzada de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Si se detecta una amenaza, Microsoft le notificará al cliente, aislar el dispositivo y corregir el problema de forma remota. 
 - **Aprovechar Guard**: se asegurará que los dispositivos de escritorio de Microsoft administrado siempre se protegen con la actualización de seguridad más reciente para el sistema operativo y aplicaciones, uso de [Windows Update para la empresa](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb). Guard vulnerabilidad se configurarán con estas opciones:

 Configuración | Directiva
 --- | ---
 Marcar credenciales robar desde el subsistema de autoridad de seguridad local de Windows | Sólo auditoría
 Adición de en otros procesos de aplicaciones de Office | Sólo auditoría
 Creación de contenido ejecutable aplicaciones/macros de Office | Bloque
 Iniciar procesos secundarios de aplicaciones de Office | Sólo auditoría
 Importa Win32 desde el código de macro de Office | Bloque
 Confusos código js/vbs/ps o macro | Bloque
 Ejecución carga js/vbs descargar desde internet (sin excepciones) | Bloque
 Creación del proceso de los comandos PSExec y WMI | Sólo auditoría
 Sin firmar y que no son procesos que se ejecutan desde USB | Bloque
 Archivos ejecutables que no cumplen con los criterios de la lista de confianza, vigencia o una difusión | Sólo auditoría
 Quita la ejecución de contenido ejecutable de correo electrónico | Bloque
 Protección avanzada ransomware | Sólo auditoría









