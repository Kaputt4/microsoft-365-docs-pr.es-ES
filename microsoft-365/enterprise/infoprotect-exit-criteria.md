---
title: Criterios de salida de infraestructura de protección de información
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examine los criterios para la infraestructura y los servicios basados en la protección de información a fin de asegurarse de que su configuración cumple los requisitos de Microsoft 365 Enterprise.
ms.openlocfilehash: f4896baeb4c18fc1eabac10b15f3ad8e150ab260
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370137"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Criterios de salida de infraestructura de protección de información

![Fase 6: Protección de la información](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Asegúrese de que su infraestructura de protección de información cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obligatorio: se han definido los niveles de protección de información y seguridad de su organización

Ha planeado y determinado los niveles de seguridad que necesita su organización. Estos niveles definen un nivel mínimo de seguridad y niveles adicionales para la información cada vez más confidencial y su seguridad de datos necesaria.

Como mínimo, usa tres niveles de seguridad:

- Línea base
- Confidencial
- Extremadamente regulado

Si es necesario, el [Paso 1](infoprotect-define-sec-infoprotect-levels.md) puede resultarle útil para cumplir este requisito. 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obligatorio: se ha configurado una mayor seguridad para Microsoft 365

Ha configurado los siguientes valores para [mayor seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Directivas de administración de amenazas en el Centro de seguridad de Microsoft 365
- Configuración adicional de todo el espacio empresarial de Exchange Online
- Directivas de uso compartido aplicables a todo en el espacio empresarial en el centro de administración de SharePoint Online
- Configuración de Azure Active Directory (Azure AD)

También ha [habilitado la Protección contra amenazas avanzada (ATP) de Office 365 para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Si es necesario, el [paso 3](infoprotect-configure-increased-security-office-365.md) puede ayudarle a cumplir este requisito. 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Opcional: se ha configurado la clasificación en el entorno

Ha trabajado con sus equipos legales y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para el gobierno de datos y las directivas de seguridad de su organización. 

Dichas directivas se corresponden con la configuración y la implementación de:

- Tipos de datos confidenciales
- Etiquetas de retención
- Etiquetas de confidencialidad
- Etiquetas de Azure Information Protection

Si es necesario, el [paso 2](infoprotect-configure-classification.md) puede ayudarle a cumplir este requisito. 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Opcional: Windows Information Protection está implementado en su entorno

Los dispositivos Windows 10 Enterprise inscritos tienen una directiva de Intune implementada y aplicada que determina:

- Qué aplicaciones proteger.
- El nivel de protección.
- Dónde se extiende la protección.

Si es necesario, el [Paso 4](infoprotect-deploy-windows-information-protection.md) puede ayudarle a cumplir este requisito. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>Opcional: Prevención de pérdida de datos (DLP) de Office 365 está implementada

Tiene analizado, probar y, a continuación, implementan el conjunto de directivas DLP, con las ubicaciones y reglas con condiciones y acciones, que su organización necesita para proteger los clientes y otros tipos de datos privados y se ajusten a normativas regionales y del sector y requisitos.

El personal de cumplimiento y seguridad de datos usa el panel de seguridad y cumplimiento de Office 365 para supervisar incidentes de DLP.

Si es necesario, el [Paso 5](infoprotect-data-loss-prevention.md) puede resultarle útil para cumplir este requisito. 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>Opcional: El cifrado del correo electrónico está configurado:

Configuró la siguiente codificación de correo electrónico necesaria para su organización:

|||
|:-------|:-----|
| **Método de cifrado** | **Para el correo electrónico enviado** |
| [Cifrado de mensajes de Office 365 (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | Fuera de su organización con cifrado |
| [Information Rights Management (IRM)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | Con cifrado y permisos |
| [Extensiones seguras multipropósito de correo electrónico en Internet (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | Tanto con el cifrado como las firmas digitales que usan la criptografía de clave pública |
|||

Si es necesario, el [Paso 6](infoprotect-email-encryption.md) puede ayudarle a cumplir este requisito.

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Opcional: se ha configurado la administración del acceso con privilegios para Office 365

Ha usado la información en el tema [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (Configuración de la administración del acceso con privilegios en Office 365) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en su organización. Ha configurado estas directivas y el acceso Just-in-time está habilitado para el acceso a la información confidencial o el acceso a la configuración crítica.

Si es necesario, el [paso 7](infoprotect-configure-privileged-access-management.md) puede ayudarle a cumplir este requisito. 

## <a name="results-and-next-steps"></a>Resultados y siguientes pasos

Su infraestructura de protección de información para Microsoft 365 Enterprise utiliza niveles de seguridad definidos, seguridad ampliada de Office 365, clasificación con etiquetas y tipos de datos confidenciales, Windows Information Protection, Prevención de pérdida de datos, cifrado del correo electrónico y administración del acceso con privilegios.

Si está siguiendo la implementación de punto a punto de Microsoft 365 Enterprise, ya puede hacer que las [cargas de trabajo y escenarios](deploy-workloads.md) aprovechen todas las características y configuración de la infraestructura de base.
