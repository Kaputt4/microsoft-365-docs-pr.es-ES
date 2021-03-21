---
title: Controles de aislamiento de Microsoft 365
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
description: Obtenga información sobre cómo funcionan los controles de aislamiento en Microsoft 365, lo que permite que los servicios entren en funcionamiento o permanezcan autónomos según sea necesario.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918947"
---
# <a name="microsoft-365-isolation-controls"></a>Controles de aislamiento de Microsoft 365 

Microsoft trabaja continuamente para garantizar que la arquitectura multiinquilino de Microsoft 365 admita estándares de seguridad, confidencialidad, privacidad, integridad, locales, internacionales y de [disponibilidad.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) La escala y el ámbito de los servicios proporcionados por Microsoft dificultan y no son económicos administrar Microsoft 365 con una interacción humana significativa. Los servicios de Microsoft 365 se proporcionan a través de varios centros de datos distribuidos globalmente, cada uno altamente automatizado con pocas operaciones que requieren un toque humano o cualquier acceso al contenido del cliente. Nuestro personal admite estos servicios y centros de datos con herramientas automatizadas y acceso remoto altamente seguro. 

Microsoft 365 se compone de varios servicios que proporcionan una funcionalidad empresarial importante y contribuyen a toda la experiencia de Microsoft 365. Cada uno de estos servicios es independiente y está diseñado para integrarse entre sí.

Microsoft 365 está diseñado con los siguientes principios:

 - **[Arquitectura orientada al servicio:](/previous-versions/aa480021(v=msdn.10))** diseño y desarrollo de software en forma de servicios interoperables que proporcionan una funcionalidad empresarial bien definida.
 - **[Garantía de](https://www.microsoft.com/download/details.aspx?id=40872)** seguridad operativa: un marco que incorpora los conocimientos adquiridos a través de diversas capacidades que son exclusivas de Microsoft, incluidos el Ciclo de vida de desarrollo de seguridad de [Microsoft,](https://www.microsoft.com/sdl/default.aspx)el Centro de respuesta de seguridad de [Microsoft](https://technet.microsoft.com/library/dn440717.aspx)y un profundo conocimiento del panorama de amenazas de ciberseguridad.

Los servicios de Microsoft 365 funcionan entre sí, pero están diseñados e implementados para que se puedan implementar y operar como servicios autónomos, independientemente entre sí. Microsoft segrega las tareas y áreas de responsabilidad de Microsoft 365 para reducir las oportunidades de modificación no autorizada o involuntaria o mal uso de los activos de la organización. Los equipos de Microsoft 365 han definido roles como parte de un mecanismo de control de acceso completo basado en roles.

## <a name="customer-content-isolation"></a>Aislamiento de contenido del cliente

Todo el contenido del cliente de un inquilino está aislado de otros inquilinos y de los datos de operaciones y sistemas usados en la administración de Microsoft 365. Se implementan varias formas de protección en Todo Microsoft 365 para minimizar el riesgo de peligro de cualquier servicio o aplicación de Microsoft 365. Varias formas de protección también impiden el acceso no autorizado a la información de los inquilinos o al propio sistema de Microsoft 365.

Para obtener información sobre cómo Microsoft implementa el aislamiento lógico de los datos de inquilino en Microsoft 365, vea [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).