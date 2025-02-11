---
title: Identidad para Contoso Corporation
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: 83c5444be2edafde4fc7b3cb677804e909837b72
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68179447"
---
# <a name="identity-for-the-contoso-corporation"></a>Identidad para Contoso Corporation

Microsoft proporciona identidad como servicio (IDaaS) en sus ofertas en la nube a través de Azure Active Directory (Azure AD). Para adoptar Microsoft 365 para empresas, la solución Contoso IDaaS tenía que usar su proveedor de identidades local e incluir la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.

## <a name="the-contoso-active-directory-domain-services-forest"></a>El bosque de contoso Servicios de dominio de Active Directory

Contoso usa un único bosque Servicios de dominio de Active Directory (AD DS) para contoso\.com con siete subdominios, uno para cada región del mundo. La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.

Este es el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.

:::image type="content" alt-text="Bosque y dominios de Contoso en todo el mundo." source="../media/contoso-identity/contoso-identity-fig1.png" lightbox="../media/contoso-identity/contoso-identity-fig1.png":::
 
Contoso decidió usar las cuentas y grupos del bosque de contoso\.com para la autenticación y autorización para sus cargas de trabajo y servicios de Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>La infraestructura de autenticación federada de Contoso

Contoso permite lo siguiente:

- Los clientes deben usar sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en el sitio web público de la empresa.
- Proveedores y asociados para usar sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de asociados de la empresa.

Esta es la red perimetral de Contoso que contiene un sitio web público, una extranet de asociado y un conjunto de servidores de Servicios de federación de Active Directory (AD FS) (AD FS). La red perimetral está conectada a Internet que contiene clientes, asociados y servicios de Internet.

![Compatibilidad de Contoso con la autenticación federada para clientes y asociados.](../media/contoso-identity/contoso-identity-fig2.png)
 
Los servidores de AD FS en la red perimetral facilitan la autenticación de las credenciales del cliente por parte de sus proveedores de identidades para acceder al sitio web público y las credenciales de asociado para acceder a la extranet del asociado.

Contoso decidió mantener esta infraestructura y dedicarla a la autenticación de clientes y asociados. Los arquitectos de identidad de Contoso están investigando la conversión de esta infraestructura en las soluciones de Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) y [B2C](/azure/active-directory-b2c/solution-articles)

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube

Contoso quería usar su bosque de AD DS local para la autenticación en los recursos en la nube de Microsoft 365. Decidió usar la sincronización de hash de contraseña (PHS).

PHS sincroniza el bosque de AD DS local con el inquilino de Azure AD de su suscripción de Microsoft 365 para empresas, copiando cuentas de usuario y grupo y una versión con hash de contraseñas de cuenta de usuario.

Para realizar la sincronización de directorios, Contoso implementó la herramienta Azure AD Connect en un servidor de su centro de datos de París.

Este es el servidor que ejecuta Azure AD Connect que sondea el bosque de Contoso AD DS para ver si hay cambios y, a continuación, sincroniza esos cambios con el inquilino de Azure AD.

![La infraestructura de sincronización de directorios PHS de Contoso.](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-zero-trust-identity-and-device-access"></a>Directivas de acceso condicional para Confianza cero identidad y acceso a dispositivos

Contoso creó un conjunto de [directivas de Acceso Condicional](../security/office-365-security/identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:

- Las protecciones de *punto de partida* se aplican a todas las cuentas de usuario.
- Las protecciones *empresariales* se aplican a la dirección sénior y al personal ejecutivo.
- Las protecciones *de seguridad especializadas* se aplican a usuarios específicos de los departamentos financieros, legales y de investigación que tienen acceso a datos altamente regulados.

Este es el conjunto resultante de directivas de acceso condicional de dispositivo e identidad de Contoso.

:::image type="content" alt-text="Directivas de acceso condicional de dispositivo e identidad de Contoso." source="../media/contoso-identity/contoso-identity-fig5.png" lightbox="../media/contoso-identity/contoso-identity-fig5.png":::
 
## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso usa su infraestructura de Configuration Manager de punto de conexión de Microsoft para [implementar y mantener Windows 10 Enterprise actuales](contoso-win10.md) en toda su organización.

## <a name="see-also"></a>Vea también

[Implementar identidad para Microsoft 365](deploy-identity-solution-overview.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)