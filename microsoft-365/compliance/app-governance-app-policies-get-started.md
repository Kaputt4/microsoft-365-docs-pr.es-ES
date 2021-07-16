---
title: Introducción a las directivas de aplicación
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
description: Introducción a las directivas de aplicación.
ms.openlocfilehash: 3f80048835388e740ba64ac36d1aa19594bf7a9d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420406"
---
# <a name="get-started-with-app-policies"></a>Introducción a las directivas de aplicación

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Las directivas de aplicación para la gobernanza de aplicaciones de Microsoft le permiten implementar condiciones más proactivas o reactivas a fin de crear alertas o correcciones automáticas para las necesidades específicas de cumplimiento de aplicaciones en la organización.

Para ver una lista de las directivas de aplicaciones actuales, vaya al **Centro de cumplimiento de Microsoft 365 > Protección y gobernanza de aplicaciones > Directivas**.

![La página de resumen de directivas de MAPG en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>Que información está disponible en el panel de políticas de aplicaciones

Puede ver la cantidad de directivas activas, inactivas y de prueba, así como la siguiente información para cada directiva:

- **Nombre de la directiva**
- **Estado**

  - **Activa**: todas las acciones y evaluaciones de la directiva están activas.
  - **Inactive**: todas las acciones y evaluaciones de la directiva están deshabilitadas.
  - **Modo de auditoría**: la evaluación de la directiva está en modo de auditoría. La directiva está activa, pero las acciones de directiva están deshabilitadas.

- **Gravedad**: nivel de gravedad establecido en cualquier alerta activada debido a que esta directiva se evalúa como TRUE, lo que forma parte de la configuración de la directiva.
- **Número de alertas activas**: alertas generadas por la directiva, que tienen un estado **En curso** o **Nueva**.
- **Número total de alertas**: alertas tanto activas como resueltas para esta directiva.
- **Fecha de la última alerta**: fecha de la última alerta generada por esta directiva.
- **Última modificación**: fecha en que se cambió esta directiva por última vez.

De forma predeterminada, la lista de directivas se ordena por **Última modificación**. Para ordenar la lista según otro atributo, seleccione el nombre del atributo.

Al seleccionar una directiva, verá un panel de directivas detallado con esta información adicional:

- **Descripción**: una explicación más detallada del propósito de la directiva.
- **Creada por**: nombre principal de usuario (UPN) de la cuenta que creó la directiva.
- Una lista de las alertas activas generadas por esta directiva.

Puede editar o eliminar una directiva de aplicación seleccionando **Editar** o **Eliminar** en el panel de detalles de la directiva o seleccionando los puntos suspensivos verticales de la directiva en la lista de directivas.

También puede:

- Crear una nueva directiva. Puede empezar con una directiva de uso de aplicaciones o una de permisos.
- Exporte la lista de directivas a un archivo de valores separados por comas (CSV). Por ejemplo, podría abrir el archivo CVS en Microsoft Excel y ordenar la lista de directivas por **Gravedad** y, luego, por **Número total de alertas**.
- Busque en la lista de directivas.

## <a name="next-step"></a>Paso siguiente

[Cree una directiva de aplicación.](app-governance-app-policies-create.md)
