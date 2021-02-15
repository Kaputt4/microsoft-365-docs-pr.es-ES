---
title: Identidad para Contoso Corporation
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
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754657"
---
# <a name="identity-for-the-contoso-corporation"></a>Identidad para Contoso Corporation

Microsoft proporciona Identidad como servicio (IDaaS) en sus ofertas de nube a través de Azure Active Directory (Azure AD). Para adoptar Microsoft 365 para empresas, la solución IDaaS de Contoso tenía que usar su proveedor de identidades local e incluir la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.

## <a name="the-contoso-active-directory-domain-services-forest"></a>El bosque de Servicios de dominio de Active Directory de Contoso

Contoso usa un único bosque de Servicios de dominio de Active Directory (AD DS) para contoso com con siete subdominios, uno para \. cada región del mundo. La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.

Este es el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen concentradores regionales.

![Bosque y dominios de Contoso en todo el mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso decidió usar las cuentas y grupos del bosque com de contoso para la autenticación y autorización de sus cargas de trabajo y servicios \. de Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>La infraestructura de autenticación federada de Contoso

Contoso permite lo siguiente:

- Los clientes deben usar sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en el sitio web público de la compañía.
- Los proveedores y partners usan sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de partners de la compañía.

Esta es la red perimetral de Contoso que contiene un sitio web público, una extranet de asociados y un conjunto de servidores de Servicios de federación de Active Directory (AD FS). La red perimetral está conectada a Internet que contiene clientes, partners y servicios de Internet.

![Compatibilidad de Contoso con autenticación federada para clientes y socios](../media/contoso-identity/contoso-identity-fig2.png)
 
Los servidores de AD FS en la red perimetral facilitan la autenticación de credenciales de cliente por parte de sus proveedores de identidades para obtener acceso al sitio web público y a las credenciales de socio para obtener acceso a la extranet de asociados.

Contoso decidió mantener esta infraestructura y dedicarla a la autenticación de clientes y partners. Los arquitectos de identidad de Contoso están investigando la conversión de esta infraestructura en las soluciones de Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube

Contoso quería usar su bosque de AD DS local para la autenticación en recursos en la nube de Microsoft 365. Decidió usar la sincronización de hash de contraseña (PHS).

PHS sincroniza el bosque de AD DS local con el inquilino de Azure AD de su suscripción de Microsoft 365 para empresas, copiando cuentas de usuario y grupo y una versión con hash de contraseñas de cuentas de usuario.

Para realizar la sincronización de directorios, Contoso implementó la herramienta Azure AD Connect en un servidor de su centro de datos de París.

Este es el servidor que ejecuta Azure AD Connect sondear el bosque de Contoso AD DS para buscar cambios y, a continuación, sincronizar esos cambios con el inquilino de Azure AD.

![La infraestructura de sincronización de directorios phs de Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Directivas de Acceso Condicional a identidades y dispositivos

Contoso creó un conjunto de [directivas de Acceso Condicional](identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:

- *Las protecciones* de línea base se aplican a todas las cuentas de usuario.
- *Las protecciones* confidenciales se aplican al personal directivo y ejecutivo.
- *Las protecciones altamente* reguladas se aplican a usuarios específicos de los departamentos de finanzas, jurídicos y de investigación que tienen acceso a datos altamente regulados.

Este es el conjunto resultante de directivas de acceso condicional de dispositivo e identidad de Contoso.

![Directivas de acceso condicional a identidades y dispositivos de Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Paso siguiente

Obtén información sobre cómo Contoso usa su infraestructura de Microsoft Endpoint Configuration Manager para implementar y mantener [windows 10 Enterprise actual](contoso-win10.md) en toda la organización.

## <a name="see-also"></a>Vea también

[Plan de identidad para Microsoft 365](identity-roadmap-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
