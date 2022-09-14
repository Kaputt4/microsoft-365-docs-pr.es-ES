---
title: Plan de desarrollo de inquilinos para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La hoja de ruta para configurar los inquilinos para Microsoft 365.
ms.openlocfilehash: 679d88d00bd0b806ec5b1be098ddad7bee2d82d0
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67672015"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Plan de desarrollo de inquilinos para Microsoft 365

El inquilino de Microsoft 365 es el conjunto de servicios asignados a su organización. Normalmente, este inquilino está asociado a uno o varios de los nombres de dominio DNS públicos y actúa como un contenedor central y aislado para distintas suscripciones y las licencias que se asignan a las cuentas de usuario. Para obtener más información, consulte [Suscripciones, licencias, cuentas e inquilinos para las ofertas en la nube de Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

Al crear un inquilino de Microsoft 365, se asigna a una ubicación geográfica específica. También puede tener un inquilino con varias ubicaciones geográficas y mover el inquilino de una ubicación a otra.

Para preparar el inquilino para usuarios, grupos, licencias y aplicaciones en la nube, es fundamental planear y ejecutar cuidadosamente la configuración del inquilino.

## <a name="set-up-your-microsoft-365-tenant"></a>Configurar el espacio empresarial de Microsoft 365.

Después de asegurarse de que las redes están optimizadas para el acceso a Microsoft 365 tanto para trabajadores locales como remotos, las siguientes grandes tareas planean y, a continuación, configuran el inquilino de Microsoft 365 para nombres de dominio DNS, servicios comunes y para esa infraestructura de identidad que admite el inicio de sesión de usuario seguro.

### <a name="plan"></a>Plan

Para planear la implementación del inquilino:

- [Descripción de las suscripciones, las licencias y los inquilinos de Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Información sobre cómo usar certificados SSL de terceros](plan-for-third-party-ssl-certificates.md)
- [Descripción de las formas en que un inquilino de Microsoft 365 se integra con los servicios de Azure AD](integrated-apps-and-azure-ads.md)
- [Planeamiento de la compatibilidad con aplicaciones cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinación de cómo usar la autenticación moderna híbrida](hybrid-modern-auth-overview.md)
- [Planear actualizaciones de Office 2007 y Office 2010](plan-upgrade-previous-versions-office.md)
- [Descripción del aislamiento de inquilinos](/compliance/assurance/assurance-microsoft-365-isolation-controls#tenant-isolation)

### <a name="deploy"></a>Implementar

Para implementar el inquilino: 

- Agregue los [dominios DNS](../admin/setup/add-domain.md) para su organización.
- Use las [guías de configuración de la Centro de administración de Microsoft 365](setup-guides-for-microsoft-365.md).
- Compile la [infraestructura de identidad](deploy-identity-solution-overview.md).

### <a name="move-a-tenants-geographic-locations"></a>Mover las ubicaciones geográficas de un inquilino

Microsoft continúa abriendo nuevas ubicaciones geográficas del centro de datos para los servicios de Microsoft 365. Estas nuevas zonas geográficas del centro de datos agregan recursos de capacidad y proceso para admitir la demanda y el crecimiento del uso de los clientes. Además, las nuevas zonas geográficas del centro de datos ofrecen residencia de datos en la ubicación geográfica para los datos principales de los clientes.

Para obtener más información, consulte [Traslado de datos principales a nuevas geoáreas del centro de datos de Microsoft 365](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Implementación multigeográfica de Microsoft 365

Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia de Microsoft 365 a varias regiones geográficas y/o países dentro de su inquilino existente.

Para más información, vea [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Administración de varios inquilinos de Microsoft 365 

Aunque tener un único inquilino para su organización es ideal, puede ser una de las muchas organizaciones que tienen varios inquilinos. Las razones pueden incluir fusiones y adquisiciones, desea aislamiento administrativo o una TI descentralizada.

Si tiene varios inquilinos de Microsoft 365, consulte estos artículos para obtener más información sobre:

- [Colaboración entre inquilinos](microsoft-365-inter-tenant-collaboration.md)
- [Migración de buzones de inquilinos cruzados](cross-tenant-mailbox-migration.md)
- [Migraciones de espacio empresarial a espacio empresarial](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Paso siguiente

Inicie el planeamiento de [inquilinos con suscripciones, licencias, cuentas e inquilinos](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
