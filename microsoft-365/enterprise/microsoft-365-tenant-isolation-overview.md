---
title: Aislamiento de inquilino en Microsoft 365
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
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923081"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Aislamiento de inquilino en Microsoft 365

Una de las principales ventajas de la informática en la nube es el concepto de una infraestructura común y compartida entre numerosos clientes simultáneamente, lo que lleva a economías de escala. Este concepto se denomina *multiinquilino*. Microsoft trabaja continuamente para garantizar que las arquitecturas multiinquilino de nuestros servicios en la nube admiten estándares de seguridad, confidencialidad, privacidad, integridad y disponibilidad a nivel empresarial.

En función de las importantes inversiones y la experiencia obtenidas de [trustworthy Computing](https://www.microsoft.com/trust-center) y el ciclo de vida de desarrollo de [seguridad,](https://www.microsoft.com/securityengineering/sdl/)los servicios en la nube de Microsoft se diseñaron con la suposición de que todos los inquilinos son potencialmente agresivos para todos los demás inquilinos, y hemos implementado medidas de seguridad para evitar que las acciones de un inquilino afecten a la seguridad o el servicio de otro inquilino, o accedan al contenido de otro inquilino.

Los dos objetivos principales de mantener el aislamiento de inquilinos en un entorno multiinquilino son:

1.    Impedir la filtración o el acceso no autorizado al contenido del cliente entre inquilinos; y
2.    Impedir que las acciones de un inquilino afecten negativamente al servicio de otro inquilino

Se han implementado varias formas de protección a lo largo de Microsoft 365 para impedir que los clientes puedan poner en peligro los servicios o aplicaciones de Microsoft 365 o obtener acceso no autorizado a la información de otros inquilinos o del propio sistema Microsoft 365, incluidos:

- El aislamiento lógico del contenido del cliente dentro de cada espacio empresarial para Microsoft 365 servicios se logra Azure Active Directory autorización y control de acceso basado en roles.
- SharePoint Online proporciona mecanismos de aislamiento de datos en el nivel de almacenamiento.
- Microsoft usa una seguridad física rigurosa, un filtrado en segundo plano y una estrategia de cifrado multicapa para proteger la confidencialidad y la integridad del contenido del cliente. Todos Microsoft 365 centros de datos tienen controles de acceso biométricos, con la mayoría de las impresiones de la palma para obtener acceso físico. Además, todos los empleados de Microsoft con sede en Estados Unidos deben completar correctamente una comprobación de antecedentes estándar como parte del proceso de contratación. Para obtener más información sobre los controles usados para el acceso administrativo en Microsoft 365, vea [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).
- Microsoft 365 usa tecnologías del lado del servicio que cifran el contenido del cliente en reposo y en tránsito, incluidos BitLocker, cifrado por archivo, Seguridad de la capa de transporte (TLS) y Seguridad de protocolos de Internet (IPsec). Para obtener detalles específicos sobre el cifrado en Microsoft 365, vea [Tecnologías de cifrado de datos en Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).

Juntos, las protecciones mencionadas anteriormente proporcionan controles de aislamiento lógico robustos que proporcionan protección contra amenazas y mitigación equivalentes a las proporcionadas por el aislamiento físico solo.

## <a name="related-links"></a>Vínculos relacionados

- [Aislamiento y Control de acceso en Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Aislamiento del inquilino en Office Graph y Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Aislamiento de inquilino en Búsqueda de Microsoft 365](microsoft-365-isolation-in-microsoft-365-search.md)
- [Aislamiento del inquilino en Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Límites de recursos](/compliance/assurance/assurance-resource-limits)
- [Supervisar y probar los límites de inquilinos](/compliance/assurance/assurance-monitoring-and-testing)
- [Aislamiento y control de acceso en Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)