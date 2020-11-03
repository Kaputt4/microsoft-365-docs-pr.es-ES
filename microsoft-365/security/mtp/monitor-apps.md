---
title: 'Supervisión de aplicaciones & de informes: Centro de seguridad'
description: Obtenga información sobre cómo obtener más información sobre el uso de aplicaciones en la nube en la organización. Incluye distintos tipos de aplicaciones, su nivel de riesgo y alertas.
keywords: seguridad, malware, Microsoft 365, M365, Security Center, monitor, Report, apps
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcb7997c8c248c2b4e7d16902b6ebdd7756ccd0b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846633"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Supervisión y generación de informes de aplicaciones en el centro de seguridad de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Estos informes proporcionan más información sobre cómo se usan las aplicaciones en la nube en la organización. Incluye distintos tipos de aplicaciones, su nivel de riesgo y alertas.

## <a name="monitor-email-accounts-at-risk"></a>Supervisión de cuentas de correo electrónico en peligro

La **protección de correo electrónico** muestra las cuentas de correo electrónico en riesgo. Puede seleccionar una cuenta para investigar con más detalle en el centro de seguridad de Microsoft defender.

![Tarjeta de protección de correo electrónico](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Supervisar los permisos de aplicación concedidos por los usuarios

**Cloud App Security: aplicaciones de OAuth** enumera las aplicaciones descubiertas por Cloud App Security a las que los usuarios han concedido permisos. El catálogo de riesgos de Cloud App Security incluye más de 16.000 aplicaciones que se evalúan con más de 70 factores de riesgo.

Los factores de riesgo comienzan a partir de información general, como el editor de la aplicación. A continuación, se desplaza a medidas y controles de seguridad, por ejemplo, si la aplicación admite el cifrado en reposo o proporciona un registro de auditoría de la actividad de los usuarios.

![Tarjeta de aplicaciones de OAuth para Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Supervisar las cuentas de usuario de aplicación de nube

**Cuentas de aplicación de nube para revisión** enumera las cuentas que pueden requerir atención.

![Cuentas de aplicación de nube para la tarjeta de revisión](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Comprender qué aplicaciones en la nube se usan

Las **aplicaciones en la nube detectadas (categorías)** muestran qué tipos de aplicaciones se usan en la organización. Se vincula al panel de detección en la nube de Cloud App Security. Para obtener más información, consulte [Inicio rápido: trabajar con aplicaciones detectadas](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Tarjeta de categorías de aplicaciones en la nube detectadas](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Supervisar dónde acceden los usuarios a las aplicaciones en la nube

Las **ubicaciones de actividad de aplicación de nube** muestran dónde los usuarios están accediendo a las aplicaciones en la nube.

![Tarjeta de ubicaciones de actividad de aplicación en la nube](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Supervisión del estado de las cargas de trabajo de la infraestructura

**Estado** de la infraestructura muestra alertas de estado de mantenimiento para cargas de trabajo de infraestructura en Azure defender *.

Azure defender * proporciona administración de seguridad unificada y defender para Office 365 en cargas de trabajo locales y en la nube. Puede recopilar, buscar y analizar datos de seguridad de diferentes orígenes, incluidos firewalls y otras soluciones de asociados.

Para obtener más información, consulte [documentación de Azure defender *](https://docs.microsoft.com/azure/security-center/).

![Tarjeta de mantenimiento de la infraestructura](../../media/infrastructure-health.png)
