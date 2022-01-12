---
title: Paso 5. Implementar perfiles de dispositivo en Microsoft Intune
ms.author: bcarter
author: brendacarter
f1.keywords:
- configuration profiles
- Windows security baselines for Intune
- customize configuration profiles
manager: dougeby
audience: ITPro
description: Introducción a los perfiles de configuración para aplicar una configuración segura en los dispositivos que usan Intune para realizar la transición de estos controles de seguridad a la nube.
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- Configuration profiles
- Windows security baselines for Intune
- customize configuration profiles-
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: 94825143349b329cf571c9735a3573f8fc65e8b8
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61939302"
---
# <a name="step-5-deploy-device-profiles-in-microsoft-intune"></a>Paso 5. Implementar perfiles de dispositivo en Microsoft Intune

Microsoft Intune incluye las opciones de configuración y las características que puede habilitar o deshabilitar en distintos dispositivos de la organización. Estas opciones de configuración y características se agregarán a "perfiles de configuración". Puede crear perfiles para diferentes dispositivos y distintas plataformas, como iOS/iPadOS, administrador de dispositivos Android, Android Enterprise y Windows. Luego, use Intune para aplicar o "asignar" el perfil a los dispositivos.

En este artículo se proporcionan instrucciones introductorias sobre los perfiles de configuración. 


![Pasos para administrar dispositivos](../media/devices/intune-mdm-step-4.png#lightbox)

Los perfiles de configuración le ofrecen la posibilidad de configurar una protección importante y de hacer que los dispositivos cumplan los requisitos para que puedan acceder a los recursos. Anteriormente, estos tipos de cambios se configuraban mediante la configuración de directiva de grupo en Active Directory Domain Services. Una estrategia de seguridad moderna incluye mover controles de seguridad a la nube, donde la aplicación de estos controles no depende de los recursos locales y el acceso. Los perfiles de configuración de Intune son la manera de realizar la transición de estos controles de seguridad a la nube. 

Para darte una idea del tipo de perfiles de configuración que puedes crear, consulta [Aplicar funciones y configuración en los dispositivos mediante perfiles de dispositivos en Microsoft Intune](/mem/intune/configuration/device-profiles).

## <a name="deploy-windows-security-baselines-for-intune"></a>Implementar las líneas base de seguridad de Windows para Intune

Como punto de partida, si deseas alinear las configuraciones de dispositivos con las líneas base de seguridad de Microsoft, se recomiendan las líneas base de seguridad de Microsoft Endpoint Manager. La ventaja de este enfoque es que puedes confiar en Microsoft para mantener actualizadas las líneas base a medida que se publican características de Windows 10 y 11. 

Para implementar las líneas base de seguridad de Windows para Intune, disponibles para Windows 10 y Windows 11. Consulta [Usar las líneas base de seguridad para configurar dispositivos Windows en Intune](/mem/intune/protect/security-baselines) para obtener información sobre las líneas base disponibles.

Por ahora, solo tienes que implementar las líneas base de seguridad de MDM más adecuadas. Consulta [Gestionar perfiles de líneas base de seguridad en Microsoft Intune ](/mem/intune/protect/security-baselines-configure) para crear el perfil y elegir la versión de las líneas base.

Más adelante, cuando Microsoft Defender para punto de conexión esté configurado y hayas conectado Intune, implementa las líneas base de Defender para punto de conexión. Este tema se trata en el siguiente artículo de esta serie: [Paso 6. Supervisar el riesgo del dispositivo y el cumplimiento de las líneas base de seguridad](manage-devices-with-intune-monitor-risk.md).

Es importante comprender que estas líneas base de seguridad no son compatibles con CIS o NIST, sino que reflejan estrechamente sus recomendaciones. Para obtener más información, consulta [¿Cumplen las líneas base de seguridad de Intune con CIS o NIST](/mem/intune/protect/security-baselines)?

## <a name="customize-configuration-profiles-for-your-organization"></a>Personalizar perfiles de configuración para su organización

Además de implementar las líneas base preconfiguradas, muchas organizaciones de escala empresarial implementan perfiles de configuración para un control más pormenorizado. Esta configuración ayuda a reducir la dependencia de los objetos de directivas de grupo en el entorno de Active Directory local y a mover los controles de seguridad a la nube. 

Las muchas opciones que puedes configurar mediante perfiles de configuración se pueden agrupar en cuatro categorías, como se muestra a continuación.

![Categorías de perfil de dispositivos de Intune](../media/devices/intune-device-profile-categories.png#lightbox)

En la tabla siguiente se describe la ilustración.


|Categoría |Descripción |Ejemplos  |
|---------|---------|---------|
|Características del dispositivo     | Controla las características del dispositivo. Esta categoría solo se aplica a dispositivos iOS/iPadOS y macOS.        | Airprint, notificaciones, mensajes de pantalla de bloqueo        |
|Restricciones de dispositivo     | Controla la seguridad, el hardware, el uso compartido de datos y más opciones de configuración en los dispositivos        | Requerir un PIN, cifrado de datos        |
|Configuración de acceso     |  Configura un dispositivo para acceder a los recursos de la organización        | Perfiles de correo electrónico, perfiles de VPN, configuración de Wi-Fi, certificados        |
|Personalizado     | Establecer la configuración personalizada o ejecutar acciones de configuración personalizadas       | Establecer la configuración de OEM, ejecutar scripts de PowerShell        |
|    |         |         |

Al personalizar los perfiles de configuración de su organización, usa las siguientes instrucciones:
- Simplifica la estrategia de gobernanza de la seguridad manteniendo un número total de directivas reducido.
- Agrupar la configuración en las categorías enumeradas anteriormente o en las categorías que tengan sentido para tu organización.
- Al mover controles de seguridad de objetos de directiva de grupo (GPO) a perfiles de configuración de Intune, ten en cuenta si las opciones configuradas por cada GPO siguen siendo relevantes y necesarias para contribuir a la estrategia de seguridad en la nube general. El acceso condicional y las muchas directivas que se pueden configurar en los servicios en la nube, incluido Intune, proporcionan una protección más sofisticada de la que se podría configurar en un entorno local donde se diseñaron originalmente los GPO personalizados.
- Usa el análisis de directivas de grupo para comparar y asignar la configuración actual de los GPO a las funcionalidades de Microsoft Endpoint Manager. Consulta [Analizar los objetos de la directiva de grupo (GPO) locales con el análisis de directivas de grupo](/mem/intune/configuration/group-policy-analytics) en Microsoft Endpoint Manager.
- Al usar perfiles de configuración personalizados, asegúrate de usar las instrucciones siguientes: [Crear un perfil con configuración personalizada en Intune](/mem/intune/configuration/custom-settings-configure).

## <a name="additional-resources"></a>Recursos adicionales

Si no estás seguro de por dónde empezar con los perfiles de dispositivos, puede ayudarte lo siguiente:

- [Escenarios guiados](/mem/intune/fundamentals/guided-scenarios-overview) 
- [Líneas base de seguridad](/mem/intune/protect/security-baselines)

Si tu entorno incluye GPO locales, las siguientes características son una buena transición a la nube:

- [Análisis de directivas de grupo](/mem/intune/configuration/group-policy-analytics)
- [Plantillas de administrador (ADMX)](/mem/intune/configuration/administrative-templates-windows)
- [Catálogo de configuraciones](/mem/intune/configuration/settings-catalog)


## <a name="next-steps"></a>Pasos siguientes
Vaya al [Paso 6. Supervisar el riesgo del dispositivo y el cumplimiento de las líneas base de seguridad](manage-devices-with-intune-monitor-risk.md).
