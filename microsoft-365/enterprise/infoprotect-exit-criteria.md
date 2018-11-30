---
title: Criterios de salida de infraestructura de protección de información
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Examine los criterios para la infraestructura y los servicios basados en la protección de información a fin de asegurarse de que su configuración cumple los requisitos de Microsoft 365 Enterprise.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871687"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Criterios de salida de infraestructura de protección de información

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Antes de que complete su infraestructura base, asegúrese de que su infraestructura de protección de información cumple estas condiciones. 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obligatorio: se han definido los niveles de protección de información y seguridad de su organización

Ha planeado y determinado los niveles de seguridad que necesita su organización. Estos niveles definen un nivel mínimo de seguridad y niveles adicionales para la información cada vez más confidencial y su seguridad de datos necesaria.

Como mínimo, usa tres niveles de seguridad:

- Línea base
- Confidencial
- Extremadamente regulado

Si es necesario, el [paso 1](infoprotect-define-sec-infoprotect-levels.md) puede ayudarle a cumplir este requisito. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>Obligatorio: se ha configurado una mayor seguridad para Office 365

Ha configurado las siguientes opciones para obtener una mayor seguridad en función de la información disponible en [Configurar al inquilino de Office 365 para una mayor seguridad](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):

- Directivas de administración de amenazas en el Centro de seguridad y cumplimiento de Office 365
- Configuración adicional de todo el espacio empresarial de Exchange Online
- Directivas de uso compartidas de todo el espacio empresarial en el Centro de administración de SharePoint
- Configuración en Azure Active Directory

También ha [habilitado la Protección contra amenazas avanzada de Office 365 (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Si es necesario, el [paso 3](infoprotect-configure-increased-security-office-365.md) puede ayudarle a cumplir este requisito. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Opcional: se ha configurado la clasificación en el entorno

Ha trabajado con sus equipos legales y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para los datos de su organización, que incluye lo siguiente:

- Tipos de datos confidenciales
- Etiquetas de Office 365
- Etiquetas de Azure Information Protection

Si es necesario, el [paso 2](infoprotect-configure-classification.md) puede ayudarle a cumplir este requisito. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Opcional: se ha configurado la administración del acceso con privilegios para Office 365

Ha usado la información del artículo [Configurar la administración del acceso con privilegios de Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en la organización de Office 365. Ha configurado estas directivas y el acceso puntual está habilitado para el acceso a los datos confidenciales o a las opciones de configuración críticas.

Si es necesario, el [paso 4](infoprotect-configure-privileged-access-management.md) puede ayudarle a cumplir este requisito. 

## <a name="next-step"></a>Paso siguiente

Ya está preparado para implementar [cargas de trabajo y escenarios](deploy-workloads.md), como Microsoft Teams y Exchange Online, que se ejecutan en función de la infraestructura base de Microsoft 365 Enterprise.
