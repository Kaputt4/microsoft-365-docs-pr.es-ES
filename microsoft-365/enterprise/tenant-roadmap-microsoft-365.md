---
title: Guía básica de inquilinos para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Guía básica para configurar los inquilinos para Microsoft 365.
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948402"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Guía básica de inquilinos para Microsoft 365

Su inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización. Normalmente, este inquilino está asociado a uno o varios de los nombres de dominio DNS públicos y actúa como un contenedor central y aislado para distintas suscripciones y las licencias que se asignan a cuentas de usuario. Para obtener más información, vea [Suscripciones, licencias, cuentas](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)e inquilinos para las ofertas de nube de Microsoft.

Al crear un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica. También puede tener un inquilino con varias ubicaciones geográficas y mover el inquilino de una ubicación a otra.

Para preparar el espacio empresarial para usuarios, grupos, licencias y aplicaciones en la nube, es fundamental planear y ejecutar cuidadosamente la configuración del espacio empresarial.

## <a name="set-up-your-microsoft-365-tenant"></a>Configurar el inquilino de Microsoft 365

Después de asegurarse de que las redes están optimizadas para el acceso a Microsoft 365 para los trabajadores locales y remotos, las siguientes grandes tareas están planeando y configurando su inquilino de Microsoft 365 para nombres de dominio DNS, servicios comunes y para esa infraestructura de identidad que admite el inicio de sesión seguro de los usuarios.

### <a name="plan"></a>Plan

Para planear la implementación del espacio empresarial:

- [Comprender las suscripciones, las licencias y los inquilinos de Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Comprender cómo usar certificados SSL de terceros](plan-for-third-party-ssl-certificates.md)
- [Comprender las formas en que un inquilino de Microsoft 365 se integra con los servicios de Azure AD](integrated-apps-and-azure-ads.md)
- [Planeación de la compatibilidad con aplicaciones cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinar cómo usar la autenticación moderna híbrida](hybrid-modern-auth-overview.md)
- [Planear las actualizaciones de Office 2007 y Office 2010](plan-upgrade-previous-versions-office.md)
- [Comprender el aislamiento de inquilinos](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Implementar

Para implementar el espacio empresarial: 

- Agregue los [dominios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) de su organización.
- Use las [guías de configuración en el Centro de administración de Microsoft 365.](setup-guides-for-microsoft-365.md)
- Cree su infraestructura [de identidades](identity-roadmap-microsoft-365.md) y [proteja los inicios de sesión de usuario.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Mover las ubicaciones geográficas de un inquilino

Microsoft continúa abierto nuevas ubicaciones geográficas de centros de datos (geos) para los servicios de Microsoft 365. Estas nuevas ubicaciones geográficas de centro de datos agregan capacidad y recursos de cálculo para admitir la demanda del cliente y el crecimiento del uso. Además, las nuevas ubicaciones geográficas del centro de datos ofrecen residencia de datos en la ubicación geográfica para los datos principales de los clientes.

Para obtener más información, vea Mover los datos principales a las nuevas ubicaciones geográficas del centro de datos [de Microsoft 365.](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Implementar Microsoft 365 Multi-Geo

Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.

Para más información, vea [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Administrar varios inquilinos de Microsoft 365 

Aunque es ideal tener un único inquilino para la organización, puede ser una de las muchas organizaciones que tienen varios inquilinos. Los motivos pueden incluir fusiones y adquisiciones, quieres aislamiento administrativo o tienes una TI descentralizada.

Si tiene varios inquilinos de Microsoft 365, vea estos artículos para obtener más información sobre:

- [Colaboración entre inquilinos](microsoft-365-inter-tenant-collaboration.md)
- [Migración de buzones de inquilinos cruzados](cross-tenant-mailbox-migration.md)
- [Migraciones de espacio empresarial a espacio empresarial](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Paso siguiente

Inicie la planeación del espacio empresarial [con suscripciones, licencias, cuentas e inquilinos.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
