---
title: Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos de autenticación solo para la nube.
ms.openlocfilehash: aa18e1a9943ec12465737f6c3f2e12c1fa49e2a3
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398882"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365

*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*

[Las configuraciones de](../security/office-365-security/microsoft-365-policies-configurations.md) acceso a dispositivos e identidades son un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).

En este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla con los requisitos de la [configuración de requisitos previos solo para la nube](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.

Existen siete fases para configurar el entorno de pruebas:

1.  Crear el entorno de prueba ligero
2.  Configurar ubicaciones con nombre
3.  Configurar la escritura diferida de contraseñas
4.  Configurar el autoservicio de restablecimiento de contraseñas
5.  Configurar la autenticación multifactor
6.  Habilitar Azure AD Identity Protection
7.  Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fase 1: Crear el entorno de prueba ligero de Microsoft 365

Siga las instrucciones de [Configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
Esta es la configuración resultante.

![El entorno de prueba ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a>Fase 2: Configurar ubicaciones con nombre

En primer lugar, determine las direcciones IP públicas o los intervalos de direcciones usados por su organización.

Luego, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o los intervalos de direcciones como ubicaciones con nombre. 

## <a name="phase-3-configure-password-writeback"></a>Fase 3: Configurar la escritura diferida de contraseñas

Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-4-configure-self-service-password-reset"></a>Fase 4: Configurar el autoservicio de restablecimiento de contraseñas

Siga las instrucciones de la [Fase 3 de la Guía del laboratorio de pruebas del restablecimiento de contraseñas](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:

- Usuario 2
- Usuario 3
- Usuario 4
- Usuario 5

Pruebe el restablecimiento de contraseñas solo para la cuenta de Usuario 2.

## <a name="phase-5-configure-multi-factor-authentication"></a>Fase 5: Configurar la autenticación multifactor

Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de autenticación multifactor](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:

- Usuario 2
- Usuario 3
- Usuario 4
- Usuario 5

Pruebe la autenticación multifactor solo para la cuenta del Usuario 2.

## <a name="phase-6-enable-azure-ad-identity-protection"></a>Fase 6: Habilitar Azure AD Identity Protection

Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de autenticación multifactor de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 7: Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online

Para Exchange Online, siga [estas instrucciones](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Para Skype Empresarial Online:

1. Conéctese a [Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

2. Ejecute este comando.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Compruebe que el cambio se realizó correctamente con este comando.

  ```powershell
  Get-CsOAuthConfiguration
  ```

El resultado es un entorno de prueba que cumple con los requisitos de la [configuración de requisitos previos solo para la nube](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades. 

## <a name="next-step"></a>Paso siguiente

Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicionales](m365-enterprise-test-lab-guides.md#identity)

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
