---
title: 'Fase 4: Aplicaciones de Microsoft 365 para empresas'
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
description: Pasos para implementar la infraestructura de Aplicaciones de Microsoft 365 para empresas para Microsoft 365 Enterprise.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011952"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Fase 4: Aplicaciones de Microsoft 365 para empresas

![Fase 4: Aplicaciones de Microsoft 365 para empresas](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise y Microsoft 365 Educación*

Microsoft 365 Enterprise incluye Aplicaciones de Microsoft 365 para empresas, la versión de suscripción de Office. Al igual que Office 2019, Aplicaciones de Microsoft 365 para empresas incluye todas las aplicaciones de Office, y esas aplicaciones se instalan directamente en los dispositivos del cliente. A diferencia de Office 2019, Aplicaciones de Microsoft 365 para empresas se actualiza regularmente con nuevas características y tiene un modelo de licencia basado en el usuario que permite a los usuarios instalar Office en varios dispositivos. Para obtener más información, consulte [Acerca de Aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).

En esta fase, implementará Aplicaciones de Microsoft 365 para empresas en dispositivos cliente como parte de Microsoft 365 Enterprise. Además de esta guía, le recomendamos que use [Microsoft FastTrack](https://fasttrack.microsoft.com/office) para ayudarle con la implementación. 

Si ya tiene Aplicaciones de Microsoft 365 para empresas implementado, consulte los [criterios de salida](office365proplus-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias para Microsoft 365 Enterprise.

>[!Note]
>Para implementar Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas juntos consulte el [Centro de implementación de escritorio](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Paso 1: Evaluar el entorno

Antes de implementar Aplicaciones de Microsoft 365 para empresas, siga las instrucciones de [Evaluar el entorno y los requisitos para implementar Aplicaciones de Microsoft 365](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). Esta evaluación incluye los requisitos del sistema, detalles de los dispositivos cliente (como arquitecturas e idiomas necesarios), requisitos de licencia, capacidad de red y compatibilidad de aplicaciones. Al completar la evaluación, podrá tomar decisiones clave como parte de la planeación de la implementación.

## <a name="step-2-plan-your-deployment"></a>Paso 2: Planear la implementación

Después de evaluar el entorno, siga las instrucciones de [Planear una implementación de Aplicaciones de Microsoft 365](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) para crear un plan de implementación. Este plan incluye las decisiones siguientes: 

- Cómo implementar Office, como qué herramienta usar (por ejemplo, Microsoft Endpoint Configuration Manager o la herramienta de implementación de Office) y desde dónde instalar Office
- Cómo administrar las actualizaciones de Office.
- Qué canales de actualización usar (los canales de actualización de Office controlan la frecuencia con la que los usuarios reciben actualizaciones de características para las aplicaciones de Office).
- Los grupos de implementación y los paquetes de instalación de Office que quiera usar, incluidas qué aplicaciones de Office e idiomas se deben instalar para los usuarios.

El [artículo de planeación](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) incluye los procedimientos recomendados para todas estas opciones, como administrar la implementación, administrar las actualizaciones, definir los paquetes de instalación y crear los grupos de implementación. 

## <a name="step-3-deploy"></a>Paso 3: Implementar

En función de su plan de implementación, elija cómo desea realizar la implementación:

- **[Implementar Aplicaciones de Microsoft 365 con Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** administre la implementación con Configuration Manager y descargue e implemente Office desde puntos de distribución de la red.

- **[Implementar Aplicaciones de Microsoft 365 desde la nube](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** administre la implementación con la ODT e instale Office en dispositivos cliente directamente desde la CDN de Office.
 
- **[Autoinstalación de Aplicaciones de Microsoft 365 para empresas desde el portal de Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** administre la implementación desde el portal de Office y haga que los usuarios instalen Office en los dispositivos cliente directamente desde el portal.

Muchas organizaciones usarán una combinación de estas opciones para distintos usuarios. Por ejemplo, una organización puede usar Configuration Manager para implementar Office en la mayoría de los usuarios, pero habilitar la instalación propia para un pequeño grupo de trabajadores que no se suelen conectar a la red interna. 

Si su organización usa Configuration Manager, le recomendamos actualizar a la rama actual y a la versión actual. Para obtener más información, vea [¿Qué rama de Configuration Manager debo utilizar?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Aprenda cómo los expertos en Microsoft están [implementando y gestionando las actualizaciones de Aplicaciones de Microsoft 365 para empresas](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Cómo Contoso hizo Microsoft 365 Enterprise

Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó Aplicaciones de Microsoft 365 para empresas](contoso-o365pp.md).

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de la infraestructura para las Aplicaciones de Microsoft 365 para empresas](office365proplus-exit-criteria.md)
