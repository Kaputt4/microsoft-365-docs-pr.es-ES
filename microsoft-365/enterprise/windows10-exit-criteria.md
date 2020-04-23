---
title: 'Fase 3: Criterios de salida de infraestructura de Windows 10 Enterprise'
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Asegúrese de que la configuración cumple con los criterios de Microsoft 365 Enterprise para Windows 10 Enterprise.
ms.openlocfilehash: cf4a813a6cf89029eebde8e5947caf7b3c2ea553
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636692"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>Fase 3: Criterios de salida de infraestructura de Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Asegúrese de que su infraestructura de Windows 10 Enterprise cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>Necesario: Los dominios de Microsoft 365 se agregan y comprueban

El inquilino de Azure AD para sus suscripciones de Office 365 e Intune está configurado con sus nombres de dominio de Internet (por ejemplo, contoso.com), en lugar de solo un nombre de dominio que incluya "onmicrosoft.com". 

Si no lo hace, estará limitando los métodos de autenticación que puede configurar. Por ejemplo, el paso a través y la autenticación federada no pueden usar el nombre de dominio de "onmicrosoft.com".

Si es necesario, el [paso 1](windows10-prepare-your-org.md) puede ayudarle con este requisito.

## <a name="optional-your-users-are-added-and-licensed"></a>Opcional: Los usuarios se agregan y reciben una licencia

Se agregan las cuentas correspondientes a los usuarios, ya sea directamente a su inquilino de Azure AD para sus suscripciones de Office 365 e Intune o a partir de la sincronización de directorios del servidor local de los servicios de dominio de Active Directory (AD DS).

Cuando se agregan los usuarios, puede asignarles licencias de Microsoft 365 Enterprise, directamente como un administrador global o de usuarios, o automáticamente a través de la pertenencia a grupos.

Si es necesario, el [paso 1](windows10-prepare-your-org.md) puede ayudarle con esta opción.

## <a name="optional-diagnostics-are-enabled"></a>Opcional: el diagnóstico está habilitado

Se ha habilitado la configuración de datos de diagnóstico mediante Directiva de grupo, Microsoft Intune, el Editor del Registro o en el símbolo del sistema.

Si es necesario, el [paso 1](windows10-prepare-your-org.md) puede ayudarle con esta opción.

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>Para la actualización local: crear una secuencia de tareas de Configuration Manager para una implementación de sistema operativo

Para iniciar una secuencia de tareas de Configuration Manager con el fin de realizar una actualización local en un dispositivo con Windows 7 o Windows 8.1, debe:

- Establecer el nivel de datos de diagnóstico de Windows adecuado
- Haber comprobado la preparación para actualizar Windows
- Haber creado la secuencia de tareas de Configuration Manager que incluya una colección de dispositivos y una implementación de sistema operativo con una imagen de sistema operativo de Windows 10

Una vez hecho todo esto, puede realizar actualizaciones en los dispositivos que están preparados para actualizar Windows. Para obtener el máximo partido de Microsoft 365 Enterprise, actualice tantos dispositivos que utilicen Windows 7 y Windows 8.1 como sea posible. 

Cada dispositivo con Windows 10 Enterprise puede beneficiarse de las ventajas de la solución integrada de Microsoft 365 Enterprise. Los dispositivos con Windows 7 o Windows 8.1 restantes no pueden usar las tecnologías conectadas a la nube ni las características de seguridad avanzadas de Windows 10 Enterprise.

Si es necesario, el [paso 2](windows10-deploy-inplaceupgrade.md) puede ayudarle con este requisito.

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>Necesario para los nuevos dispositivos: configurar Windows Autopilot

Para usar Windows Autopilot con el fin de implementar y personalizar Windows 10 Enterprise en un dispositivo nuevo, debe:

- Haber configurado el nivel de datos de diagnóstico de Windows adecuado
- Haber configurado los requisitos previos de Windows Autopilot, entre los que se incluyen:
   - El registro de dispositivos y la personalización de la configuración rápida
   - Personalización de marca para configuración rápida
   - Inscripción automática de MDM en Microsoft Intune
   - Conectividad de red a servicios en la nube usados por Windows Autopilot
- Los dispositivos que tienen preinstalado Windows 10, versión 1703 o posterior
- Seleccionado el Programa de implementación de Windows Autopilot para su organización

Una vez que se ha realizado la configuración de Windows Autopilot, puede usarlo para configurar y personalizar Windows 10 Enterprise para la configuración rápida (OOBE) de:

- Nuevos dispositivos
- Dispositivos que ya han completado una configuración de fábrica en su organización. 

Windows Autopilot configura el dispositivo y lo conecta a Azure AD.

Sin Windows Autopilot, debe configurar manualmente los nuevos dispositivos, incluida la conexión a Azure AD.

Si es necesario, el [paso 3](windows10-deploy-autopilot.md) puede ayudarle con este requisito.

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>Opcional: Usa Estado de dispositivos de Windows Analytics para supervisar los dispositivos con Windows 10 Enterprise

Usó la información de Supervisar el estado de los dispositivos con Estado del dispositivo para detectar y solucionar los problemas que afectan a los usuarios finales. Tratar rápidamente los problemas de los usuarios finales puede reducir los costos de soporte técnico y mostrar a los usuarios el compromiso de TI con Windows 10 Enterprise, lo que puede ayudarle a impulsar la adopción en toda la organización. 

Si es necesario, el [paso 4](windows10-enable-windows-analytics.md) puede ayudarle con esta opción.

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>Necesario: Usa Antivirus de Windows Defender o su propia solución antimalware

Implementó Antivirus de Windows Defender o su propia solución antivirus para proteger los dispositivos que ejecutan Windows 10 Enterprise contra software malintencionado. Si implementó el Antivirus de Windows Defender, ha implementado un método de creación de informes, como Microsoft Endpoint Configuration Manager o Microsoft Intune, para supervisar la actividad y los eventos del antivirus.

Si es necesario, el [paso 5](windows10-enable-security-features.md#windows10-sec-av) puede ayudarle con este requisito.

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>Necesario: Usa Protección contra vulnerabilidades de seguridad de Windows Defender

Implementó Protección contra vulnerabilidades de seguridad de Windows Defender para proteger los dispositivos que ejecutan Windows 10 Enterprise contra intrusiones y ha implementado un método de creación de informes, como Administrador de configuración o Microsoft Intune, para supervisar la actividad y los eventos de intrusión.

Si es necesario, el [paso 5](windows10-enable-security-features.md#windows10-sec-eg) puede ayudarle con este requisito.

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>Necesario: Usa Protección contra amenazas avanzada de Microsoft Defender (solo Microsoft 365 E5)

Implementó Protección contra amenazas avanzada de Microsoft Defender (ATP) para detectar, investigar y responder a las amenazas avanzadas contra su red y los dispositivos que ejecutan Windows 10 Enterprise. 

Opcionalmente, ha integrado Microsoft Defender ATP con otras herramientas para ampliar sus capacidades.

Si es necesario, el [paso 5](windows10-enable-security-features.md#windows10-sec-atp) puede ayudarle con este requisito.

## <a name="results-and-next-steps"></a>Resultados y pasos siguientes

La infraestructura de Windows 10 Enterprise está lista para comenzar la instalación en nuevos dispositivos y las actualizaciones en contexto en dispositivos que ejecutan las versiones anteriores de Windows. Está utilizando las características de seguridad claves de Windows 10 Enterprise.

|||
|:-------|:-----|
|![Fase 4: Aplicaciones de Microsoft 365 para empresas](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| Si sigue las fases de la implementación de un extremo a otro de Microsoft 365 Enterprise, la siguiente fase es [Aplicaciones de Microsoft 365 para empresas](office365proplus-infrastructure.md). |
