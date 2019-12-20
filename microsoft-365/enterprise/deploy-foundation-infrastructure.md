---
title: Infraestructura básica de Microsoft 365 para empresas
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda las fases principales para implementar la infraestructura básica de Microsoft 365 para empresas en su organización, también conocida como la implementación principal.
ms.openlocfilehash: 78bfaf64fc247a88b30df4f2cf2a7f8b962dfdb6
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801965"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure"></a>Infraestructura básica de Microsoft 365 para empresas

Si está realizando la implementación de un extremo a otro de Microsoft 365 para empresas, debe crear primero una base firme en la que las aplicaciones y servicios puedan desbloquear la creatividad y el trabajo en equipo en un entorno seguro. Esta base a veces se conoce como la *implementación principal*.

Para una ruta de acceso de un extremo a otro definida para implementación, puede usar estas fases para planear e implementar la infraestructura básica de Microsoft 365 para empresas:

| | Fase | Resultados |
|:-------|:-----|:-----|
|![Fase 1: Redes](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[Fase 1: Redes](networking-infrastructure.md)| La red está optimizada para obtener acceso a los servicios en la nube de Microsoft 365. |
|![Fase 2: Identidad](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[Fase 2: Identidad](identity-infrastructure.md)| Las cuentas de administrador están protegidas, los usuarios y grupos se sincronizan y la autenticación de usuario es sólida. |
|![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[Fase 3: Windows 10 Enterprise](windows10-infrastructure.md)| Los equipos con Windows existentes pueden actualizar a Windows 10 Enterprise y los nuevos dispositivos se instalan con Windows 10 Enterprise. |
|![Fase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md)| Los usuarios existentes de Microsoft Office pueden actualizar a Office 365 ProPlus. |
|![Fase 5: Administración de dispositivos móviles](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[Fase 5: Administración de dispositivos móviles](mobility-infrastructure.md)| Se pueden inscribir y administrar los dispositivos. |
|![Fase 6: Protección de la información](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[Fase 6: Protección de la información](infoprotect-infrastructure.md)| Las características de seguridad de Office 365 están habilitadas y sus etiquetas y políticas están listas para proteger documentos y correo electrónico. |

Las fases comienzan por lo más fundamental (redes e identidad) y después crean capas de configuración de infraestructura y grupos para:

- Instalar la versión más actualizada y segura de Windows en sus dispositivos y manténgalo al día.
- Instalar la versión más reciente de Microsoft Office en sus dispositivos y manténgala al día. 
- Administre los dispositivos de su organización y el acceso a las aplicaciones.
- Proteger la información en los dispositivos y en la nube.

Pero tiene la posibilidad de configurar e implementar las fases o los pasos en fases para que se ajusten a sus recursos de TI y a sus necesidades empresariales.

- **Si tiene una organización más pequeña o reciente**, siga las fases según sea necesario para crear la infraestructura metódicamente. Para una implementación simplificada para no empresas, haga clic [aquí](deploy-foundation-infrastructure-non-enterprises.md).

-  **Si tiene una organización empresarial**,vea las fases como capas de infraestructura de TI en lugar de una ruta definida, y determine la mejor forma de cumplir los requisitos de cada capa en toda la organización.

Al final de cada fase, debe examinar *los criterios*de salida, en los que se incluyen las condiciones necesarias que debe cumplir y las condiciones opcionales que se deben considerar. Los criterios de salida para cada fase garantizan que su infraestructura local y en la nube, y la configuración de un extremo al otro resultante, cumplan los requisitos para una implementación de Microsoft 365 para empresas.

Para ver cómo se estructura el contenido, vea este breve vídeo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

Esta es la infraestructura básica en la guía general de implementación de Microsoft 365 para empresas:

![La infraestructura básica en la guía general de implementación de Microsoft 365 para empresas:](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a>A simple vista

El [póster de infraestructura básica de Microsoft 365 para empresas](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf) es una ubicación central para que la pueda ver, en cada fase:

- Objetivos generales de la fase para administradores y usuarios
- Los servicios, características y herramientas
- Las decisiones clave de diseño para planear
- Los resultados de la configuración
- El proceso para incorporar a un nuevo usuario
- Cómo supervisar y actualizar

[![Imagen para el póster de la infraestructura básica de Microsoft 365 para empresas](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)

Para descargar una copia del póster, haga clic [aquí](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).


## <a name="infrastructure-configuration-vs-user-rollout"></a>Configuración de la infraestructura frente a la inscripción de usuarios

La infraestructura de base es un conjunto de software y servicios configurados que permiten aprovechar toda la gama de funcionalidades y protecciones que ofrece Microsoft 365 Enterprise para empresas. El objetivo de la implementación de un extremo a otro es que esta infraestructura se aplique a todos los usuarios y sus dispositivos con Windows. 

Pero es importante que tenga en cuenta que la infraestructura básica de Microsoft 365 para empresas es independiente de la implementación de software y servicios para los usuarios. ***Puede configurar las capas de la infraestructura base sin tener que implementar esas capas para todos los usuarios.***

Es posible configurar y probar los elementos de la infraestructura de base antes de la implementación de esos elementos para los usuarios de las oficinas, regiones y divisiones de su organización.

Por ejemplo, puede crear la configuración de:

| Fase | Resultados |
|:-------|:-----|
| Identidad | Sincronización de cuentas y grupos para las directivas de acceso condicional basado en la identidad. |
| Windows 10 Enterprise | Grupos para actualizar automáticamente los equipos con Windows 7 o Windows 8.1 a Windows 10 Enterprise. |
| Office 365 ProPlus | Grupos para implementar automáticamente Office 365 ProPlus para usuarios con Office 2010, Office 2013 u Office 2016. |
| Administración de dispositivos móviles | Grupos para la inscripción de dispositivos y directivas de acceso condicional basado en el dispositivo. |
| Protección de la información | Grupos de etiquetas de confidencialidad de Office 365. |

Cuando se haya preparado para implementar elementos de esta infraestructura para los usuarios, usted:

| Fase | Acción de implementación |
|:-------|:-----|
| Identidad | Agregará cuentas de usuario a los grupos para las directivas de acceso condicional basado en la identidad. |
| Windows 10 Enterprise | Agregará cuentas a los grupos para implementar automáticamente Windows 10 Enterprise para los usuarios con Windows 7 o Windows 8.1. |
| Office 365 ProPlus | Agregará cuentas de usuario a los grupos para implementar automáticamente Office 365 ProPlus para usuarios con Office 2010, Office 2013 u Office 2016. |
| Administración de dispositivos móviles | Agregará cuentas a los grupos para la inscripción de dispositivos y directivas de acceso condicional basado en el dispositivo. |
| Protección de la información | Agregue cuentas de usuario a los grupos para las etiquetas de sensibilidad. |

Cuando las fases o los elementos de la infraestructura de base se hayan completado y probado, puede implementar software instalado, como Windows 10 Enterprise y Office 365 ProPlus, así como protecciones y servicios basados en la nube, como la inscripción de dispositivo y las directivas de acceso condicional, para los usuarios de la manera que mejor se adapte a sus objetivos empresariales y recursos de TI.

## <a name="deployment-and-project-management-strategies"></a>Estrategias de administración de proyectos y de implementación

Para darle algunas ideas sobre cómo enfocar la administración de proyectos de las distintas fases de la infraestructura de base para los usuarios piloto y el resto de su organización, vea [Estrategias de implementación de la infraestructura base de Microsoft 365 Enterprise](deployment-strategies-microsoft-365-enterprise.md).

## <a name="deployment-for-non-enterprises"></a>Implementación para no empresas

Si su organización es más pequeña y Microsoft 365 empresarial no es adecuado para usted, consulte [implementación para empresas](deploy-foundation-infrastructure-non-enterprises.md) que no tengan un método de implementación simplificado.


## <a name="next-step"></a>Siguiente paso

| Donde estoy | Donde necesito ir |
|:-------|:-----|
| Tengo la infraestructura existente para Office 365, Enterprise Mobility + Security (EMS) o Windows 10 Enterprise | Comience con [la implementación de la infraestructura existente](deploy-with-existing-infrastructure.md), que le guiará a través del criterio de salida para cada fase. |
| Estoy iniciando desde cero como empresa | Empiece su recorrido de implementación de un extremo a otro con [Fase 1: Networking](networking-infrastructure.md). |
| Estoy empezando desde cero como no empresa | Empiece su recorrido de implementación de un extremo a otro con [Implementación para no empresas](deploy-foundation-infrastructure-non-enterprises.md). |
