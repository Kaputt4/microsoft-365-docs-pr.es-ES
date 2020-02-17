---
title: Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure Azure AD Identity Protection y analice las cuentas actuales en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068497"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise

*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*

La protección de identidad de Azure Active Directory (Azure AD) le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automáticas e investigar incidentes. En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.

Hay dos fases para la configuración de Azure AD Identity Protection en su entorno de prueba de Microsoft 365 Enterprise:

1. Crear el entorno de pruebas de Microsoft 365 Enterprise.
2. Use Azure AD Identity Protection.

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise

Si solo quiere probar Azure AD Identity Protection de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: usar la protección de identidad de Azure AD

1. Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global de su entorno de prueba de Microsoft 365 Enterprise.
2. En Azure portal, escriba **protección de identidad** en el cuadro de búsqueda y, a continuación, haga clic en **Azure ad Identity Protection**.
3. En la hoja **protección de identidad: información general** , haga clic en cada uno de los informes para ver qué son los informes.
4. En **notificar**, haga clic en **alertas de usuarios en riesgo detectado**.
5. En el panel de **alertas usuarios en riesgo detectados** , seleccione **medio**.
6. Para **los mensajes de correo electrónico se envían a los siguientes usuarios**, haga clic en **incluido** y compruebe que la cuenta de administrador global está en la lista de miembros seleccionados.
7. Haga clic en **Guardar **.

Haga clic en las diferentes directivas en **proteger** para ver cómo configurarlas. Si crea y activa una directiva, asegúrese de que no bloquee el acceso por un ámbito de condiciones demasiado amplio o de que no pueda iniciar sesión, ni siquiera como administrador global.

Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Consulte el paso [proteger contra credenciales en peligro](identity-secure-user-sign-ins.md#identity-ident-prot) en la fase de identidad para obtener información y vínculos para implementar Azure ad Identity Protection en producción.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
