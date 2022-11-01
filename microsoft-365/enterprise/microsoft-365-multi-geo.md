---
title: Microsoft 365 Multi-Geo
ms.reviewer: anfra
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: En este artículo, obtendrá información sobre cómo expandir la presencia de Microsoft 365 a varias regiones geográficas con Microsoft 365 Multi-Geo.
ms.openlocfilehash: f663d95b6d1d714b0b144d32736013885a7aad87
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804956"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

El complemento Funcionalidades multigeográficas de Microsoft 365 proporciona a los clientes la capacidad de expandir su presencia de Microsoft 365 a varias regiones geográficas o condados dentro de un único _inquilino_ de Microsoft 365 existente. Multi-Geo permite a los clientes administrar ubicaciones de datos en reposo en un nivel granular para sus usuarios, sitios de SharePoint, Grupos de Microsoft 365 y los equipos de Microsoft Teams. Multi-Geo está dirigido a clientes que necesitan almacenar datos de clientes en varias zonas geográficas al mismo tiempo para satisfacer sus requisitos de residencia de datos y cuyas necesidades pueden cambiar con el tiempo.
  
Microsoft 365 Multi-Geo está diseñado para satisfacer los requisitos de residencia de datos de los clientes y permitir la colaboración entre y entre los clientes ubicación satélite y ubicaciones de datos preferidas. Si el cliente requiere funcionalidades de optimización de rendimiento para Microsoft 365, consulte <a href="https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848" target="_blank">Planeamiento de red y optimización del rendimiento para Microsoft 365</a> o póngase en contacto con el grupo de soporte técnico.

>[!NOTE]
>Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams están disponibles para la configuración multigeográfica. Consulte las secciones compromiso de residencia de datos para [Exchange Online](m365-dr-workload-exo.md), [SharePoint Online y OneDrive para la Empresa](m365-dr-workload-spo.md), y [Microsoft Teams](m365-dr-workload-teams.md#data-residency-commitments-available) para obtener más detalles.

Para ver un vídeo de introducción a Microsoft 365 Multi-Geo, consulte [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).

## <a name="multi-geo-architecture"></a>Arquitectura de Multi-Geo

En un entorno multigeográfico, el _inquilino_ de Microsoft 365 consta de una ubicación central (donde se aprovisionó originalmente la suscripción de Microsoft 365) y una o varias ubicaciones satélite. En un _inquilino_ habilitado para varias zonas geográficas, la información sobre las ubicaciones geográficas, los grupos y la información de usuario se domina en Azure Active Directory (Azure AD). Dado que la información _del inquilino_ se domina de forma centralizada y se sincroniza en cada ubicación geográfica, el uso compartido y las experiencias que implican a cualquier usuario de la empresa contienen reconocimiento global.

![Recorte de pantalla del mapa multigeográfico desde el Centro de administración de SharePoint](../media/multi-geo-world-map.png)

## <a name="licensing"></a>Licencias

Microsoft 365 Multi-Geo está disponible como complemento a los siguientes planes de suscripción de Microsoft 365 para Enterprise Agreement clientes. Los clientes deben comprar una serie de licencias multigeográficas iguales o superiores al 5 % de sus puestos elegibles totales. Las licencias de suscripción del usuario deben estar en el mismo Contrato Enterprise que las licencias de Multi-Geo Services. Póngase en contacto con el equipo de su cuenta de Microsoft para obtener más información.

- Microsoft 365 F1, F3, E3 o E5
- Office 365 F3, E1, E3 o E5
- Exchange Online (plan 1 o plan 2)
- OneDrive para la Empresa (plan 1 o plan 2)
- SharePoint Online (plan 1 o plan 2)

Tenga en cuenta que las _funcionalidades multigeográficas del plan de Microsoft 365_ son una licencia de complemento de nivel de usuario. Necesita una licencia para cada usuario que quiera hospedar en una ubicación _de Geografía satélite_ . Puede agregar licencias adicionales a lo largo del tiempo a medida que agregue usuarios en ubicaciones _de Geografía satélite_ .

No hay licencias multigeográficas específicas para recursos compartidos, como sitios de SharePoint, Grupos de Microsoft 365 o equipos de Microsoft Teams. Si se han adquirido suficientes licencias de usuario multigeográficas, los clientes pueden usar multigeográficas con sitios de SharePoint, Grupos de Microsoft 365 y equipos de Microsoft Teams sin limitación.

## <a name="microsoft-365-multi-geo-availability"></a>Disponibilidad de Microsoft 365 Multi-Geo

Actualmente, se ofrece Microsoft 365 Multi-Geo en estos países y regiones:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Introducción

Siga estos pasos para empezar a trabajar con multigeográfica:

1. Trabaje con el equipo de cuentas para agregar el plan de servicio _Funciones multigeográficas en Microsoft 365_. Le guiará para agregar el número de licencias necesarias. La característica multigeográfica está disponible para Enterprise Agreement clientes.

2. Antes de empezar a usar Microsoft 365 Multi-Geo, Microsoft debe configurar el _inquilino_ de Exchange Online para la compatibilidad multigeográfica. Este proceso de configuración de un solo uso se desencadena después de ordenar las _funcionalidades multigeográficas en_ el plan de servicio de Microsoft 365 y las licencias se muestran en el _inquilino_. Recibirá notificaciones específicas de la carga de trabajo en el Centro de mensajes de [Microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) una vez que el _inquilino_ haya completado el proceso de configuración de cada carga de trabajo y, a continuación, puede empezar a configurar y usar las funcionalidades multigeográficas de Microsoft 365. El tiempo necesario para configurar un _inquilino_ para la compatibilidad multigeográfica varía de _inquilino_ a _inquilino_, pero la mayoría de _los inquilinos_ finalizan en un mes después de recibir las licencias de características. _Los inquilinos_ más grandes o más complejos pueden requerir más tiempo para completar el proceso de configuración. Póngase en contacto con el equipo de su cuenta para obtener más información sobre su _inquilino_ específico en caso de que lo necesite.

3. Lea [Planificar el entorno multigeográfico](plan-for-multi-geo.md).

4. Obtenga información sobre cómo [administrar un entorno multigeográfico](administering-a-multi-geo-environment.md) y [cómo los usuarios experimentarán el entorno](multi-geo-user-experience.md).

5. Cuando esté listo para configurar Microsoft 365 Multi-Geo, [configure su espacio empresarial multigeográfico](multi-geo-tenant-configuration.md).

6. [Configure la búsqueda](configure-search-for-multi-geo.md).
  
> [!NOTE]
> Para obtener más información sobre los servicios de Microsoft 365 que admiten multigeográfica, consulte las páginas de residencia de datos de cargas de trabajo [exo](m365-dr-workload-exo.md), [ODSP](m365-dr-workload-spo.md) y [Teams](m365-dr-workload-teams.md) para obtener más información.


## <a name="see-also"></a>Vea también

[Capacidades multigeográficas en Exchange Online y OneDrive](https://Aka.ms/GoMultiGeo)

[Capacidades multigeográficas de OneDrive y SharePoint Online](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Capacidades multigeográficas de Exchange Online](multi-geo-capabilities-in-exchange-online.md)

[Experiencia de equipos en un entorno multigeo](/microsoftteams/teams-experience-o365odb-spo-multi-geo)
