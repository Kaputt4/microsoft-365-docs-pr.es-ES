---
title: Determinación de la posición de cumplimiento de las aplicaciones
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
description: Determine la posición de cumplimiento de las aplicaciones.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420254"
---
# <a name="determine-your-app-compliance-posture"></a>Determinación de la posición de cumplimiento de las aplicaciones

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La gobernanza de aplicaciones de Microsoft le permite evaluar rápidamente la posición de cumplimiento de las aplicaciones de terceros, y el acceso que tienen a los datos del inquilino de Microsoft 365, desde la página de información general de gobernanza de aplicaciones del [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/appgovernance).

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> Su cuenta de inicio de sesión debe tener uno de los [estos roles](app-governance-get-started.md#administrator-roles) para ver datos de gobernanza de aplicaciones.
>

En esta página, podrá ver:

- En relación con las aplicaciones habilitadas para OAuth que usan la API de Microsoft Graph:

  - Cuántas están en el inquilino
  - Cuántas podrían tener privilegios excesivos
  - Cuántas tienen privilegios elevados

  A partir de esta información, puede determinar el nivel de riesgo para su organización a causa de las aplicaciones con privilegios excesivos y elevados.

- En relación con las alertas:

  - Cuántas alertas activas tiene el inquilino
  - Cuántas se basan en las detecciones de gobernanza de aplicaciones (**alertas de amenazas**)
  - Cuántas se basan en las directivas de aplicaciones que tiene implementadas (**alertas de directivas**)
  - Las 10 alertas más recientes

  A partir de esta información, puede determinar la rapidez con la que se generan las alertas y la cantidad relativa de alertas detectadas y basadas en directivas.

- En relación con el acceso a los datos y los recursos:

  - El acceso a los datos de la API de la aplicación en los últimos 90 días
  - El uso de los recursos principales en los últimos 90 días

  A partir de esta información, puede determinar si hay picos anómalos en el acceso a los datos del inquilino de Microsoft 365.
