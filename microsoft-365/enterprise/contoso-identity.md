---
title: Identidad para Contoso Corporation
author: kelleyvice-msft
f1.keywords:
  - NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
  - M365-identity-device-management
  - Strat_O365_Enterprise
ms.custom: null
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
---

# <a name="identity-for-the-contoso-corporation"></a>Identidad para Contoso Corporation

Microsoft proporciona Identity as a Service (IDaaS) a través de sus ofertas en la nube mediante Azure Active Directory (Azure AD). Para adoptar Microsoft 365 empresa, la solución IDaaS de Contoso tenía que usar su proveedor de identidades local e incluir la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.

## <a name="the-contoso-active-directory-domain-services-forest"></a>El bosque de Servicios de dominio de Active Directory de Contoso

Contoso usa un único bosque de Servicios de dominio de Active Directory (AD DS) para contosocom\. con siete subdominios, uno para cada región del mundo. La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.

Este es el bosque contoso con dominios regionales para las diferentes partes del mundo que contienen concentradores regionales.

:::image type="content" alt-text="Bosque y dominios de Contoso en todo el mundo." source="../media/contoso-identity/contoso-identity-fig1.png" lightbox="../media/contoso-identity/contoso-identity-fig1.png":::
 
Contoso decidió usar las cuentas y grupos del bosque contosocom\. para la autenticación y autorización para sus Microsoft 365 cargas de trabajo y servicios.

## <a name="the-contoso-federated-authentication-infrastructure"></a>La infraestructura de autenticación federada de Contoso

Contoso permite lo siguiente:

- Los clientes usan sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en el sitio web público de la compañía.
- Proveedores y partners para usar sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de partners de la compañía.

Esta es la DMZ de Contoso que contiene un sitio web público, una extranet de asociado y un conjunto de servidores de Servicios de federación de Active Directory (AD FS). La DMZ está conectada a Internet que contiene clientes, partners y servicios de Internet.

![Compatibilidad con Contoso para la autenticación federada para clientes y partners.](../media/contoso-identity/contoso-identity-fig2.png)
 
Los servidores de AD FS en la DMZ facilitan la autenticación de credenciales de cliente por parte de sus proveedores de identidades para obtener acceso al sitio web público y a las credenciales de socio para acceder a la extranet de partners.

Contoso decidió mantener esta infraestructura y dedicarse a la autenticación de clientes y partners. Los arquitectos de identidad de Contoso están investigando la conversión de esta infraestructura en las soluciones de Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) y [B2C](/azure/active-directory-b2c/solution-articles)

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube

Contoso quería usar su bosque de AD DS local para la autenticación para Microsoft 365 en la nube. Decidió usar la sincronización de hash de contraseña (PHS).

PHS sincroniza el bosque de AD DS local con el inquilino Azure AD de su suscripción de Microsoft 365 para empresas, copiando cuentas de usuario y grupo y una versión hash de contraseñas de cuentas de usuario.

Para realizar la sincronización de directorios, Contoso implementó la Azure AD Conectar en un servidor en su centro de datos de París.

Este es el servidor que ejecuta Azure AD Conectar el bosque de Contoso AD DS en busca de cambios y, a continuación, sincroniza esos cambios con el Azure AD inquilino.

![La infraestructura de sincronización de directorios de PHS de Contoso.](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-zero-trust-identity-and-device-access"></a>Directivas de acceso condicional para la identidad de confianza cero y el acceso a dispositivos

Contoso creó un conjunto de [directivas de Acceso Condicional](../security/office-365-security/identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:

- *Las protecciones* de punto de inicio se aplican a todas las cuentas de usuario.
- *Enterprise* protecciones se aplican al personal directivo y ejecutivo.
- *Las protecciones* de seguridad especializadas se aplican a usuarios específicos de los departamentos de finanzas, legales e investigación que tienen acceso a datos altamente regulados.

Este es el conjunto resultante de directivas de identidad y dispositivo de acceso condicional de Contoso.

:::image type="content" alt-text="Directivas de identidad y dispositivo de acceso condicional de Contoso." source="../media/contoso-identity/contoso-identity-fig5.png" lightbox="../media/contoso-identity/contoso-identity-fig5.png":::
 
## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso usa su Microsoft Endpoint Configuration Manager para [implementar y](contoso-win10.md) mantener el nivel Windows 10 Enterprise toda su organización.

## <a name="see-also"></a>Vea también

[Implementar identidad para Microsoft 365](deploy-identity-solution-overview.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)