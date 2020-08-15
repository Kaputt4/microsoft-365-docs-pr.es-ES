---
title: Requisitos previos de acceso de dispositivos e identidades para la sincronización de hash de contraseña en su entorno de prueba de Microsoft 365
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
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos para la autenticación de sincronización de hash de contraseña.
ms.openlocfilehash: 6aa6b1cd1b8f9459b27e46fa67c62b35014b2d7e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686255"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>Requisitos previos de acceso de dispositivos e identidades para la sincronización de hash de contraseña en su entorno de prueba de Microsoft 365

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Las [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md) son un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios de Microsoft 365 para empresas que se integran con Azure Active Directory (Azure ad).

Este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla los requisitos del [Active Directory con la configuración de requisitos previos de sincronización de hash de contraseña](identity-access-prerequisites.md#prerequisites) para acceso de dispositivos e identidades.

Existen ocho fases para configurar el entorno de pruebas:

1.  Crear una empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas
2.  Configurar el inicio de sesión único de conexión directa de Azure AD
3.  Configurar ubicaciones con nombre
4.  Configurar la escritura diferida de contraseñas
5.  Configurar el autoservicio de restablecimiento de contraseñas para todas las cuentas de usuario.
6.  Configurar la autenticación multifactor para todas las cuentas de usuario.
7.  Habilitar Azure AD Identity Protection
8.  Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>Fase 1: Crear una empresa simulada con la sincronización de hash de contraseñas en el entorno de prueba de Microsoft 365

Siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md).
Esta es la configuración resultante.

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Fase 2: Configurar inicio de sesión único de conexión directa de Azure AD

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 del inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Fase 3: Configurar ubicaciones con nombre

En primer lugar, determine las direcciones IP públicas o el intervalo de direcciones usadas por su organización.

A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre. 

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

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Fase 7: Habilitación de Azure AD Identity Protection

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 8: Habilitar autenticación moderna para Exchange Online y Skype Empresarial Online

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

El resultado es un entorno de prueba que cumple los requisitos de [Active Directory con la configuración de requisitos previos de sincronización de hash de contraseña](identity-access-prerequisites.md#prerequisites) para acceso de dispositivos e identidades. 

## <a name="next-step"></a>Paso siguiente

Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicionales](m365-enterprise-test-lab-guides.md#identity)

[Mapa de ruta de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
