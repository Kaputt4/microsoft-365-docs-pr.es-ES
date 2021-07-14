---
title: Obtenga información sobre las directivas de aplicación
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
description: Obtenga información sobre las directivas de aplicación.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420358"
---
# <a name="learn-about-app-policies"></a>Obtenga información sobre las directivas de aplicación

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La gobernanza de aplicaciones de Microsoft detecta un comportamiento anómalo de la aplicación en el inquilino de Microsoft 365 y genera alertas que puede ver, investigar y resolver. Más allá de esta funcionalidad de detección integrada, puede usar un conjunto de plantillas predeterminadas para crear sus propias directivas de aplicación que generen otras alertas.

Estas directivas para patrones y comportamientos de aplicaciones y usuarios pueden proteger a los usuarios contra el uso de aplicaciones no compatibles o malintencionadas y limitar el acceso de aplicaciones de riesgo a los datos del espacio empresarial.

Esta es una revisión rápida de los roles de administrador necesarios para la administración de directivas de aplicaciones.

| Función | Leer directivas | Crear, actualizar o eliminar directivas |
|:-------|:-----|:-------|
| Administrador de cumplimiento | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Lector de cumplimiento | ![Marca de verificación](..\media\checkmark.png) |  |
| Administrador global | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Lector global  | ![Marca de verificación](..\media\checkmark.png) |  |
| Administrador de seguridad | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Lector de seguridad  | ![Marca de verificación](..\media\checkmark.png) |  |
| Operador de seguridad | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a>Paso siguiente

[Introducción a las directivas de aplicación.](app-governance-app-policies-get-started.md)
