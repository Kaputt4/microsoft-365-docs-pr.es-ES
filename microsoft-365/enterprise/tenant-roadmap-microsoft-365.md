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
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909459"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Guía básica de inquilinos para Microsoft 365

Su Microsoft 365 es el conjunto de servicios asignados a su organización. Normalmente, este inquilino está asociado a uno o varios de los nombres de dominio DNS públicos y actúa como un contenedor central y aislado para distintas suscripciones y las licencias que se asignan a cuentas de usuario. Para obtener más información, vea [Suscripciones, licencias, cuentas](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)e inquilinos para las ofertas en la nube de Microsoft.

Al crear un inquilino Microsoft 365, se asigna a una ubicación geográfica específica. También puede tener un inquilino con varias ubicaciones geográficas y mover el espacio empresarial de una ubicación a otra.

Para preparar el espacio empresarial para usuarios, grupos, licencias y aplicaciones en la nube, es fundamental planear y ejecutar cuidadosamente la configuración del espacio empresarial.

## <a name="set-up-your-microsoft-365-tenant"></a>Configurar el espacio empresarial de Microsoft 365.

Después de asegurarse de que las redes están optimizadas para el acceso a Microsoft 365 tanto para los trabajadores locales como para los trabajadores remotos, las siguientes tareas grandes planean y, a continuación, configuran el inquilino de Microsoft 365 para nombres de dominio DNS, servicios comunes y para esa infraestructura de identidad que admite el inicio de sesión seguro del usuario.

### <a name="plan"></a>Planear

Para planear la implementación del espacio empresarial:

- [Comprender suscripciones, licencias y inquilinos Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Comprender cómo usar certificados SSL de terceros](plan-for-third-party-ssl-certificates.md)
- [Comprender las formas en que un inquilino Microsoft 365 está integrado con los servicios de Azure AD](integrated-apps-and-azure-ads.md)
- [Planear la compatibilidad con aplicaciones cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinar cómo usar la autenticación moderna híbrida](hybrid-modern-auth-overview.md)
- [Planear las actualizaciones Office 2007 y Office 2010](plan-upgrade-previous-versions-office.md)
- [Comprender el aislamiento de inquilino](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Implementar

Para implementar el espacio empresarial: 

- Agregue los [dominios DNS](../admin/setup/add-domain.md) de la organización.
- Use las [guías de instalación en el centro Microsoft 365 administración.](setup-guides-for-microsoft-365.md)
- Cree su infraestructura [de identidad y](identity-roadmap-microsoft-365.md) proteja los [inicios de sesión de usuario.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Mover las ubicaciones geográficas de un inquilino

Microsoft continúa abierto nuevas ubicaciones geográficas de centros de datos (geos) para Microsoft 365 servicios. Estas nuevas geos del centro de datos agregan capacidad y recursos informáticos para admitir la demanda del cliente y el crecimiento del uso. Además, las nuevas geos del centro de datos ofrecen residencia de datos en geo para los datos principales del cliente.

Para obtener más información, vea [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Implementar Microsoft 365 Multi-Geo

Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.

Para más información, vea [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Administrar varios Microsoft 365 inquilinos 

Aunque tener un único inquilino para su oganización es ideal, puede ser una de muchas organizaciones que tienen varios inquilinos. Las razones pueden incluir fusiones y adquisiciones, desea aislamiento administrativo o tiene una TI descentralizada.

Si tiene varios inquilinos Microsoft 365, vea estos artículos para obtener más información acerca de:

- [Colaboración entre inquilinos](microsoft-365-inter-tenant-collaboration.md)
- [Migración de buzones de inquilinos cruzados](cross-tenant-mailbox-migration.md)
- [Migraciones de espacio empresarial a espacio empresarial](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Paso siguiente

Inicie la planeación del espacio empresarial [con suscripciones, licencias, cuentas e inquilinos.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)