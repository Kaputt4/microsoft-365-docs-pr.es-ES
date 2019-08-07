---
title: Infraestructura básica de Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda las fases principales para implementar la infraestructura básica de Microsoft 365 Enterprise en su organización, también conocida como la implementación principal.
ms.openlocfilehash: 0c683f771609c847556f82fe84a17dad13ee34d4
ms.sourcegitcommit: d9b462e035416bfa4b3d42467902c75859c55381
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "36055031"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a>Infraestructura básica de Microsoft 365 Enterprise

Si realiza la implementación de un extremo a otro de Microsoft 365 Enterprise por su cuenta, primero debe crear una base firme en la que los servicios y aplicaciones impulsen la creatividad y el trabajo en equipo en un entorno seguro. Esta base a veces se conoce como la *implementación principal*.

Para una ruta de implementación de un extremo a otro definida, puede usar estas fases para planear e implementar la infraestructura de base de Microsoft 365 Enterprise:

| | Fase | Resultados |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[Fase 1: Redes](networking-infrastructure.md)| La red está optimizada para obtener acceso a los servicios en la nube de Microsoft 365. |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[Fase 2: Identidad](identity-infrastructure.md)| Las cuentas de administrador están protegidas, los usuarios y grupos se sincronizan y la autenticación de usuario es sólida. |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[Fase 3: Windows 10 Enterprise](windows10-infrastructure.md)| Los equipos con Windows existentes pueden actualizar a Windows 10 Enterprise y los nuevos dispositivos se instalan con Windows 10 Enterprise. |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md)| Los usuarios existentes de Microsoft Office pueden actualizar a Office 365 ProPlus. |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[Fase 5: Administración de dispositivos móviles](mobility-infrastructure.md)| Se pueden inscribir y administrar los dispositivos. |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[Fase 6: Protección de la información](infoprotect-infrastructure.md)| Las etiquetas están preparadas para proteger documentos y se habilitan las características de seguridad de Office 365. |

Las fases comienzan por lo más fundamental (redes e identidad) y después crean capas de configuración de infraestructura y grupos para:

- Instalar la versión más actualizada y segura de Windows en sus dispositivos.
- Instalar la versión más reciente de Microsoft Office en sus dispositivos. 
- Administrar los dispositivos de su organización.
- Proteger la información en los dispositivos y en la nube.

Pero tiene la posibilidad de configurar e implementar las fases o los pasos en fases para que se ajusten a sus recursos de TI y a sus necesidades empresariales.

- **Si tiene una organización más pequeña o reciente**, siga las fases según sea necesario para crear la infraestructura metódicamente.

-  **Si tiene una organización empresarial**,vea las fases como capas de infraestructura de TI en lugar de una ruta definida, y determine la mejor forma de cumplir los requisitos de cada capa en toda la organización.

Al final de cada fase, debería examinar sus criterios de salida, que incluyen las condiciones necesarias y opcionales que tener en cuenta. Los criterios de salida para cada fase garantizan que su infraestructura local y en la nube y la configuración de un extremo al otro resultante cumplen los requisitos para una implementación de Microsoft 365 Enterprise.

Para ver cómo se estructura el contenido, vea este breve vídeo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

Esta es la infraestructura de base de la guía de implementación de Microsoft 365 Enterprise general:

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a>A simple vista

El [póste de Microsoft 365 Enterprise Foundation Infrastructure ](http://aka.ms/m365efoundinfraposter) es una ubicación central para que lo vean, en cada fase:

- Objetivos generales de la fase para administradores y usuarios
- Los servicios, características y herramientas
- Las decisiones clave de diseño para planear
- Los resultados de la configuración
- El proceso para incorporar a un nuevo usuario
- Cómo supervisar y actualizar

![](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)

Para descargar una copia del póster, haga clic [aquí](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).


## <a name="infrastructure-configuration-vs-user-rollout"></a>Configuración de la infraestructura frente a la inscripción de usuarios

La infraestructura de base es un conjunto de software y servicios configurados que permiten aprovechar toda la gama de funcionalidades y protecciones que ofrece Microsoft 365 Enterprise al combinarse para un usuario. El objetivo de la implementación de un extremo a otro es que esta infraestructura se aplique a todos los usuarios y sus dispositivos con Windows. 

Pero es importante que tenga en cuenta que la infraestructura de base de Microsoft 365 Enterprise es independiente de la implementación de software y servicios para los usuarios. ***Puede configurar las capas de la infraestructura base sin tener que implementar esas capas para todos los usuarios.***

Por lo tanto, es posible configurar y probar los elementos de la infraestructura de base antes de la implementación de esos elementos para los usuarios de las oficinas, regiones y divisiones de su organización.

Por ejemplo, puede crear la configuración de:

| Fase | Resultados |
|:-------|:-----|
| Identidad | Sincronización de cuentas y grupos para las directivas de acceso condicional basado en la identidad. |
| Windows 10 Enterprise | Grupos para actualizar automáticamente los equipos con Windows 7 o Windows 8.1 a Windows 10 Enterprise. |
| Office 365 ProPlus | Grupos para implementar automáticamente Office 365 ProPlus para usuarios con Office 2010, Office 2013 u Office 2016. |
| Administración de dispositivos móviles | Grupos para la inscripción de dispositivos y directivas de acceso condicional basado en el dispositivo. |
| Protección de la información | Etiquetas y grupos de sensibilidad para la protección de información de Office 365 y de Azure. |

Cuando se haya preparado para implementar elementos de esta infraestructura para los usuarios, usted:

| Fase | Acción de implementación |
|:-------|:-----|
| Identidad | Agregará cuentas de usuario a los grupos para las directivas de acceso condicional basado en la identidad. |
| Windows 10 Enterprise | Agregará cuentas a los grupos para implementar automáticamente Windows 10 Enterprise para los usuarios con Windows 7 o Windows 8.1. |
| Office 365 ProPlus | Agregará cuentas de usuario a los grupos para implementar automáticamente Office 365 ProPlus para usuarios con Office 2010, Office 2013 u Office 2016. |
| Administración de dispositivos móviles | Agregará cuentas a los grupos para la inscripción de dispositivos y directivas de acceso condicional basado en el dispositivo. |
| Protección de la información | Agregará cuentas de usuario a los grupos para obtener etiquetas de protección de la información. |

Cuando la infraestructura de base se haya completado y probado, puede implementar software instalado, como Windows 10 Enterprise y Office 365 ProPlus, así como protecciones y servicios basados en la nube, como la inscripción de dispositivo y las directivas de acceso condicional, para los usuarios de la manera que mejor se adapte a sus objetivos empresariales y recursos de TI.

## <a name="deployment-and-project-management-strategies"></a>Estrategias de administración de proyectos y de implementación

Para darle algunas ideas sobre cómo enfocar la administración de proyectos de las distintas fases de la infraestructura de base para los usuarios piloto y el resto de su organización, vea [Estrategias de implementación de la infraestructura base de Microsoft 365 Enterprise](deployment-strategies-microsoft-365-enterprise.md).

## <a name="deployment-for-non-enterprises"></a>Implementación para no empresas

Si su organización es más pequeña y Microsoft 365 Business no es adecuada para usted, consulte[, Implementación para no empresas](deploy-foundation-infrastructure-non-enterprises.md).


## <a name="next-step"></a>Paso siguiente


| Donde estoy | Donde necesito ir |
|:-------|:-----|
| Tengo la infraestructura existente para Office 365, Enterprise Mobility + Security (EMS) o Windows 10 Enterprise | Comience con [la implementación de la infraestructura existente](deploy-with-existing-infrastructure.md), que le guiará a través del criterio de salida para cada fase. |
| Estoy empezando desde cero como empresa | Empiece su recorrido de implementación de un extremo a otro con [Fase 1: Networking](networking-infrastructure.md). |
| Estoy empezando desde cero como no empresa | Empiece su recorrido de implementación de un extremo a otro con [Implementación para no empresas](deploy-foundation-infrastructure-non-enterprises.md). |
