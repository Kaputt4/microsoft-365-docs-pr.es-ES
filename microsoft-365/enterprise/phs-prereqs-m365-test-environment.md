---
title: Requisitos previos de acceso de dispositivos e identidades para la sincronización de hash de contraseña en su entorno de prueba de Microsoft 365
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
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos para la autenticación de sincronización de hash de contraseña.
ms.openlocfilehash: 2ca83b6ab715a752d3d9620af631263eb5d84fa3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051251"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>Requisitos previos de acceso de dispositivos e identidades para la sincronización de hash de contraseña en su entorno de prueba de Microsoft 365

*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

[Las configuraciones](../security/defender-365-security/microsoft-365-policies-configurations.md) de acceso a dispositivos y identidades son un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios de Microsoft 365 para empresas que están integrados con Azure Active Directory (Azure AD).

En este artículo se describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla los requisitos del híbrido con la configuración de requisitos previos de autenticación de sincronización [de hash](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) de contraseña para el acceso a dispositivos y identidades.

Hay diez fases para configurar este entorno de prueba:

1. Crear una empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas
2. Configurar el inicio de sesión único de conexión directa de Azure AD
3. Configurar ubicaciones con nombre
4. Configurar la escritura diferida de contraseñas
5. Configurar el autoservicio de restablecimiento de contraseñas para todas las cuentas de usuario.
6. Configurar la autenticación multifactor para todas las cuentas de usuario.
7. Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio
8. Configurar la protección con contraseña de Azure AD 
9. Habilitar Azure AD Identity Protection
10. Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>Fase 1: Crear una empresa simulada con la sincronización de hash de contraseñas en el entorno de prueba de Microsoft 365

Siga las instrucciones de la Guía del laboratorio de [pruebas](password-hash-sync-m365-ent-test-environment.md) de sincronización de hash de contraseña.
Esta es la configuración resultante.

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Fase 2: Configurar inicio de sesión único de conexión directa de Azure AD

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 del inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Fase 3: Configurar ubicaciones con nombre

En primer lugar, determine las direcciones IP públicas o el intervalo de direcciones usadas por su organización.

A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre. 

## <a name="phase-4-configure-password-writeback"></a>Fase 4: Configurar la escritura diferida de contraseñas

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-5-configure-self-service-password-reset"></a>Fase 5: Configurar el autoservicio de restablecimiento de contraseña

Siga las instrucciones en la [Guía de entorno de pruebas, fase 3 de la operación de restablecimiento de contraseña](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:

- Usuario 2
- Usuario 3
- Usuario 4
- Usuario 5

Pruebe el restablecimiento de contraseña solo de la cuenta Usuario 2.

## <a name="phase-6-configure-multi-factor-authentication"></a>Fase 6: Configurar la autenticación multifactor

Siga las instrucciones en [Guía del laboratorio de pruebas, fase 2 de la autenticación multifactor ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:

- Usuario 2
- Usuario 3
- Usuario 4
- Usuario 5

Pruebe la autenticación multifactor solo para la cuenta Usuario 2.

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Fase 7: Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio 

Sigue [estas instrucciones para](/azure/active-directory/devices/hybrid-azuread-join-plan) habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio.

## <a name="phase-8-configure-azure-ad-password-protection"></a>Fase 8: Configurar la protección con contraseña de Azure AD 

Siga [estas instrucciones para](/azure/active-directory/authentication/concept-password-ban-bad) bloquear las contraseñas débiles conocidas y sus variantes.

## <a name="phase-9-enable-azure-ad-identity-protection"></a>Fase 9: Habilitar Azure AD Identity Protection

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 10: Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online

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

El resultado es un entorno de prueba que cumple los requisitos de [Active Directory con la configuración de requisitos previos de sincronización de hash de contraseña](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) para acceso de dispositivos e identidades. 

## <a name="next-step"></a>Paso siguiente

Use [Directivas comunes de acceso a dispositivos e identidades](../security/defender-365-security/identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicionales](m365-enterprise-test-lab-guides.md#identity)

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
