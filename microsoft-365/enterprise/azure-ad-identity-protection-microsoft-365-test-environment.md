---
title: Azure AD Identity Protection para su entorno de prueba de Microsoft 365 para empresas
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
description: Configure Azure AD Identity Protection y analice las cuentas actuales en su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487713"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection para su entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*

Puede usar Azure Active Directory (Azure AD) Identity Protection para detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automatizadas e investigar incidentes. En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.

La configuración de Azure AD Identity Protection en el entorno de prueba de Microsoft 365 para empresas consta de dos fases:

- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Usar Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si solo desea probar Azure AD Identity Protection de forma ligera con los requisitos mínimos, siga las instrucciones de [la configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> La prueba de Azure AD Identity Protection no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Usar Azure AD Identity Protection

1. Abra una instancia privada del explorador e inicie sesión en Azure Portal con la cuenta de administrador global de su entorno de prueba de [https://portal.azure.com](https://portal.azure.com) Microsoft 365 para empresas.
2. En Azure Portal, escriba **Identity Protection** en el cuadro de búsqueda y, a continuación, seleccione Azure AD **Identity Protection.**
3. En la **hoja Identity Protection - Información** general, seleccione cada informe para ver lo que está informando.
4. En **Notificar,** seleccione **Usuarios en riesgo alertas detectadas.**
5. En el panel **De alertas detectadas de usuarios en** riesgo, seleccione **Medio**.
6. Para **los correos electrónicos se envían a los siguientes usuarios,** **seleccione** Incluido y compruebe que su cuenta de administrador global está en la lista de miembros seleccionados.
7. Seleccione **Guardar**.

En **Proteger,** seleccione varias directivas para ver cómo configurarlas. Si crea y activa una directiva, asegúrese de que no está bloqueando el acceso de todos los usuarios o es posible que no pueda iniciar sesión. Para evitarlo, excluya cuentas de usuario específicas, como administradores globales.

Para más pruebas y experimentación, consulta [Simulación de eventos de riesgo.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
