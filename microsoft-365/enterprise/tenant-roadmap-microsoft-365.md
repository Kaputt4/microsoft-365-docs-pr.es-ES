---
title: Mapa de ruta del espacio empresarial para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La guía básica para configurar los inquilinos para Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656012"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Mapa de ruta del espacio empresarial para Microsoft 365

Su inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización. Normalmente, este inquilino está asociado con uno o más de los nombres de dominio DNS y actúa como un contenedor central para distintas suscripciones y las licencias que se asignan a las cuentas de usuario. Para obtener más información, vea [suscripciones, licencias, cuentas e inquilinos para las ofertas de la nube de Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

Cuando se crea un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica. También puede tener un inquilino con varias ubicaciones geográficas y mover el espacio empresarial de una ubicación a otra.

Para preparar su inquilino para la identidad, es fundamental planear y ejecutar cuidadosamente la configuración de inquilinos.


## <a name="set-up-your-microsoft-365-tenant"></a>Configurar su inquilino de Microsoft 365

Una vez que haya comprobado que la red está optimizada para el acceso a Microsoft 365 tanto para trabajadores locales como remotos, las próximas grandes tareas planean y configuran el espacio empresarial de Microsoft 365 para los nombres de dominio DNS, los servicios comunes y para esa infraestructura de identidad que admita el inicio de sesión de usuario seguro.

## <a name="plan"></a>Plan

Para planear la implementación del espacio empresarial:

- [Comprender las suscripciones, las licencias y los inquilinos de Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Aprenda a usar certificados SSL de terceros](plan-for-third-party-ssl-certificates.md)
- [Comprender las formas en que un inquilino de Microsoft 365 se integra con los servicios de Azure AD](integrated-apps-and-azure-ads.md)
- [Planeación del soporte técnico de aplicaciones cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinación del uso de la autenticación moderna híbrida](hybrid-modern-auth-overview.md)
- [Planeación de actualizaciones de Office 2007 y Office 2010](plan-upgrade-previous-versions-office.md)
- [Comprender el aislamiento de inquilino](microsoft-365-tenant-isolation-overview.md)
- [Obtener información detallada sobre Microsoft 365 Service Assurance](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a>Implementar

Para implementar su espacio empresarial: 

- Agregue los [dominios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para su organización.
- Use las [guías de configuración del centro de administración de Microsoft 365](setup-guides-for-microsoft-365.md).
- Crear la [infraestructura de identidad](identity-roadmap-microsoft-365.md) y [proteger los inicios de sesión de los usuarios](microsoft-365-secure-sign-in.md).

### <a name="move-a-tenants-geographic-locations"></a>Mover las ubicaciones geográficas de un inquilino

Microsoft sigue abrir nuevas ubicaciones geográficas del centro de recursos (GEOS) para los servicios de Microsoft 365. Estos nuevos GEOS de centro de recursos agregan capacidad y computan recursos para apoyar el crecimiento de la demanda y el uso de los clientes. Además, el nuevo centro de datos GEOS ofrece una residencia de datos geográfica para los principales datos de clientes.

Para obtener más información, vea [mover datos principales a New Microsoft 365 Datacenter GEOS](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Implementación de Microsoft 365 multigeográfico

Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.

Para obtener más información, vea [Microsoft 365 multi-geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenancies"></a>Administrar varios arrendamientos de Microsoft 365 

Aunque tener un único inquilino para su oganization es ideal, puede ser una de las muchas organizaciones que tienen varios arrendamientos. Los motivos para varios inquilinos pueden incluir fusiones y adquisiciones, desear el aislamiento administrativo o tener un descentralizado.

Si tiene varios arrendamientos de Microsoft 365, consulte estos artículos para obtener más información acerca de:

- [Colaboración entre inquilinos](microsoft-365-inter-tenant-collaboration.md)
- [Migración de buzones de inquilinos cruzados](cross-tenant-mailbox-migration.md)
- [Migraciones de espacio empresarial a espacio empresarial](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a>Paso siguiente

Inicie la planeación del espacio empresarial con [suscripciones, licencias, cuentas e inquilinos](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
