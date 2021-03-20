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
description: Configure Azure AD Identity Protection y analice las cuentas actuales en su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905349"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas

*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

Puede usar Azure Active Directory (Azure AD) Identity Protection para detectar posibles vulnerabilidades que afecten a las identidades de su organización, configurar respuestas automatizadas e investigar incidentes. En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.

La configuración de Azure AD Identity Protection en el entorno de prueba de Microsoft 365 para empresas implica dos fases:

- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Usar Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para](../downloads/Microsoft365EnterpriseTLGStack.pdf)enterprise Test Lab Guide Stack .
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si solo desea probar Azure AD Identity Protection de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas de Azure AD Identity Protection no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: Usar Azure AD Identity Protection

1. Abra una instancia privada del explorador e inicie sesión en Azure Portal con la cuenta de administrador global de su entorno de prueba de [https://portal.azure.com](https://portal.azure.com) Microsoft 365 para empresas.
2. En Azure Portal, escriba **Identity Protection** en el cuadro de búsqueda y, a continuación, seleccione Azure AD **Identity Protection**.
3. En la **hoja Identity Protection - Overview,** seleccione cada informe para ver lo que está informando.
4. En **Notificar**, seleccione **Usuarios en riesgo alertas detectadas**.
5. En el panel **Usuarios en riesgo de alertas detectadas,** seleccione **Medio**.
6. Para **los correos electrónicos se envían a los siguientes usuarios,** seleccione **Incluido** y compruebe que su cuenta de administrador global esté en la lista de miembros seleccionados.
7. Seleccione **Guardar**.

En **Proteger,** seleccione varias directivas para ver cómo configurarlas. Si crea y activa una directiva, asegúrese de que no está bloqueando el acceso para todos los usuarios, o puede que no pueda iniciar sesión. Para evitar esto, excluya cuentas de usuario específicas, como administradores globales.

Para más pruebas y experimentación, vea [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)