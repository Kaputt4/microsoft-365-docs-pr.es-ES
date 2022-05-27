---
title: Introducción a la directiva predeterminada de DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el informe para refinar la directiva predeterminada de prevención de pérdida de datos (DLP) de su organización.
ms.openlocfilehash: 893aae6dfbc4e5c9fcf48a8eec53694352ead4f2
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753460"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introducción a la directiva predeterminada de DLP

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Antes de crear la primera directiva de Prevención de pérdida de datos de Microsoft Purview (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a proteger el contenido confidencial, ya que le notifican cuándo se compartieron con alguien ajeno a su organización el correo electrónico o los documentos que contienen un número de tarjeta de crédito. Verá esta recomendación en la página **Inicio** de la portal de cumplimiento Microsoft Purview. 
  
Puede usar este widget para ver rápidamente cuándo y cuánta información confidencial se ha compartido y, a continuación, refinar la directiva DLP predeterminada con solo un clic o dos. También puede editar la directiva DLP predeterminada en cualquier momento porque es totalmente personalizable. Tenga en cuenta que si no ve la recomendación al principio, intente hacer clic en **+Más** en la parte inferior de la sección **Recomendado para usted** . 
  
![Widget denominado Protección adicional del contenido compartido.](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Ver el informe y refinar la directiva DLP predeterminada

Cuando el widget muestra que los usuarios han compartido información confidencial con personas ajenas a la organización, elija **Refinar directiva DLP** en la parte inferior. 
  
El informe detallado muestra cuándo y cuánto contenido que contiene los números de tarjeta de crédito se ha compartido en los últimos 30 días. Tenga en cuenta que las coincidencias de reglas pueden tardar hasta 48 horas en aparecer en el widget.
  
Para ayudar a proteger la información confidencial, la directiva DLP predeterminada:
  
- Detecta cuándo el contenido de Exchange, SharePoint y OneDrive que contiene al menos un número de tarjeta de crédito se comparte con personas ajenas a la organización.
    
- Muestra una sugerencia de directiva y envía una notificación por correo electrónico a los usuarios cuando intentan compartir esta información confidencial con personas ajenas a la organización. Para obtener más información sobre estas opciones, vea [Enviar notificaciones por correo electrónico y mostrar sugerencias de directivas para directivas DLP](use-notifications-and-policy-tips.md).
    
- Genera informes de actividad detallados para que pueda realizar un seguimiento de cosas como quién compartió el contenido con personas ajenas a la organización y cuándo lo hizo. Puede usar los [informes DLP](view-the-dlp-reports.md) y los [datos de registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **DLP de actividad** = ) para ver esta información.
    
Para refinar rápidamente la directiva DLP predeterminada, puede elegir tenerla:
  
- Envíe un correo electrónico de informe de incidentes cuando los usuarios compartan esta información confidencial con personas ajenas a su organización.
    
- Agregue otros usuarios al informe de incidentes de correo electrónico.
    
- Bloquee el acceso al contenido que contiene la información confidencial, pero permita al usuario invalidar y compartir o enviar si es necesario.
    
Para obtener más información sobre los informes de incidentes o la restricción del acceso, consulte [Referencia de prevención de pérdida de datos](data-loss-prevention-policies.md).
  
Si desea cambiar estas opciones más adelante, puede editar la directiva DLP predeterminada en cualquier momento; consulte la sección siguiente.
  
![Configuración para el widget denominado Protección adicional del contenido compartido.](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Editar la directiva DLP predeterminada

Esta directiva se denomina **Directiva DLP predeterminada** y aparece en **Prevención de pérdida de datos** en la página **Directiva** del portal de cumplimiento Microsoft Purview. 
  
Esta directiva es totalmente personalizable, igual que cualquier directiva DLP que cree usted mismo desde cero. También puede desactivar o eliminar la directiva para que los usuarios ya no reciban sugerencias de directiva ni notificaciones por correo electrónico.
  
![Directiva DLP denominada Directiva DLP predeterminada.](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Cuando el widget hace y no aparece

El widget denominado **Proteger más contenido compartido** aparece en la sección **Recomendado para usted** de la página **Inicio** de la portal de cumplimiento Microsoft Purview. 
  
Este widget solo aparece cuando:
  
- No hay directivas de prevención de pérdida de datos en el centro de administración de portal de cumplimiento Microsoft Purview o Exchange. Este widget está diseñado para ayudarle a empezar a trabajar con DLP, por lo que no aparece si ya tiene directivas DLP.
    
- El contenido que contiene al menos una tarjeta de crédito se ha compartido con alguien de fuera de la organización en los últimos 30 días.
    
Tenga en cuenta que las coincidencias de reglas pueden tardar hasta 48 horas en estar disponibles para el widget, por lo que, una vez detectada la información confidencial compartida externamente, la recomendación puede tardar hasta dos días en aparecer.
  
Por último, después de usar el widget para refinar la directiva DLP predeterminada, el widget desaparece de la página **Principal** . 
  

