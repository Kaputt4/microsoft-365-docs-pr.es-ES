---
title: Aislamiento de inquilinos en Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Este artículo contiene un resumen de cómo Microsoft aplica el aislamiento de inquilinos en servicios en la nube como Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384935"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Aislamiento de inquilinos en Microsoft 365

Una de las principales ventajas de la informática en la nube es el concepto de una infraestructura común y compartida entre numerosos clientes al mismo tiempo, lo que lleva a la escala. Este concepto se denomina *multiinquilino.* Microsoft trabaja continuamente para garantizar que las arquitecturas multiinquilino de nuestros servicios en la nube admitan estándares de seguridad, confidencialidad, privacidad, integridad y disponibilidad a nivel empresarial.

En función de las inversiones y la experiencia significativas recopiladas de [Trustworthy Computing](https://www.microsoft.com/trust-center) y el ciclo de vida de desarrollo de [seguridad,](https://www.microsoft.com/securityengineering/sdl/)los servicios en la nube de Microsoft se diseñaron con la suposición de que todos los inquilinos son potencialmente diferentes a todos los demás inquilinos, y hemos implementado medidas de seguridad para evitar que las acciones de un inquilino afecten a la seguridad o al servicio de otro inquilino, o accedan al contenido de otro inquilino.

Los dos objetivos principales de mantener el aislamiento de inquilinos en un entorno multiinquilino son:

1.    Evitar la filtración de contenido de clientes o el acceso no autorizado a ellos en todos los inquilinos; y
2.    Impedir que las acciones de un inquilino afecten negativamente al servicio de otro inquilino

Se han implementado varias formas de protección en Todo Microsoft 365 para evitar que los clientes puedan poner en peligro los servicios o aplicaciones de Microsoft 365 o obtener acceso no autorizado a la información de otros inquilinos o del propio sistema de Microsoft 365, incluidos:

- El aislamiento lógico del contenido del cliente en cada inquilino para los servicios de Microsoft 365 se logra a través de la autorización de Azure Active Directory y el control de acceso basado en roles.
- SharePoint Online proporciona mecanismos de aislamiento de datos en el nivel de almacenamiento.
- Microsoft usa la seguridad física rigurosa, el filtrado en segundo plano y una estrategia de cifrado de varias capas para proteger la confidencialidad y la integridad del contenido del cliente. Todos los centros de datos de Microsoft 365 tienen controles de acceso biométrico, con la mayoría de las huellas de palma que requieren para obtener acceso físico. Además, todos los empleados de Microsoft basados en Estados Unidos deben completar correctamente una comprobación de antecedentes estándar como parte del proceso de contratación. Para obtener más información sobre los controles usados para el acceso administrativo en Microsoft 365, vea Controles de acceso administrativo [de Microsoft 365.](microsoft-365-administrative-access-controls-overview.md)
- Microsoft 365 usa tecnologías del lado del servicio que cifran el contenido del cliente en reposo y en tránsito, incluido BitLocker, cifrado por archivo, Seguridad de la capa de transporte (TLS) y seguridad de protocolo de Internet (IPsec). Para obtener detalles específicos sobre el cifrado en Microsoft 365, vea Tecnologías de cifrado [de datos en Microsoft 365.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)

Juntas, las protecciones mencionadas anteriormente proporcionan sólidos controles de aislamiento lógico que proporcionan protección contra amenazas y mitigación equivalentes a las proporcionadas solo por el aislamiento físico.

## <a name="related-links"></a>Vínculos relacionados

- [Aislamiento y Control de acceso en Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Aislamiento del inquilino en Office Graph y Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Aislamiento de inquilino en Búsqueda de Microsoft 365](microsoft-365-isolation-in-microsoft-365-search.md)
- [Aislamiento del inquilino en Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Límites de recursos](microsoft-365-resource-limits.md)
- [Supervisar y probar los límites de inquilinos](microsoft-365-monitoring-and-testing.md)
- [Aislamiento y control de acceso en Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)
