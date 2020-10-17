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
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487713"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Puede usar Azure Active Directory (Azure AD) Identity Protection para detectar posibles vulnerabilidades que afecten a las identidades de su organización, configurar respuestas automáticas e investigar incidentes. En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.

La configuración de Azure AD Identity Protection en el entorno de prueba de Microsoft 365 para empresas implica dos fases:

- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: usar la protección de identidad de Azure AD](#phase-2-use-azure-ad-identity-protection)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar la protección de identidad de Azure AD de manera ligera con los requisitos mínimos, siga las instrucciones de [configuración de base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: usar la protección de identidad de Azure AD

1. Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global del entorno de prueba de Microsoft 365 para empresas.
2. En Azure portal, escriba **protección de identidad** en el cuadro de búsqueda y, a continuación, seleccione **Azure ad Identity Protection**.
3. En la hoja de la **información general** de la identidad, seleccione cada uno de los informes para ver su información.
4. En **notificar**, seleccione **usuarios en alertas de riesgo detectado**.
5. En el panel de **alertas usuarios en riesgo detectados** , seleccione **medio**.
6. Para **los mensajes de correo electrónico se envían a los siguientes usuarios**, seleccione **incluido** y compruebe que la cuenta de administrador global está en la lista de miembros seleccionados.
7. Seleccione **Guardar**.

En **proteger**, seleccione diversas directivas para ver cómo configurarlas. Si crea y activa una directiva, asegúrese de que no esté bloqueando el acceso de todos los usuarios o de que no pueda iniciar sesión. Para evitarlo, excluya las cuentas de usuario específicas, como los administradores globales.

Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Mapa de ruta de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
