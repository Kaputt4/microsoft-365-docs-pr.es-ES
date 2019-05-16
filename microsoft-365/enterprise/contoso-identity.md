---
title: Identidad para Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: 3b11546f99831ffe4d31ea3b102d080ddf1f9957
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072660"
---
# <a name="identity-for-the-contoso-corporation"></a>Identidad para Contoso Corporation

**Resumen:** Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.

Microsoft proporciona una Identidad como servicio (IDaaS) en su oferta en la nube con Azure Active Directory (Azure AD). Para adoptar Microsoft 365 Enterprise, la solución IDaaS de Contoso debe aprovechar su proveedor de identidades local y seguir incluyendo la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.

## <a name="contosos-active-directory-domain-services-forest"></a>Bosque de Active Directory Domain Services de Contoso

Contoso usa un único bosque de Active Directory Domain Services (AD DS) para contoso.com con siete subdominios, uno para cada región del mundo. La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.

La figura 1 muestra el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.

![](./media/contoso-identity/contoso-identity-fig1.png)
 
**Figura 1: Bosque y dominios de Contoso en todo el mundo**

Contoso quería usar las cuentas y los grupos del bosque contoso.com para la autenticación y la autorización de sus cargas de trabajo y servicios en Microsoft 365.

## <a name="contosos-federated-authentication-infrastructure"></a>Infraestructura de autenticación federada de Contoso

Contoso permite lo siguiente:

- Que los clientes usen sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en su sitio web público.
- Que los proveedores y partners usen sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de partners.

La figura 2 muestra la red perimetral de Contoso con un sitio web público, una extranet de partners y un conjunto de servidores de Servicios de federación de Active Directory (AD FS). La red perimetral está conectada a Internet que contiene clientes y partners, y servicios de Internet.

![](./media/contoso-identity/contoso-identity-fig2.png)

**Figura 2: Soporte de Contoso para la autenticación federada para clientes y partners**
 
Los servidores de los Servicios de federación de Active Directory (AD FS) de la red perimetral autentican las credenciales de cliente para el acceso al sitio web público y las credenciales de partner para el acceso a la extranet de partners.

Contoso decidió mantener esta infraestructura y dedicarla a autenticaciones de partners y clientes. Los ingenieros de identidad de Contoso están investigando la conversión de esta infraestructura a Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y soluciones [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube

Contoso quería aprovechar su bosque local de AD DS para la autenticación para los recursos de nube de Microsoft 365. Optó por la sincronización de hash de contraseñas (PHS).

PHS sincroniza el bosque local de AD DS con la cuenta empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise, copiando las cuentas de usuario y de grupo, junto con una versión en hash de las contraseñas de cuentas de usuario. 

Para realizar la sincronización continua de directorios, Costoso ha implementado la herramienta Azure AD Connect en un servidor de su centro de datos de París. La figura 3 muestra el servidor que ejecuta Azure AD Connect y que sondea el bosque AD DS de Contoso en busca de cambios, para sincronizar dichos cambios con la cuenta empresarial de Azure AD.

![](./media/contoso-identity/contoso-identity-fig4.png)
 
**Figura 3: Infraestructura de sincronización PHS de directorios de Contoso**


## <a name="conditional-access-policies-for-identity-and-device-access"></a>Directivas de acceso condicional a identidades y dispositivos

Contoso creó un conjunto de [directivas de acceso condicional](identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:

- Protección **básica**, que se aplica a todas las cuentas de usuario
- Protección **confidencial**, que se aplica al personal directivo y al personal ejecutivo
- Protección **altamente regulada**, que se aplica a usuarios específicos de los departamentos financiero, legal y de investigación que tienen acceso a datos altamente regulados.

La figura 4 muestra el conjunto resultante de directivas de acceso condicional a identidades.

![](./media/contoso-identity/contoso-identity-fig5.png)
 
**Figura 4: Directivas de acceso condicional a identidades y dispositivos de Contoso**

## <a name="next-step"></a>Paso siguiente

[Obtenga información sobre](contoso-win10.md) cómo aprovecha Contoso su infraestructura de System Center Configuration Manager para implementar y mantener actualizado Windows 10 Enterprise en la organización.

## <a name="see-also"></a>Vea también

[Identidad para Microsoft 365 Enterprise](identity-infrastructure.md)

[Guía de implementación](deploy-microsoft-365-enterprise.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
