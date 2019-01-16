---
title: Entorno de prueba de Azure protección de identidad de AD para su empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurar la protección de identidad de Azure AD y analizar las cuentas actuales en el entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871243"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Entorno de prueba de Azure protección de identidad de AD para su empresa de 365 de Microsoft

Protección de identidad de AD Azure permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar las respuestas automáticas e investigar incidentes. En este artículo se describe cómo habilitar la protección de la identidad de Azure AD y ver el análisis de las cuentas del entorno de prueba.

Hay dos fases para configurar la protección de la identidad de AD de Azure en el entorno de prueba de Microsoft 365 Enterprise:

1. Crear el entorno de prueba de Microsoft 365 Enterprise.
2. Habilitar y usar la protección de la identidad de AD de Azure.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea probar la protección de la identidad de AD de Azure en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la protección de la identidad de AD de Azure en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Prueba de protección de identidad de Azure AD no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar la protección de la identidad de Azure AD y experimentar con él en un entorno que representa una organización típica. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Fase 2: Habilitar y usar la protección de la identidad de AD de Azure

1. Abra una instancia privada de su explorador e inicie sesión el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global de su entorno de prueba de Microsoft 365 Enterprise.
2. En el portal de Azure, haga clic en **todos los servicios > Marketplace**.
3. Escriba la **protección de la identidad de Azure AD** y, a continuación, haga clic en él.
4. En el servidor blade **De introducción** , haga clic en **incorporado** en **configuración**, haga clic en **Anclar a panel**y, a continuación, haga clic en **crear**.
5. En el portal de Azure, haga clic en **protección de la identidad de AD de Azure** en el panel. 

   Debería ver un blade de **Azure AD protección-Introducción Identity** con un panel. En **las vulnerabilidades**, tenga en cuenta que determina el número de cuentas de usuario sin registro autenticación multifactor. Este número variará en función de anterior Microsoft 365 Enterprise prueba guías de laboratorio de que ha llevado a cabo.

6. Haga clic en a través de las categorías para **investigar** ver si hay eventos que se han detectado o los usuarios.

Para realizar más pruebas y experimentación, consulte [eventos de riesgo Simulating](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Vea el paso de [protección contra credenciales ponen en peligro](identity-azure-ad-identity-protection.md) en la fase de identidad para obtener información y vínculos para implementar la protección de la identidad de AD de Azure en producción.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
