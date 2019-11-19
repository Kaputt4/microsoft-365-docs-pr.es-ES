---
title: Guías del laboratorio de pruebas de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/04/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Use estas guías del laboratorio de pruebas para configurar la demostración, prueba de concepto y entornos de desarrollo y prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 2f6fd8c17096c9c25a0f1af886894e68d33e939d
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672576"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a>Guías del laboratorio de pruebas de Microsoft 365 Enterprise

*Estas aplican tanto para Microsoft 365 Enterprise como para Office 365 Enterprise.*

Las Guías del laboratorio de pruebas (TLG) le ayudan a obtener información rápidamente sobre productos de Microsoft. Proporcionan instrucciones prescriptivas para configurar entornos de pruebas representativos pero simplificados. Puede usar estos entornos para la demostración, la personalización o la creación de pruebas de concepto complejas durante el tiempo que dure una suscripción de prueba o de pago. 

Las TLG están diseñadas para ser modulares. Se desarrollan entre sí para crear varias configuraciones que se adapten a sus necesidades de configuración de aprendizaje o de prueba. La experiencia práctica "Lo diseñé yo mismo y funciona" le ayudará a comprender los requisitos de implementación de un nuevo producto o escenario para que pueda planear mejor su hospedaje en producción.

Las TLG también le permiten crear entornos representativos para desarrollo y prueba de aplicaciones, también conocidos como entornos de desarrollo y prueba.
  
![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

[![Pila de guías de laboratorio de pruebas de Microsoft 365 Enterprise](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Configuración básica

Primero debe crear un entorno de prueba para [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) que incluya Office 365 E5, Enterprise Mobility + Security (EMS) E5 y Windows 10 Enterprise. Puede crear dos tipos distintos de configuraciones básicas:

- Use la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md) si quiere configurar y demostrar las características y funciones de Microsoft 365 Enterprise solo en un entorno de nube, que no incluye ningún componente local.

- Use la [configuración básica de empresa simulada](simulated-ent-base-configuration-microsoft-365-enterprise.md) para configurar y demostrar las características y funciones de Microsoft 365 Enterprise en un entorno híbrido de nube, que use componentes locales como un dominio Active Directory Domain Services (AD DS).

También puede crear entornos de prueba para Office 365 E5 al no agregar la licencia de Microsoft 365 E5 a su prueba o entorno de prueba de producción.
    
## <a name="identity"></a>Identidad

Para mostrar características y funciones relacionadas con identidades, vea:

- [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md)
  
   Habilite y pruebe la sincronización de directorios basada en hash de contraseñas desde un controlador de dominio AD DS.

- [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md)
  
   Habilite y pruebe la autenticación de paso a un controlador de dominio AD DS.

- [Inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Habilite y pruebe Azure AD Seamless Single Sign-on (SSO) con un controlador de dominio AD DS.

- [Autenticación multifactor](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Habilite y pruebe la autenticación multifactor basada en teléfono inteligente para una cuenta de usuario determinada.

- [Proteger las cuentas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Bloquear sus cuentas de administrador global con directivas de acceso condicional.

- [Reescritura de contraseña](password-writeback-m365-ent-test-environment.md)

   Usar una escritura diferida de contraseñas para cambiar la contraseña de su cuenta de usuario de AD DS de Azure AD.

- [Restablecimiento de contraseña](password-reset-m365-ent-test-environment.md)

   Use el restablecimiento de contraseñas de autoservicio (SSPR) para restablecer su contraseña.

- [Licencias automáticas y pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Haga que administrar nuevas cuentas sea más fácil que nunca con licencias automáticas y pertenencia a grupos dinámica.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Examine sus cuentas actuales de usuarios en busca de vulnerabilidades.

- [Acceso de dispositivos e identidades](identity-device-access-m365-test-environment.md)

   Crear un entorno para probar la identidad recomendada y configuraciones de acceso de dispositivo y directivas de acceso condicional.


## <a name="mobile-device-management"></a>Administración de dispositivos móviles

Para mostrar funcionalidades y características relacionadas con la administración de dispositivos móviles, vea:

- [Directivas de cumplimiento de dispositivos](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Cree un grupo de usuarios y una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.
    
- [Inscribir dispositivos iOS y Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Inscriba los dispositivos Android o iOS y adminístrelos de forma remota.


## <a name="information-protection"></a>Protección de la información

Para demostrar características y funciones de la información relacionadas con la protección, vea:

- [Mayor seguridad de Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure las opciones para aumentar la seguridad de Office 365 y analizar las herramientas de seguridad integrada.
  
- [Clasificación de datos](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure y aplique etiquetas de Office 365 a un documento en un sitio de grupo de SharePoint Online.
    
- [Administración del acceso con privilegios](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure la administración del acceso con privilegios para habilitar el acceso puntual a tareas elevadas o con privilegios en su organización de Office 365.


