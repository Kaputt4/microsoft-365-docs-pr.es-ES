---
title: Infraestructura de Windows 10 Enterprise para Microsoft 365 Enterprise
description: Proporciona instrucciones de alto nivel sobre los pasos necesarios para implementar Windows 10 Enterprise en equipos PC como parte de Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, Windows 10 Enterprise, implementación
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 147dd0ec0276d685177ae389092ec18ace0d7bed
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831693"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise incluye Windows 10 Enterprise, que proporciona las herramientas para hacer más y mantener la seguridad. Windows 10 Enterprise:

- **Está integrado para simplificar** : aproveche la potencia de la nube para ayudar a reducir la complejidad de la administración del entorno de dispositivos de ti moderno actual, independientemente del tamaño.
- **Tiene seguridad inteligente** , que es la versión más segura de Windows, con capacidades de seguridad inteligentes diseñadas para trabajar conjuntamente para proteger mejor su organización.
- **Permite** la creatividad y el trabajo en equipo, lo que desbloquea la creatividad y el trabajo en equipo para proporcionar la experiencia más productiva que los usuarios y el equipo de ti les encantarán.

Necesitará comprender las distintas formas en las que puede implementar el sistema operativo Windows 10 y elegir el correcto para su organización. En función de su suscripción de Microsoft 365 Enterprise, también hay características de seguridad y servicios de Windows 10 que tendrá que configurar para sacar el máximo partido de Windows 10.

>[!Note]
>Para implementar Windows 10 Enterprise y Office 365 ProPlus juntos y cambiar a un [escritorio moderno](https://www.microsoft.com/microsoft-365/modern-desktop), consulte el [Centro de implementación de escritorio moderno](https://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Implementación de Windows 10

Hay varias formas en las que puede implementar Windows 10 Enterprise en su organización. Nos centraremos en cómo puede configurar e implementar una imagen de Windows 10 Enterprise a través de estos escenarios de implementación modernos.

| Escenario de implementación | Cuándo usarlo |
|:--- |:--- |
| [Uso de Microsoft Endpoint Configuration Manager como actualización local](windows10-deploy-inplaceupgrade.md) | Seleccione esta opción si necesita actualizar equipos con Windows 7 o Windows 8,1 a la <a href="https://aka.ms/windows-10-release-information" target="_blank">versión actual</a> de Windows 10 Enterprise y los equipos están administrados actualmente con <a href="https://aka.ms/introtosccm" target="_blank">Configuration Manager (rama actual)</a>. |
| [Uso de Windows AutoPilot](windows10-deploy-autopilot.md) | Seleccione esta opción si va a configurar nuevos equipos con Windows que tienen instalado Windows 10 Enterprise, versión 1703 o posterior. Los usuarios finales iniciarán la instalación con la configuración deseada; para ello, escriba sus credenciales de cuenta profesional o educativa. |

Si estos escenarios de implementación no se ajustan a las necesidades de su organización, puede obtener información sobre otros escenarios y comprender las capacidades y limitaciones de cada uno de los [escenarios de implementación de Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). También puede <a href="https://aka.ms/planforwin10deployment" target="_blank">planear la implementación de Windows 10</a> por su cuenta.

Puede obtener más información sobre Windows 10 con estos artículos:

- [Página del producto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Implementar y actualizar Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Servicios y características adicionales
Como parte de la implementación de Windows 10 Enterprise, puede agregar estos servicios y características adicionales.

### <a name="windows-analytics"></a>Windows Analytics

Windows usa datos de diagnóstico para proporcionar información enriquecida y que requiere acción para ayudarle a obtener información detallada sobre la eficacia operativa y el estado de los dispositivos con Windows 10 en su entorno.

* Preparación para la actualización: la preparación para la actualización le ayudará a pasar a Windows 10 y mantenerse al día con las nuevas actualizaciones de características de Windows 10. 
* Cumplimiento de la actualización: el cumplimiento de la actualización se dirige al administrador de ti que desea obtener una vista holística de todos sus dispositivos con Windows 10, sin requisitos de infraestructura adicionales.
* Estado del dispositivo: puede usar el estado del dispositivo para detectar y corregir de forma proactiva los problemas de impacto del usuario final.

Consulte [información general de Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) para obtener más información.

### <a name="windows-security"></a>Seguridad de Windows

Windows 10 proporciona características para ayudar a proteger contra las amenazas, ayudar a proteger los dispositivos y ayudar con el control de acceso. Con Windows 10, obtendrás características de seguridad críticas que protegen el dispositivo desde el principio. Microsoft 365 E3 agrega características de seguridad como Windows Hello para empresas, el control de aplicaciones de Windows Defender y Windows Information Protection. Con Microsoft 365 E5, obtiene toda la protección de las características de seguridad basadas en la nube de Microsoft 365 E3 Security Plus y de la protección contra amenazas avanzada de Microsoft defender. 

Para obtener más información sobre las características de seguridad que se obtienen con Windows 10 Enterprise y obtener instrucciones sobre cómo implementar, administrar, configurar y solucionar tres características de seguridad clave, vea [STEP 5: deploy Windows 10 Enterprise Security Features](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Obtenga una ojeada dentro de Microsoft y obtenga información sobre cómo la compañía [implementó Windows 10 Enterprise y está usando la autenticación segura, Intune y ATP de Microsoft defender](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Cómo Contoso hizo Microsoft 365 Enterprise

Vea cómo contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó Windows 10 Enterprise](contoso-win10.md).

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 1](./media/stepnumbers/Step1.png)| [Preparar la organización para Windows 10 Enterprise](windows10-prepare-your-org.md) |
