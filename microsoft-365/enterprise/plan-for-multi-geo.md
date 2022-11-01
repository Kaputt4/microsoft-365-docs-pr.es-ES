---
title: Plan para Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Obtenga información acerca de Microsoft 365 Multi-Geo, cómo funcionan las capacidades multigeográficas y qué ubicaciones geográficas están disponibles para el almacenamiento de datos.
ms.openlocfilehash: bc742ebc77f5b28fe10f071e66d2e9753f8ced47
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804934"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Plan para Microsoft 365 Multi-Geo

Esta guía está diseñada para que los administradores de _inquilinos_ que preparen su _inquilino_ de Microsoft 365 se expandan a zonas geográficas adicionales de acuerdo con la necesidad de la empresa de cumplir los requisitos de residencia de datos.

En una configuración multigeográfica, el _inquilino_ de Microsoft 365 consta de una ubicación geográfica _aprovisionada principal_ y una o varias ubicaciones _de geografía satélite_ . Se trata de un único _inquilino_ que abarca varias ubicaciones _geography_ .

Para ayudarle a comprender los conceptos básicos de la configuración multigeográfica, revise los términos de la sección Definiciones de la [página Información general y definiciones](m365-dr-overview.md).

Para habilitar Capacidades multigeográficas es necesario completar cuatro pasos principales:

1. Trabaje con el equipo de cuentas para agregar el plan de servicio _Funciones multigeográficas en Microsoft 365_.

2. Elija las ubicaciones de _geografía satélite_ deseadas y agréguelas al _inquilino_.

3. Establezca la ubicación de datos preferida de los usuarios en la ubicación _de geografía satélite_ deseada. Cuando se aprovisiona un nuevo sitio de OneDrive para la Empresa o un buzón de Exchange Online para un usuario, se aprovisiona en su PDL.

4. Migre los sitios de OneDrive para la Empresa existentes de los usuarios desde la ubicación _Geografía aprovisionada principal_ a su ubicación de datos _Geografía satélite_ según sea necesario. (Exchange Online buzones se migran automáticamente cuando se establece la PDL de un usuario).

Para obtener más información sobre estos pasos, vea [Configuración de Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md).

Vea la [sección Disponibilidad](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability) de la página De información general multigeográfica de M365 para las _zonas geográficas_ que pueden ser una ubicación de _geografía satélite_ donde puede hospedar sitios de OneDrive para la Empresa y SharePoint Online, buzones de Exchange Online y Microsoft Teams. A medida que planee multigeográfica, haga una lista de las ubicaciones que desea agregar a su _inquilino_ de Microsoft 365. Se recomienda empezar con una o dos ubicaciones por satélite y expandirse gradualmente a más ubicaciones geográficas según sea preciso.

## <a name="best-practices"></a>Procedimientos recomendados

Se recomienda crear un usuario de prueba de Microsoft 365 para realizar algunas pruebas iniciales. Le guiaremos por algunos pasos de prueba y verificación con este usuario antes de continuar con la incorporación de usuarios de producción a Microsoft 365 Multi-Geo.

Una vez que haya completado las pruebas con el usuario de prueba, seleccione un grupo piloto (quizás del departamento de TI) para ser el primero en usar OneDrive para la Empresa y Exchange Online en una nueva ubicación geográfica. Para este primer grupo, seleccione los usuarios que aún no tienen un OneDrive para la Empresa. Le recomendamos que este grupo inicial no tenga más de cinco personas y que lo extienda gradualmente siguiendo un enfoque de lanzamiento por lotes.

Cada usuario debe tener establecida una _ubicación de datos preferida_ (PDL) para que Microsoft 365 pueda determinar en qué ubicación _geográfica_ aprovisionar su OneDrive. La ubicación de datos preferida del usuario debe coincidir con una de las ubicaciones _de geografía satélite_ elegidas o con la _geografía aprovisionada principal_. Aunque el campo PDL no es obligatorio, se recomienda establecer una PDL para todos los usuarios. Las cargas de trabajo de un usuario sin UNA PDL se aprovisionarán en la _geografía aprovisionada principal_.

Cree una lista de los usuarios e incluya su nombre principal de usuario (UPN) y el código de ubicación para la ubicación de datos preferida adecuada. Incluya el usuario de prueba y el grupo piloto inicial con el que empezar. Necesitará esta lista para los procedimientos de configuración.

Si los usuarios se sincronizan desde un sistema de Active Directory local con Azure Active Directory, debe establecer la ubicación de datos preferida como un atributo de Active Directory y sincronizarla mediante el uso de Azure Active Directory Connect. No puede configurar directamente la ubicación de datos preferida para los usuarios sincronizados utilizando Azure AD PowerShell. Se tratan los pasos para configurar PDL en Active Directory y sincronizarlas en [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation) (Sincronización con Azure Active Directory Connect: configuración de ubicación de datos preferida para Recursos de Microsoft 365).

La administración de un _inquilino multigeográfico_ puede diferir de un _inquilino_ no multigeográfico, ya que muchos de los servicios y la configuración de SharePoint Online y OneDrive para la Empresa son multigeográficos. Se recomienda revisar [Administración de un entorno multigeográfico antes de](administering-a-multi-geo-environment.md) continuar con la configuración.

Lea [Experiencia del usuario en un entorno multigeográfico](multi-geo-user-experience.md) para obtener más información sobre la experiencia de los usuarios finales en un entorno multigeográfico.

Para empezar a configurar Microsoft 365 Multi-Geo, consulte [Configuración de Microsoft 365 Multi-Geo5](multi-geo-tenant-configuration.md).

Cuando complete la configuración, recuerde [migrar las bibliotecas de OneDrive de los usuarios](move-onedrive-between-geo-locations.md) según sea necesario para que los usuarios puedan trabajar desde sus ubicaciones de datos preferidas.

## <a name="related-topics"></a>Temas relacionados

[Configuración de eDiscovery de Microsoft 365 Multi-Geo](./multi-geo-ediscovery-configuration.md)
