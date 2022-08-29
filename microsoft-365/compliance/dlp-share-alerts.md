---
title: Compartir alertas DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Obtenga información sobre cómo compartir alertas de prevención de pérdida de datos con usuarios con permisos mínimos para la investigación.
ms.openlocfilehash: 81336701a732a11e8ebd1b76e2e49ed758c00139
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360745"
---
# <a name="share-data-loss-prevention-alerts-preview"></a>Compartir alertas de prevención de pérdida de datos (versión preliminar)

Los usuarios con los [permisos adecuados](dlp-configure-view-alerts-policies.md#roles) pueden ver alertas de Prevención de pérdida de datos de Microsoft Purview (DLP) en la consola de alertas DLP. Sin embargo, a medida que se evalúan e investigan las alertas, es posible que tenga que compartirlas con otros usuarios que no tengan permisos completos para DLP y la consola de alertas.

Puede compartir una alerta con los usuarios a los que concede permisos limitados para usar los procedimientos de este artículo.

## <a name="before-you-begin"></a>Antes de empezar

Si no está familiarizado con las alertas DLP, consulte [Configuración y visualización de alertas para directivas de prevención de pérdida de datos](/microsoft-365/compliance/dlp-configure-view-alerts-policies).

En este procedimiento, debe crear un grupo de roles personalizado para Purview. Si no ha trabajado con permisos, roles y grupos de roles en Microsoft Purview, consulte [Permisos en el portal de cumplimiento Microsoft Purview](/microsoft-365/compliance/microsoft-365-compliance-center-permissions) 

## <a name="configure-dlp-alert-urls-for-review"></a>Configuración de direcciones URL de alerta DLP para su revisión

1. Abra el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) con una cuenta que tenga permisos de Administración globales.

1. Cree un [grupo de roles personalizado](/microsoft-365/compliance/microsoft-365-compliance-center-permissions#create-a-custom-role-group) para los usuarios con los que desea compartir alertas. Por ejemplo, `DLPAlertInvestigator`. Agregue estos roles al grupo:
    1. **Administración de cumplimiento DLP de solo visualización** : necesaria.
    1. **Visor de contenido de clasificación de datos** : necesario.
    1. **Vista previa** -  *este rol es opcional*, asígnelo si el revisor necesita ver el contenido de origen.

1. Agregue los usuarios al grupo de roles personalizados que acaba de crear, en este ejemplo `DLPAlertInvestigator`.

1.  Abra la pestaña **Alertas DLP** y seleccione la alerta que desea compartir. Se abrirá el panel flotante.

1. Obtenga los valores **Id. de alerta** y **Tiempo detectado** para la alerta.

![Imagen que muestra los detalles de una alerta DLP](../media/dlp-alert-details1.png)

6. El valor del campo **Hora detectada** es la hora local. Debe convertir ese valor a la hora UTC para usarlo en el `creationtime` parámetro . Hay una serie de convertidores de hora local a UTC disponibles a través de una búsqueda en Internet.

7. Construya la dirección URL que se puede compartir en este formato:

`<compliance-portal-domain>/datalossprevention/alerts/eventdeeplink?eventid={eventId}&creationtime={creationTime}`
  
Por ejemplo:
 
`compliance.microsoft.com/datalossprevention/alerts/eventdeeplink?eventid=1eae3e53-c045-1c9b-ee00-08da7a6751dc&creationtime=2022-08-10T12:30:00Z`

En este ejemplo, el valor **Hora detectada** es **9 de agosto de 2022 a las 5:30 p. m.** hora del Pacífico. Esto se convierte al **10 de agosto a las 12:30** UTC o `2022-08-10T12:30:00Z`

8. Puede compartir este vínculo con las personas del grupo que creó y podrán acceder a la alerta para su revisión e investigación.

