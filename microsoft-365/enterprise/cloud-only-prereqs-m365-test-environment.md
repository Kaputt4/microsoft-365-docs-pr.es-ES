---
title: Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos de autenticación solo para la nube.
ms.openlocfilehash: 537718eb0efcffc296162a4458158efcbdad9986
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051549"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365

*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

[Las configuraciones de acceso](../security/defender-365-security/microsoft-365-policies-configurations.md) a dispositivos y identidades son un conjunto de configuraciones recomendadas y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).

En este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla con los requisitos de la [configuración de requisitos previos solo para la nube](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.

Existen ocho fases para configurar el entorno de pruebas:

1. Crear el entorno de prueba ligero
2. Configurar ubicaciones con nombre
3. Configurar el autoservicio de restablecimiento de contraseñas
4. Configurar la autenticación multifactor
5. Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio
6. Configurar la protección con contraseña de Azure AD 
7. Habilitar Azure AD Identity Protection
8. Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fase 1: Crear el entorno de prueba ligero de Microsoft 365

Siga las instrucciones de [Configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
Esta es la configuración resultante.

![El entorno de prueba ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a>Fase 2: Configurar ubicaciones con nombre

En primer lugar, determine las direcciones IP públicas o los intervalos de direcciones usados por su organización.

A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre. 

## <a name="phase-3-configure-self-service-password-reset"></a>Fase 3: Configurar el restablecimiento de contraseñas de autoservicio

Siga las instrucciones en la [Guía de entorno de pruebas, fase 3 de la operación de restablecimiento de contraseña](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:

- Usuario 2
- Usuario 3
- Usuario 4
- Usuario 5

Pruebe el restablecimiento de contraseña solo de la cuenta Usuario 2.

## <a name="phase-4-configure-multi-factor-authentication"></a>Fase 4: Configurar la autenticación multifactor

Siga las instrucciones en [Guía del laboratorio de pruebas, fase 2 de la autenticación multifactor ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:

- Usuario 2
- Usuario 3
- Usuario 4
- Usuario 5

Pruebe la autenticación multifactor solo para la cuenta Usuario 2.

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Fase 5: Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio 

Sigue [estas instrucciones para](/azure/active-directory/devices/hybrid-azuread-join-plan) habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio.

## <a name="phase-6-configure-azure-ad-password-protection"></a>Fase 6: Configurar la protección con contraseña de Azure AD 

Siga [estas instrucciones para](/azure/active-directory/authentication/concept-password-ban-bad) bloquear las contraseñas débiles conocidas y sus variantes.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Fase 7: Habilitación de Azure AD Identity Protection

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 8: Habilitar autenticación moderna para Exchange Online y Skype Empresarial Online

Para Exchange Online, siga [estas instrucciones](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Para Skype Empresarial Online:

1. Conéctese a [Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

2. Ejecute este comando.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Compruebe que el cambio se realizó correctamente con este comando.

  ```powershell
  Get-CsOAuthConfiguration
  ```

El resultado es un entorno de prueba que cumple los requisitos de la configuración de [requisitos](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) previos de solo nube para el acceso de identidades y dispositivos. 

## <a name="next-step"></a>Paso siguiente

Use [Directivas comunes de acceso a dispositivos e identidades](../security/defender-365-security/identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicionales](m365-enterprise-test-lab-guides.md#identity)

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
