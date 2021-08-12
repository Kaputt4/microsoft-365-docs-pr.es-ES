---
title: Introducción a la detección y corrección de amenazas de aplicaciones
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
description: Introducción a la detección y corrección de amenazas de aplicaciones.
ms.openlocfilehash: 11084e54706f0c83faadf58048c205ba6ffee83e
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541242"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>Introducción a la detección y corrección de amenazas de aplicaciones

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La gobernanza de aplicaciones de Microsoft recopila alertas de amenazas generadas por métodos de detección de gobernanza de aplicaciones integrados basados en actividades de aplicaciones malintencionadas y alertas basadas en directivas generadas por las directivas de aplicación activas que cree.

El primer lugar para ver las alertas de la aplicación es el panel de gobernanza de la aplicación en [https://aka.ms/appgovernance](https://aka.ms/appgovernance).

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365 con la sección Alertas de directivas y detección resaltada](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

En esta página de descripción general, la sección de **Alertas de políticas y detección** enumera las alertas más recientes. Puede usarlo para ver rápidamente la actividad de alertas de la aplicación actual para el espacio empresarial.

Para ver todas las alertas, seleccione la pestaña de **Alertas**.

## <a name="whats-available-on-the-alerts-page"></a>Qué está disponible en la página Alertas

En la página de **Alertas** se enumeran todas las alertas basadas en la gobernanza de aplicaciones para el espacio empresarial.

![Página de resumen de alertas de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

Cada alerta de la lista tiene la siguiente información:

- **Nombre de alerta**: tipo de comportamiento anómalo.
- **Nombre de la aplicación**: la aplicación que generó la alerta.
- **Gravedad**: la gravedad asignada por la gobernanza de la aplicación para las alertas que crea o la gravedad de la directiva de aplicación que generó la alerta.
- **Origen**: origen de la alerta, que puede ser el resultado de la directiva (directivas creadas por el usuario), la detección (directivas de detección integradas) o MCAS.
- **Estado**: **Nueva** indica una alerta a la que no se le ha asignado un estado. Una vez asignado, el estado es **En curso** mientras se investiga o **Resuelto** para las alertas que se han solucionado mediante corrección automática o manual.
- **Fecha de creación**: la fecha en que la alerta fue generada por la detección de gobernanza de aplicaciones o a través de una directiva de aplicación. Todas las fechas mostradas se encuentran en la zona horaria local del Centro de cumplimiento de Microsoft 365.
- **Última actividad**: la fecha en que se cambió por última vez el estado de la alerta. Todas las fechas mostradas se encuentran en la zona horaria local del Centro de cumplimiento de Microsoft 365.

La lista de alertas se ordena por **fecha de creación** de forma predeterminada. Para ordenar la lista por otro atributo, seleccione el nombre del atributo.

También puede exportar la lista de alertas actual a un archivo de valores separados por comas (CSV). Por ejemplo, podría abrir el archivo CVS en Microsoft Excel y ordenar la lista de alertas por **Gravedad** y, a continuación, **Fecha de creación**.

## <a name="next-step"></a>Paso siguiente

[Investigar las alertas de detección de anomalías](app-governance-anomaly-detection-alerts.md)
