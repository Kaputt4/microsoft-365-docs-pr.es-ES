---
title: Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure Azure AD Identity Protection y analice las cuentas actuales en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: bc98ebbdd45e06481e2d95687fb4eb8c986533a3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673246"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise

*Esta guía del entorno de pruebas solo puede usarse en entornos de prueba de Microsoft 365 Enterprise.*

Azure AD Identity Protection le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automáticas e investigar incidentes. En este artículo se describe cómo habilitar la protección de identidad de Azure AD y ver el análisis de las cuentas del entorno de prueba.

Hay dos fases para la configuración de Azure AD Identity Protection en su entorno de prueba de Microsoft 365 Enterprise:

1. Crear el entorno de pruebas de Microsoft 365 Enterprise.
2. Habilite y use Azure AD Identity Protection.

![Guías del entorno de pruebas para la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise

Si solo quiere probar Azure AD Identity Protection de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Fase 2: habilitar y usar Azure AD Identity Protection

1. Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global de su entorno de prueba de Microsoft 365 Enterprise.
2. En Azure portal, haga clic en **todos los servicios > Marketplace**.
3. Escriba **Azure ad Identity Protection** y, a continuación, haga clic en él.
4. En la hoja **Introducción** , haga clic **en incorporada** en **configuración**, haga clic en **anclar a panel**y, a continuación, haga clic en **crear**.
5. En Azure portal, haga clic en **Azure ad Identity Protection** en el panel. 

   Debe ver un blade **de Azure ad Identity Protection-Overview** con un panel. En **vulnerabilidades**, observe que se ha determinado el número de cuentas de usuario sin registro de autenticación multifactor. Este número variará en función de las guías previas del laboratorio de pruebas de Microsoft 365 Enterprise que haya hecho.

6. Haga clic en las categorías para **investigar** para ver si hay algún usuario o evento que se haya detectado.

Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Consulte el paso [proteger contra credenciales en peligro](identity-secure-user-sign-ins.md#identity-ident-prot) en la fase de identidad para obtener información y vínculos para implementar Azure ad Identity Protection en producción.

## <a name="next-step"></a>Siguiente paso

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
