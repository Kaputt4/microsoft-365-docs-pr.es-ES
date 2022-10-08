---
title: Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure Azure AD Identity Protection y analice las cuentas actuales en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: e60115623f63417175594e76f58fde616d2698b7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185675"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas

*Esta guía de laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

Puede usar Identity Protection de Azure Active Directory (Azure AD) para detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automatizadas e investigar incidentes. En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas de entorno de prueba.

La configuración de Azure AD Identity Protection en el entorno de prueba de Microsoft 365 para empresas implica dos fases:

- [Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Uso de Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para enterprise Test Lab Guide Stack (Pila de guía del laboratorio de pruebas empresariales).](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar Azure AD Identity Protection de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de Azure AD Identity Protection no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Uso de Azure AD Identity Protection

1. Abra una instancia privada del explorador e inicie sesión en el Azure Portal en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global del entorno de prueba de Microsoft 365 para empresas.
2. En el Azure Portal, escriba **identity protection** en el cuadro de búsqueda y, a continuación, seleccione **Azure AD Identity Protection**.
3. En la hoja **Identity Protection - Overview (Protección de identidad: información general** ), seleccione cada informe para ver lo que está informando.
4. En **Notificar**, seleccione **Usuarios en riesgo detectados alertas**.
5. En el panel **Alertas detectadas de usuarios en riesgo** , seleccione **Medio**.
6. En **Correos electrónicos se envían a los siguientes usuarios**, seleccione **Incluido** y compruebe que la cuenta de administrador global está en la lista de miembros seleccionados.
7. Seleccione **Guardar**.

En **Proteger**, seleccione varias directivas para ver cómo configurarlas. Si crea y activa una directiva, asegúrese de que no está bloqueando el acceso de todos los usuarios, o es posible que no pueda iniciar sesión. Para evitarlo, excluya cuentas de usuario específicas, como administradores globales.

Para más pruebas y experimentación, consulte [Simulación de eventos de riesgo](/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Implementación de la identidad](deploy-identity-solution-overview.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)