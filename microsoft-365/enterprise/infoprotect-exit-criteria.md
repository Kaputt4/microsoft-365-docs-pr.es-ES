---
title: Criterios de salida de infraestructura de protección de información
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examine los criterios para la infraestructura y los servicios basados en la protección de información a fin de asegurarse de que su configuración cumple los requisitos de Microsoft 365 Enterprise.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283706"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Criterios de salida de infraestructura de protección de información

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Asegúrese de que su infraestructura de protección de información cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obligatorio: se han definido los niveles de protección de información y seguridad de su organización

Ha planeado y determinado los niveles de seguridad que necesita su organización. Estos niveles definen un nivel mínimo de seguridad y niveles adicionales para la información cada vez más confidencial y su seguridad de datos necesaria.

Como mínimo, usa tres niveles de seguridad:

- Línea base
- Confidencial
- Extremadamente regulado

Si es necesario, el [Paso 1](infoprotect-define-sec-infoprotect-levels.md) puede resultarle útil para cumplir este requisito. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obligatorio: se ha configurado una mayor seguridad para Microsoft 365

Ha configurado los siguientes valores para [mayor seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Directivas de administración de amenazas en el Centro de seguridad de Microsoft 365
- Configuración adicional de todo el espacio empresarial de Exchange Online
- Directivas de uso compartidas de todo el espacio empresarial en el Centro de administración de SharePoint
- Configuración de Azure Active Directory (Azure AD)

También ha [habilitado la Protección contra amenazas avanzada (ATP) de Office 365 para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/es-ES/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Si es necesario, el [paso 3](infoprotect-configure-increased-security-office-365.md) puede ayudarle a cumplir este requisito. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Opcional: se ha configurado la clasificación en el entorno

Ha trabajado con sus equipos legales y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para el gobierno de datos y las directivas de seguridad de su organización. 

Dichas directivas se corresponden con la configuración y la implementación de:

- Tipos de datos confidenciales
- Etiquetas de retención
- Etiquetas de confidencialidad
- Etiquetas de Azure Information Protection

Si es necesario, el [paso 2](infoprotect-configure-classification.md) puede ayudarle a cumplir este requisito. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Opcional: se ha configurado la administración del acceso con privilegios para Office 365

Ha usado la información en el tema [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (Configuración de la administración del acceso con privilegios en Office 365) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en su organización. Ha configurado estas directivas y el acceso Just-in-time está habilitado para el acceso a la información confidencial o el acceso a la configuración crítica.

Si es necesario, el [paso 4](infoprotect-configure-privileged-access-management.md) puede ayudarle a cumplir este requisito. 

## <a name="results-and-next-steps"></a>Resultados y siguientes pasos

La infraestructura de protección de información de Microsoft 365 Enterprise usa niveles de seguridad definidos, seguridad aumentada de Office 365, clasificación mediante etiquetas y tipos de datos confidenciales y administración de acceso privilegiado.

Si está siguiendo la implementación de punto a punto de Microsoft 365 Enterprise, ya puede hacer que las [cargas de trabajo y escenarios](deploy-workloads.md) aprovechen todas las características y configuración de la infraestructura de base.
