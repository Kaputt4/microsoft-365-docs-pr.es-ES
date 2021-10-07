---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: En este artículo, obtenga información sobre cómo expandir su Microsoft 365 a varias regiones geográficas con Microsoft 365 Multi-Geo.
ms.openlocfilehash: 5122979fc79ce9aebe542a80ed614e7dcad70d03
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198426"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

Con Microsoft 365 Multi-Geo, su organización puede expandir su presencia en Microsoft 365 a varias regiones geográficas y países dentro de su espacio empresarial existente. Póngase en contacto con su equipo de cuentas de Microsoft para registrar su compañía multinacional a Microsoft 365 Multi-Geo.
  
Con Microsoft 365 Multi-Geo, puede aprovisionar y almacenar los datos en reposo en las ubicaciones geográficas que haya elegido para cumplir los requisitos de residencia de datos y, al mismo tiempo, puede permitir la implementación global de experiencias de productividad modernas para sus empleados.

Para obtener una introducción en vídeo Microsoft 365 Multi-Geo, vea [SharePoint Online y OneDrive Multi-Geo para controlar dónde residen los datos](https://www.youtube.com/watch?v=Do9U3JuROhk).

## <a name="multi-geo-architecture"></a>Arquitectura multigeósica

En un entorno multigeográfico, su espacio empresarial de Microsoft 365 cuenta con una ubicación central (donde se aprovisionó originalmente la suscripción a Microsoft 365) y una o varias ubicaciones satélites. En un espacio empresarial multigeográfico, la información sobre las ubicaciones geográficas, grupos y la información de usuario, se controla en Azure Active Directory (Azure AD). Como la información del espacio empresarial se controla de forma centralizada y se sincroniza en cada ubicación geográfica, el uso compartido y las experiencias que involucran a todos los empleados de su compañía comparten una conciencia global.

![Captura de pantalla del mapa multige SharePoint centro de administración.](../media/multi-geo-world-map.png)

Tenga en cuenta que Microsoft 365 Multi-Geo no está diseñado principalmente para optimizar el rendimiento, sino para cumplir con los requisitos de residencia de datos. Para obtener información sobre la optimización del rendimiento de Microsoft 365, vea [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) (Planeamiento de red y ajuste de rendimiento para Microsoft 365) o póngase en contacto con su grupo de soporte técnico.

## <a name="terminology"></a>Terminología

Estos son los términos clave utilizados para describir Microsoft 365 Multi-Geo:

- **Ubicación central**: la ubicación geográfica en la que se ha aprovisionado originalmente el espacio empresarial.
- **Administrador geográfico**: un administrador que puede administrar una o varias ubicaciones satélites especificadas.
- **Código geográfico**: un código de tres letras de una ubicación geográfica determinada.
- **Ubicación geográfica**: una ubicación geográfica que puede usarse en un espacio empresarial multigeográfico para alojar datos, como los buzones de Exchange y los sitios de SharePoint y OneDrive.
- **Ubicación de datos preferida (PDL)**: una propiedad de usuario que establece el administrador e indica la ubicación geográfica donde se deben aprovisionar los buzones de Exchange de usuarios y OneDrive. La PDL también determina dónde aprovisionar sitios de SharePoint creados por el usuario.
- **Ubicación satélite**: las ubicaciones geográficas donde están habilitadas las cargas de trabajo compatibles geográficamente de Microsoft 365 (Exchange, OneDrive y SharePoint) en un espacio empresarial multigeográfico.
- **Cuenta empresarial**: la representación de una organización de Microsoft 365, que suele tener uno o más dominios asociados (por ejemplo, contoso.com).

## <a name="licensing"></a>Licencias

Microsoft 365 Multi-Geo está disponible como complemento a los siguientes planes de suscripción de Microsoft 365 para clientes de Enterprise Agreement con un mínimo de 250 puestos Microsoft 365 en su inquilino y un mínimo del 5 % de esos puestos con multigefia. Las licencias de suscripción de usuario deben estar en el mismo Enterprise Agreement que las licencias de servicios multigeómicos. Póngase en contacto con el equipo de su cuenta de Microsoft para obtener más información.

- Microsoft 365 F1, F3, E3 o E5
- Office 365 F3, E1, E3 o E5
- Exchange Online (plan 1 o plan 2)
- OneDrive para la Empresa (plan 1 o plan 2)
- SharePoint Online (plan 1 o plan 2)

Si se asigna una licencia a un usuario y se quita posteriormente, Teams datos de chat de usuario se ponen en cola para volver a la ubicación central. SharePoint y Exchange datos no se mueven.

## <a name="microsoft-365-multi-geo-availability"></a>Disponibilidad de Microsoft 365 Multi-Geo

Actualmente, se ofrece Microsoft 365 Multi-Geo en estos países y regiones:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Introducción

Siga estos pasos para empezar a usar Multi-Geo:

1. Trabaje con el equipo de cuentas para agregar el plan de servicio _Funciones multigeográficas en Microsoft 365_. Le guiará para agregar el número de licencias necesarias. La característica multigeográfica está disponible actualmente para los clientes EA con un mínimo de 250 suscripciones a Microsoft 365.

   Antes de empezar a usar Microsoft 365 Multi-Geo, Microsoft necesita configurar el espacio empresarial de Exchange Online para la compatibilidad con Multi-Geo. Este proceso de configuración única se activa después de pedir el plan de servicio de las *Capacidades multigeográficas de Microsoft 365* y después de que las licencias se muestren en el espacio empresarial. Recibirá notificaciones específicas de la carga de trabajo en el centro de mensajes de Microsoft 365 una vez que el inquilino haya completado el proceso de configuración de cada carga de trabajo y, a continuación, pueda empezar [a](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) configurar y usar las capacidades multigeós de Microsoft 365. El tiempo necesario para configurar un espacio empresarial para la compatibilidad multigeón varía de inquilino a inquilino, pero la mayoría de los inquilinos finalizan en un mes después de la recepción de las licencias de características. Es posible que los inquilinos más grandes o más complejos necesiten más tiempo para completar el proceso de configuración. Póngase en contacto con el equipo de su cuenta para obtener más información sobre su inquilino específico en caso de que lo necesite.

2. Lea [Planificar el entorno multigeográfico](plan-for-multi-geo.md).

3. Obtenga información sobre cómo [administrar un entorno multigeográfico](administering-a-multi-geo-environment.md) y [cómo los usuarios experimentarán el entorno](multi-geo-user-experience.md).

4. Cuando esté listo para configurar Microsoft 365 Multi-Geo, [configure su espacio empresarial multigeográfico](multi-geo-tenant-configuration.md).

5. [Configure la búsqueda](configure-search-for-multi-geo.md).

## <a name="see-also"></a>Vea también

[Capacidades multigeográficas en Exchange Online y OneDrive](https://Aka.ms/GoMultiGeo)

[Capacidades multigeográficas de OneDrive y SharePoint Online](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Capacidades multigeográficas de Exchange Online](multi-geo-capabilities-in-exchange-online.md)

[Experiencia de equipos en un entorno multigeo](/microsoftteams/teams-experience-o365odb-spo-multi-geo)