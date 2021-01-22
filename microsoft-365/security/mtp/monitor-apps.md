---
title: Informes de supervisión & aplicaciones- Centro de seguridad
description: Obtén información sobre cómo obtener más información sobre el uso de aplicaciones en la nube en tu organización. Incluye diferentes tipos de aplicaciones, su nivel de riesgo y alertas.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, aplicaciones
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930527"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Supervisión e informes de aplicaciones en el Centro de seguridad de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Estos informes proporcionan más información sobre cómo se usan las aplicaciones en la nube en su organización. Incluye diferentes tipos de aplicaciones, su nivel de riesgo y alertas.

## <a name="monitor-email-accounts-at-risk"></a>Supervisión de cuentas de correo electrónico en peligro

**La protección de correo** electrónico muestra cuentas de correo electrónico en riesgo. Puede seleccionar una cuenta para investigar más en el Centro de seguridad de Microsoft Defender.

![Tarjeta de protección de correo electrónico](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Supervisar los permisos de aplicación concedidos por los usuarios

**Cloud App Security: las aplicaciones de OAuth** enumeran las aplicaciones detectadas por Cloud App Security a las que los usuarios han concedido permisos. El catálogo de riesgos de Cloud App Security incluye más de 16 000 aplicaciones que se evalúan con más de 70 factores de riesgo.

Los factores de riesgo empiezan por la información general, como el editor de aplicaciones. A continuación, pasa a medidas de seguridad y controles, como si la aplicación admite el cifrado en reposo o proporciona un registro de auditoría de la actividad del usuario.

![Tarjeta de aplicaciones OAuth de Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Supervisar cuentas de usuario de aplicaciones en la nube

**Las cuentas de aplicación en la nube para revisión** enumeran las cuentas que pueden requerir atención.

![Cuentas de aplicación en la nube para la tarjeta de revisión](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Comprender qué aplicaciones en la nube se usan

**Las aplicaciones en la nube detectadas (categorías)** muestran qué tipos de aplicaciones se usan en la organización. Se vincula al panel de detección de nube en Cloud App Security. Para obtener más información, consulta [Inicio rápido: Trabajar con aplicaciones detectadas.](https://docs.microsoft.com/cloud-app-security/discovered-apps)  

![Tarjeta de categorías de aplicaciones en la nube detectadas](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Supervisar dónde acceden los usuarios a las aplicaciones en la nube

**Las ubicaciones de actividad de aplicaciones en la** nube muestran dónde obtienen acceso los usuarios a las aplicaciones en la nube.

![Tarjeta de ubicaciones de actividad de la aplicación en la nube](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Supervisar el estado de las cargas de trabajo de infraestructura

**El estado de la** infraestructura muestra alertas de estado de mantenimiento para cargas de trabajo de infraestructura en Azure Defender.

Azure Defender proporciona administración de seguridad unificada y Defender para Office 365 en cargas de trabajo locales y en la nube. Puede recopilar, buscar y analizar datos de seguridad de diferentes orígenes, incluidos firewalls y otras soluciones de asociados.

Para obtener más información, consulte [la documentación de Azure Defender.](https://docs.microsoft.com/azure/security-center/)

![Tarjeta de estado de la infraestructura](../../media/infrastructure-health.png)
