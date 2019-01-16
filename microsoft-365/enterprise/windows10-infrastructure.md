---
title: Infraestructura de Windows 10 Enterprise para Microsoft 365 Enterprise
description: Proporciona una orientación de alto nivel en los pasos que necesarios para implementar Windows 10 Enterprise en los equipos como parte de Microsoft 365 Enterprise.
keywords: Microsoft, Microsoft 365 Enterprise, Microsoft 365 documentación, Enterprise del 10 de Windows, la implementación de 365
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871163"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise incluye Windows 10 Enterprise, lo que ofrece las herramientas necesarias para hacer más y mantener la seguridad. Windows 10 Enterprise:

- **Se integra por motivos de simplicidad** - Aproveche la capacidad de la nube para ayudar a reducir la complejidad de la administración de hoy en día s moderno entorno de dispositivo de TI, independientemente de su tamaño.
- **Tiene seguridad inteligente** - nunca es la versión más segura de Windows, con seguridad inteligente capacidades que están diseñadas para que funcionen conjuntamente para mejor protección a su organización.
- **Permite creatividad y trabajo en equipo** - desbloquea creatividad y trabajo en equipo para entregar a ser productivos más experimentan que los usuarios y realizarán TI love.

Debe comprender las distintas formas que puede implementar el sistema operativo Windows 10 y elegir la más adecuada para su organización. Dependiendo de su suscripción de Microsoft 365 Enterprise, también hay 10 Windows servicios y características de seguridad que necesita configurar para sacar el máximo partido de Windows 10.

10 de Windows permite estos escenarios de negocios estratégico para Microsoft 365 Enterprise:

- Aprovechar la experiencia y el conocimiento colectivo al permitir a los usuarios descubrir, compartir y trabajar en archivos, información e ideas en la organización
- Trabajar de forma segura desde cualquier lugar, en cualquier momento y con cualquier dispositivo para mejorar la productividad, a la vez que se mantiene un estilo de trabajo flexible
- Ofrecer tranquilidad con controles y visibilidad para garantizar la conformidad verificada del sector con normas de cumplimiento internacionales
- Proteger su información y reducir el riesgo de la pérdida de datos
- Detectar y proteger el informe de las amenazas externas--Monitor y analizar la actividad para reaccionar rápidamente para proporcionar seguridad de la organización
- Proteger a los usuarios y sus cuentas
- Apoyar a su organización con mayor privacidad y cumplimiento normativo para ajustarse al Reglamento General de Protección de Datos (RGPD)
- Obtener software de escritorio y dispositivos actuales y mantenerlos actualizados, a la vez que se reducen los riesgos de seguridad y se maximiza la eficiencia de TI

Para obtener más información, vea [Transformación Digital con Microsoft 365](http://transform.microsoft.com). 

>[!Note]
>Para implementar Windows 10 Enterprise y Office 365 ProPlus juntos y cambiar a un [escritorio moderno](https://www.microsoft.com/microsoft-365/modern-desktop), consulte el [Centro de implementación de escritorio moderno](http://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Implementación de Windows 10

Hay varias maneras que puede implementar Enterprise del 10 de Windows para su organización. En este caso, nos centraremos en cómo se pueden configurar e implementar una imagen de Windows 10 Enterprise a través de estos escenarios de implementación moderno.

| Escenario de implementación | Cuándo usarlo |
|:--- |:--- |
| [Uso de System Center Configuration Manager como una actualización en contexto](windows10-deploy-inplaceupgrade.md) | Seleccione esta opción si tiene que actualizar Windows 7 o Windows 8.1 equipos a la <a href="https://aka.ms/windows-10-release-information" target="_blank">versión actual</a> de Windows 10 Enterprise y los equipos actualmente se administran con <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (rama actual)</a>. |
| [Uso de piloto automático de Windows](windows10-deploy-autopilot.md) | Seleccione esta opción si está configurando nuevos equipos de Windows que tienen Windows 10 Enterprise, versión 1703 o preinstalada más adelante. Los usuarios finales va a iniciar el programa de instalación con la configuración deseada escribiendo su trabajo o escuela las credenciales de cuenta. |

Si estos escenarios de implementación no ajustan a las necesidades de su organización, puede obtener información sobre otros escenarios y comprender las capacidades y limitaciones de cada uno de [los escenarios de implementación de Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). También puede de <a href="https://aka.ms/planforwin10deployment" target="_blank">planeación de la implementación de Windows 10</a> en su propio.

Puede obtener más información acerca de Windows 10 con estos artículos:

- [Página del producto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Implementación y actualización de Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Las características y servicios adicionales
Como parte de la implementación de Enterprise del 10 de Windows, puede agregar estos servicios adicionales y características.

### <a name="windows-analytics"></a>Windows Analytics

Windows utiliza datos de diagnóstico para proporcionar información enriquecido y posibles para ayudarle a obtener profundo entendimiento de eficacia operativa y el mantenimiento de dispositivos de Windows 10 en su entorno.

* Actualización de preparación - preparación de actualización le ayudará a mover a 10 de Windows y manténgase al día con las nuevas actualizaciones de característica de 10 de Windows. 
* Cumplimiento de normas de actualización: actualización cumplimiento está dirigido a la administración de TI que desea obtener una vista integral de todos sus dispositivos de Windows 10, sin requisitos de infraestructura adicional.
* Mantenimiento de dispositivo - puede usar mantenimiento de dispositivo detectar de forma proactiva y corregir los problemas que afecta para el usuario final.

Para obtener más información, vea [Información general sobre el análisis de Windows](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .

### <a name="windows-security"></a>Seguridad de Windows

10 de Windows proporciona características para ayudar a proteger contra amenazas, ayuda seguro de los dispositivos y ayuda en el control de acceso. Con Windows 10, obtenga las características críticas de seguridad que protegen su derecho de dispositivo desde el principio. Microsoft 365 E3 agrega las características de seguridad, como Windows Hello para la empresa, Control de la aplicación de Windows Defender y protección de la información de Windows. Con Microsoft 365 E5, obtendrá toda la protección de seguridad de Microsoft 365 E3 además de las características de seguridad basada en la nube y la protección de amenaza avanzada de Windows Defender. 

Para obtener más información acerca de las características de seguridad que se obtienen con Windows 10 Enterprise y get encontrará información sobre cómo implementar, administrar, configurar y solucionar problemas de tres características clave ecurity, vea [paso 5: características de seguridad de la implementación de Windows 10 Enterprise](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Para desplegar dentro de Microsoft y obtenga información sobre cómo la compañía planeado para, implementa y va a administrar las actualizaciones para Windows 10, vea:

- [Preparing your organization for a seamless Windows 10 deployment (Preparar la organización para una implementación perfecta de Windows 10)](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Adopting Windows as a service at Microsoft (Adoptar Windows como servicio en Microsoft)](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Deploying Windows 10 at Microsoft as an in-place upgrade (Implementar Windows 10 en Microsoft como una actualización local)](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implementing strong user authentication with Windows Hello for Business (Implementar la autenticación de usuario segura con Windows Hello para empresas)](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Windows 10 deployment: tips and tricks from Microsoft IT (Implementación de Windows 10: sugerencias y trucos de TI de Microsoft)](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (vídeo)
- [Windows Defender ATP helps detect sophisticated threats (Windows Defender ATP le ayuda a detectar sofisticadas amenazas)](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Securing the modern enterprise with Windows Defender and Windows Defender ATP (Asegurando la empresa moderna con Windows Defender y ATP de Windows Defender)](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (vídeo)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Cómo Contoso hizo Microsoft 365 Enterprise

Vea cómo la empresa Contoso, una empresarial multinacional ficticia pero representativo, [implementado Windows 10 Enterprise](contoso-win10.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Prepare la organización para Windows 10 Enterprise](windows10-prepare-your-org.md) |
