---
title: 'Fase 4: Office 365 ProPlus'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Pasos para implementar la infraestructura de Office 365 ProPlus para Microsoft 365 Enterprise.
ms.openlocfilehash: 2b3ac311863249720a2dc1fba00ead9ebf6ac8e5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066460"
---
# <a name="phase-4-office-365-proplus"></a>Fase 4: Office 365 ProPlus

![Fase 4: Office 365 ProPlus](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise y Microsoft 365 Educación*

Microsoft 365 Enterprise incluye el Office 365 ProPlus, la versión de suscripción de Office. Al igual que Office 2019, Office 365 ProPlus incluye todas las aplicaciones de Office, y esas aplicaciones se instalan directamente en los dispositivos del cliente. A diferencia de Office 2019, Office 365 ProPlus se actualiza regularmente con nuevas características y tiene un modelo de licencia basado en el usuario que permite a los usuarios instalar Office en varios dispositivos. Para obtener más información, consulte[ Acerca de Office 365 ProPlus en la empresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

En esta fase, implementará Office 365 ProPlus en dispositivos cliente como parte de Microsoft 365 Enterprise. Además de esta guía, le recomendamos que use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) para ayudarle con la implementación. 

Si ya tiene Office 365 ProPlus implementado, consulte los [criterios de salida](office365proplus-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias para Microsoft 365 Enterprise.

>[!Note]
>Para implementar Windows 10 Enterprise y Office 365 ProPlus juntos consulte el [Centro de implementación de escritorio](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Paso 1: Evaluar el entorno

Antes de implementar Office 365 ProPlus, siga las instrucciones de [Evaluar el entorno y los requisitos para implementar Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Esta evaluación incluye los requisitos del sistema, detalles de los dispositivos cliente (como arquitecturas e idiomas necesarios), requisitos de licencia, capacidad de red y compatibilidad de aplicaciones. Al completar la evaluación, podrá tomar decisiones clave como parte de la planeación de la implementación.

## <a name="step-2-plan-your-deployment"></a>Paso 2: Planear la implementación

Después de evaluar el entorno, siga las instrucciones de [Planear la implementación de Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) para crear un plan de implementación. Este plan incluye las decisiones siguientes: 

- Cómo implementar Office, como qué herramienta usar (por ejemplo, Microsoft Endpoint Configuration Manager o la herramienta de implementación de Office) y desde dónde instalar Office
- Cómo administrar las actualizaciones de Office.
- Qué canales de actualización usar (los canales de actualización de Office controlan la frecuencia con la que los usuarios reciben actualizaciones de características para las aplicaciones de Office).
- Los grupos de implementación y los paquetes de instalación de Office que quiera usar, incluidas qué aplicaciones de Office e idiomas se deben instalar para los usuarios.

El [artículo de planeación](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) incluye los procedimientos recomendados para todas estas opciones, como administrar la implementación, administrar las actualizaciones, definir los paquetes de instalación y crear los grupos de implementación. 

## <a name="step-3-deploy"></a>Paso 3: Implementar

En función de su plan de implementación, elija cómo desea realizar la implementación:

- **[Implementar Office 365 ProPlus con Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** administre la implementación con Configuration Manager, y descargar e implementar Office desde los puntos de distribución de la red

- **[Implementar Office 365 ProPlus con la ODT desde la nube](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** administre la implementación con la ODT e instale Office en dispositivos cliente directamente desde la CDN de Office.
 
- **[Instale Office 365 ProPlus desde el portal de Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** administre la implementación desde el portal de Office y haga que los usuarios instalen Office en los dispositivos cliente directamente desde el portal.

Muchas organizaciones usarán una combinación de estas opciones para distintos usuarios. Por ejemplo, una organización puede usar Configuration Manager para implementar Office en la mayoría de los usuarios, pero habilitar la instalación propia para un pequeño grupo de trabajadores que no se suelen conectar a la red interna. 

Si su organización usa Configuration Manager, le recomendamos actualizar a la rama actual y a la versión actual. Para obtener más información, vea [¿Qué rama de Configuration Manager debo utilizar?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Aprenda cómo los expertos en Microsoft están[implementando y gestionando las actualizaciones de Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Cómo Contoso hizo Microsoft 365 Enterprise

Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó Office 365 ProPlus](contoso-o365pp.md).

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Siguiente paso

[Criterios de salida de la infraestructura de Office 365 ProPlus](office365proplus-exit-criteria.md)
