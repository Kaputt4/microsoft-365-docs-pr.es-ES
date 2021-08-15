---
title: Introducción a la visibilidad y la información
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
ms.openlocfilehash: 63b55b6c943d1ccd274477aff9b3327f58aade5da9e6fd4b89db2c73c21d809c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53887070"
---
# <a name="get-started-with-visibility-and-insights"></a>Introducción a la visibilidad y la información

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

El primer lugar para comenzar es el panel de gobernanza de aplicaciones en [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de estos [roles de administrador de gobernanza de aplicaciones](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

También puede acceder al panel de gobernanza de aplicaciones desde **Office 365 > Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Información general**.

## <a name="whats-available-on-the-dashboard"></a>Lo que está disponible en el panel

El panel contiene un resumen de los componentes del ecosistema de aplicaciones Microsoft 365 en el usuario:

- **Resumen de usuarios**: rel recuento de categorías de alertas y aplicaciones clave.
- **Principales alertas**: las diez alertas activas más recientes del espacio empresarial
- **Acceso a datos y recursos**: pase el mouse por cada columna de mes en el gráfico para ver el valor correspondiente.
    - **Acceso a datos durante los últimos cuatro meses**: rastrea la totalidad de datos a los que acceden las aplicaciones del espacio empresarial a través de la API de Graph durante los últimos cuatro meses naturales. Actualmente solo incluye el uso de carga y descarga de archivos y el del correo.
    - **Acceso a los datos de los recursos principales durante los últimos cuatro meses**: uso de datos de los últimos cuatro meses naturales desglosados por tipo de recurso. Actualmente solo incluye el uso de carga y descarga de archivos y el del correo.
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
