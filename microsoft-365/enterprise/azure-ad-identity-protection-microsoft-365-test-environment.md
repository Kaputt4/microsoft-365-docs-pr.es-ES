---
title: Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas
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
description: Configure Azure AD Identity Protection y analice las cuentas actuales en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694995"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

La protección de identidad de Azure Active Directory (Azure AD) le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automáticas e investigar incidentes. En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.

Hay dos fases para la configuración de Azure AD Identity Protection en el entorno de prueba de Microsoft 365 para empresas:

1. Cree el entorno de prueba de Microsoft 365 para empresas.
2. Use Azure AD Identity Protection.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar Azure AD Identity Protection de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: usar la protección de identidad de Azure AD

1. Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global del entorno de prueba de Microsoft 365 para empresas.
2. En Azure portal, escriba **protección de identidad** en el cuadro de búsqueda y, a continuación, haga clic en **Azure ad Identity Protection**.
3. En la hoja **protección de identidad: información general** , haga clic en cada uno de los informes para ver qué son los informes.
4. En **notificar**, haga clic en **alertas de usuarios en riesgo detectado**.
5. En el panel de **alertas usuarios en riesgo detectados** , seleccione **medio**.
6. Para **los mensajes de correo electrónico se envían a los siguientes usuarios**, haga clic en **incluido** y compruebe que la cuenta de administrador global está en la lista de miembros seleccionados.
7. Haga clic en **Guardar **.

Haga clic en las diferentes directivas en **proteger** para ver cómo configurarlas. Si crea y activa una directiva, asegúrese de que no bloquee el acceso por un ámbito de condiciones demasiado amplio o de que no pueda iniciar sesión, ni siquiera como administrador global.

Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Mapa de ruta de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
