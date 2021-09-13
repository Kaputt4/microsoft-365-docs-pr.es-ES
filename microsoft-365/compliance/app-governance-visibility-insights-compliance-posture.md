---
title: Determinación de la posición de cumplimiento de las aplicaciones
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
description: Determine la posición de cumplimiento de las aplicaciones.
ms.openlocfilehash: 4cc54e5ea0fdaf0a8a196b90b09e2e8be970c7c1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190017"
---
# <a name="determine-your-app-compliance-posture"></a>Determinación de la posición de cumplimiento de las aplicaciones

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La gobernanza de aplicaciones de Microsoft le permite evaluar rápidamente la posición de cumplimiento de las aplicaciones de terceros, y el acceso que tienen a los datos del inquilino de Microsoft 365, desde la página de información general de gobernanza de aplicaciones del Centro de cumplimiento de Microsoft 365.

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365.](..\media\manage-app-protection-governance\mapg-cc-overview.png)

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

  - Datos totales a los que acceden las aplicaciones del inquilino a través de la API de Graph durante los tres meses naturales actuales y anteriores. (Actualmente solo incluye el uso de carga y descarga de correo y archivos)
  - Uso de datos durante los tres meses naturales actuales y anteriores, desglosados por tipo de recurso. (Actualmente solo incluye el uso de carga y descarga de correo y archivos)

  A partir de esta información, puede determinar si hay picos anómalos en el acceso a los datos del inquilino de Microsoft 365.
