---
title: Corregir amenazas de la aplicación
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Corregir amenazas de la aplicación.
ms.openlocfilehash: 05106b9aaf790f92e8b69bfe14b393c45c934862
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193368"
---
# <a name="remediate-app-threats"></a>Corregir amenazas de la aplicación

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Las amenazas de aplicación se corrigen a su usuario de Microsoft 365 a través de la página **Alertas** de la sección de gobernanza de aplicaciones de Microsoft del Centro de cumplimiento de Microsoft 365.

![Página de resumen de alertas de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365.](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

La página **Alertas** enumera de forma predeterminada las nuevas alertas de amenazas generadas por la gobernanza de aplicaciones y las alertas basadas en directivas generadas por las directivas de aplicaciones activas. Puede ver los detalles de una alerta específica seleccionándola, lo cual abre un panel de alertas con información de alerta adicional y la capacidad de cambiar su estado.

![Página de detalle de alertas de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-alerts-alert.png)

En este panel, puede obtener esta información adicional:

- Detalles adicionales sobre la alerta del **campo de** descripción.
- Nombre de la directiva de aplicación que generó la alerta a partir del **campo** nombre de directiva. También puede seleccionar **Ver directiva** para ir a la directiva de aplicación que generó la alerta.

Las directivas de aplicación que configuró para la corrección automática desde **Acción** tendrán el estado de **Resuelto**.

Puede corregir una alerta de aplicación con estos pasos:

1. Investigación: examine la información de la alerta y cambie su estado a **Marcar en curso**.
2. Resolución: después de la investigación y, según sea necesario, la determinación de los cambios de directiva de aplicación o la asistencia continua de aplicaciones en el usuario, cambie su estado a **Resuelto**.

En función de los patrones de alerta de la aplicación, puede actualizar la directiva de aplicación adecuada y cambiar su configuración de **Acción** para realizar la corrección automática. Esto elimina la necesidad de investigar y resolver manualmente las alertas futuras que son generadas por la directiva de aplicación. Para obtener más información, consulte[Administre sus directivas de aplicación](app-governance-app-policies-manage.md).
