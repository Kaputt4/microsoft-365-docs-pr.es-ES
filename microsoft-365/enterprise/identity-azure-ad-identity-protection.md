---
title: 'Paso 6: Proteger contra credenciales en peligro'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871803"
---
# <a name="step-6-protect-against-credential-compromise"></a>Paso 6: Proteger contra credenciales en peligro

*Este paso es opcional y solo es válido para la versión E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, obtendrá información sobre cómo configurar directivas para proteger contra credenciales en peligro, donde un atacante determina el nombre de la cuenta y la contraseña de un usuario para obtener acceso a los servicios y datos en la nube de una organización. Azure AD Identity Protection ofrece distintas formas de impedir que un atacante se mueva lateralmente por sus cuentas y grupos y, en consecuencia, impedir que obtenga acceso a los datos más valiosos.

Con Azure AD Identity Protection, puede:

|||
|:---------|:---------|
|Determinar y corregir posibles vulnerabilidades en las identidades de su organización|Azure AD usa aprendizaje automático para detectar anomalías y actividades sospechosas, como inicios de sesión y actividades posteriores al inicio de sesión. Con estos datos, Identity Protection genera informes y alertas que le permiten evaluar los problemas y tomar medidas.|
|Detectar acciones sospechosas relacionadas con las identidades de su organización y responder a ellas automáticamente|Puede configurar directivas basadas en riesgos que responden automáticamente a los problemas encontrados cuando se alcanza un nivel de riesgo especificado. Estas directivas, además de otros controles de acceso condicional proporcionados por Azure Active Directory y Enterprise Mobility + Security (EMS), pueden automáticamente impedir el acceso o realizar acciones correctivas, como activar restablecimientos de contraseña y exigir la autenticación multifactor para los inicios de sesión posteriores.|
|Investigar incidentes sospechosos y solucionarlos con acciones administrativas|Puede investigar eventos de riesgo con información sobre el incidente de seguridad. Hay disponibles flujos de trabajo básicos para realizar un seguimiento de las investigaciones e iniciar acciones de corrección, como restablecimientos de contraseña.|

Vea [más información sobre Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Vea los [pasos para habilitar Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

El resultado de este paso es que habilitó Azure AD Identity Protection y ahora lo usa para:

- Solucionar posibles vulnerabilidades de identidad.
- Detectar posibles intentos de uso ilícito de credenciales.
- Investigar y solucionar incidentes de identidad sospechosos y continuados.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-ident-prot) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [Sincronización de directorios](identity-azure-ad-connect.md) |


