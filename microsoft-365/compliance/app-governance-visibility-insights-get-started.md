---
title: Introducción a la visibilidad y la información
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Introducción a la visibilidad y la información.
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430485"
---
# <a name="get-started-with-visibility-and-insights"></a>Introducción a la visibilidad y la información

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

El primer lugar para comenzar es el panel de gobernanza de aplicaciones en [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de estos [roles de administrador de gobernanza de aplicaciones](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

También puede acceder al panel de gobernanza de aplicaciones desde **Centro de administración de Microsoft 365 > Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Información general**.

## <a name="whats-available-on-the-dashboard"></a>Lo que está disponible en el panel

El panel contiene un resumen de los componentes del ecosistema de aplicaciones Microsoft 365 en el usuario:

- **Resumen de usuarios**: rel recuento de categorías de alertas y aplicaciones clave.
- **Alertas de directiva y detección**: las alertas activas más recientes en el usuario
- **Acceso a datos y recursos**: agregue el acceso a la API de la aplicación y al uso general de los recursos principales del usuario. Pase el mouse por cada columna de mes en el gráfico para ver el valor correspondiente.
- **Mejore la protección y la gobernanza de sus aplicaciones**: acciones recomendadas tales como la creación de una directiva de permisos o de uso de aplicaciones.
- **Principales aplicaciones por categorías**: las aplicaciones principales ordenadas por estas categorías:
  
  - **Todas las categorías**: se ordena entre todas las categorías disponibles.
  - **Privilegios elevados**: privilegios elevados es una categoría determinada internamente basada en el aprendizaje automático y las señales de la plataforma.
  - **Privilegios excesivos**: cuando la gobernanza de aplicaciones recibe datos de telemetría que indican que no se ha usado un permiso concedido a una aplicación en los últimos 90 días, esa aplicación tiene privilegios excesivos. La gobernanza de aplicaciones debe funcionar durante al menos 90 días para determinar si alguna aplicación tiene privilegios excesivos.  
  - **Sin verificar**: las aplicaciones que no han recibido [certificación de editorial](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) se consideran sin verificar.
  - **Solo aplicaciones**: [los permisos de aplicaciones](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) se utilizan por aplicaciones que pueden ejecutarse sin un usuario que haya iniciado sesión. Las aplicaciones con permisos para acceder a los datos en el usuario son potencialmente de mayor riesgo.
  - **Aplicaciones nuevas**: nuevas aplicaciones de Microsoft 365 que se han registrado en los últimos siete días.  

## <a name="next-step"></a>Paso siguiente

[Obtenga información detallada sobre una aplicación específica](app-governance-visibility-insights-view-apps.md).
