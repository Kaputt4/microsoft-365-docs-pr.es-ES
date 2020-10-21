---
title: Identidad para Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637252"
---
# <a name="identity-for-the-contoso-corporation"></a>Identidad para Contoso Corporation

Microsoft proporciona identidad como un servicio (IDaaS) en todas sus ofertas de la nube a través de Azure Active Directory (Azure AD). Para adoptar Microsoft 365 para empresas, la solución IDaaS de Contoso tuvo que usar su proveedor de identidades local e incluir la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.

## <a name="the-contoso-active-directory-domain-services-forest"></a>El bosque de servicios de dominio de Active Directory de Contoso

Contoso usa un solo bosque de servicios de dominio de Active Directory (AD DS) para contoso \. com con siete subdominios, uno para cada región del mundo. La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.

Este es el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.

![Bosque y dominios de Contoso en todo el mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso decidió usar las cuentas y los grupos del \. bosque com de Contoso para la autenticación y autorización de sus cargas de trabajo y servicios de Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>La infraestructura de autenticación federada de Contoso

Contoso permite lo siguiente:

- Los clientes usen sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en el sitio web público de la compañía.
- Proveedores y partners para usar sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de asociados de la compañía.

Esta es la DMZ de Contoso que contiene un sitio web público, una extranet de asociados y un conjunto de servidores de AD FS. La DMZ está conectada a Internet que contiene clientes, socios y servicios de Internet.

![Soporte técnico de Contoso para la autenticación federada para clientes y Partners](../media/contoso-identity/contoso-identity-fig2.png)
 
Los servidores de AD FS en la DMZ facilitan la autenticación de las credenciales del cliente por sus proveedores de identidades para obtener acceso al sitio web público y las credenciales del asociado para obtener acceso a la extranet del asociado.

Contoso decidió mantener esta infraestructura y dedicarla a la autenticación de clientes y socios. Los arquitectos de identidad de Contoso están investigando la conversión de esta infraestructura en las soluciones de Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube

Contoso quería usar su bosque de AD DS local para la autenticación en los recursos de nube de Microsoft 365. Decidió usar la sincronización de hash de contraseña (PHS).

PHS sincroniza el bosque de AD DS local con el inquilino de Azure AD de su suscripción de Microsoft 365 para empresas, copiando las cuentas de usuario y grupo y una versión hash de las contraseñas de cuentas de usuario.

Para realizar la sincronización de directorios, contoso implementó la herramienta de Azure AD Connect en un servidor en su centro de recursos de París.

Este es el servidor que ejecuta Azure AD Connect y sondea el bosque de Contoso AD DS para obtener los cambios y, a continuación, sincronizar dichos cambios con el inquilino de Azure AD.

![La infraestructura de sincronización de directorios de Contoso PHS](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Directivas de Acceso Condicional a identidades y dispositivos

Contoso creó un conjunto de [directivas de Acceso Condicional](identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:

- Las protecciones de *línea base* se aplican a todas las cuentas de usuario.
- Las protecciones *confidenciales* son válidas para el liderazgo Senior y el personal ejecutivo.
- Las protecciones *altamente reguladas* se aplican a usuarios específicos en los departamentos de finanzas, legales y de investigación que tienen acceso a datos altamente regulados.

Este es el conjunto resultante de directivas de acceso condicional de identidad de Contoso y de dispositivo.

![Directivas de acceso condicional a identidades y dispositivos de Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Paso siguiente

[Obtenga información sobre](contoso-win10.md) cómo contoso usa su infraestructura de Microsoft Endpoint Configuration Manager para implementar y mantener la actual de Windows 10 Enterprise en su organización.

## <a name="see-also"></a>Vea también

[Plan de identidad para Microsoft 365](identity-roadmap-microsoft-365.md)

[Información general de Microsoft 365 para empresas](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
