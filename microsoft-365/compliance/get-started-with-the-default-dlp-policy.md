---
title: Introducción a la directiva predeterminada de DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el informe para refinar la directiva predeterminada de prevención de pérdida de datos (DLP) de su organización.
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817619"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introducción a la directiva predeterminada de DLP

Antes incluso de crear la primera directiva de prevención de pérdida de datos (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a proteger su contenido confidencial al notificarle cuándo se compartieron el correo electrónico o los documentos que contienen un número de tarjeta de crédito con alguien de fuera de su organización. Verá esta recomendación en la página **principal** del Centro de cumplimiento &amp; de seguridad. 
  
Puede usar este widget para ver rápidamente cuándo y cuánta información confidencial se compartió y, a continuación, refinar la directiva DLP predeterminada en un solo clic o dos. También puede editar la directiva DLP predeterminada en cualquier momento porque es totalmente personalizable. Tenga en cuenta que si no ve la recomendación al principio, intente hacer clic en **+Más** en la parte inferior de la sección Recomendado **para** usted. 
  
![Widget denominado Proteger aún más el contenido compartido](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Ver el informe y refinar la directiva DLP predeterminada

Cuando el widget le muestre que los usuarios han compartido información confidencial con personas de fuera de su organización, elija **Refinar** directiva DLP en la parte inferior. 
  
El informe detallado muestra cuándo y cuánto contenido que contiene números de tarjeta de crédito se compartió en los últimos 30 días. Tenga en cuenta que las coincidencias de reglas pueden tardar hasta 48 horas en aparecer en el widget.
  
Para ayudar a proteger la información confidencial, la directiva DLP predeterminada:
  
- Detecta cuando el contenido de Exchange, SharePoint y OneDrive que contiene al menos un número de tarjeta de crédito se comparte con personas de fuera de su organización.
    
- Muestra una sugerencia de directiva y envía una notificación por correo electrónico a los usuarios cuando intentan compartir esta información confidencial con personas de fuera de su organización. Para obtener más información sobre estas opciones, vea Enviar notificaciones por correo electrónico y [mostrar sugerencias de directiva para directivas DLP.](use-notifications-and-policy-tips.md)
    
- Genera informes de actividad detallados para que pueda realizar un seguimiento de cosas como quién compartió el contenido con personas de fuera de su organización y cuándo lo hizo. Puede usar los informes [DLP y](view-the-dlp-reports.md) los datos del registro de [auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **DLP** de  =  actividad) para ver esta información.
    
Para refinar rápidamente la directiva DLP predeterminada, puede elegir que:
  
- Envíe un correo electrónico de informe de incidentes cuando los usuarios compartan esta información confidencial con personas de fuera de su organización.
    
- Agregue otros usuarios al informe de incidentes de correo electrónico.
    
- Bloquear el acceso al contenido que contiene la información confidencial, pero permitir al usuario invalidar y compartir o enviar si es necesario.
    
Para obtener más información sobre los informes de incidentes o la restricción del acceso, vea [Información general sobre las directivas de prevención de pérdida de datos.](data-loss-prevention-policies.md)
  
Si desea cambiar estas opciones más adelante, puede editar la directiva DLP predeterminada en cualquier momento ( vea la sección siguiente).
  
![Configuración del widget denominado Protección adicional del contenido compartido](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Editar la directiva DLP predeterminada

Esta directiva se denomina **directiva DLP predeterminada y** aparece en Prevención de pérdida **de** datos en la **página Directiva** del Centro de cumplimiento &amp; de seguridad. 
  
Esta directiva es totalmente personalizable, igual que cualquier directiva DLP que cree usted mismo desde cero. También puede desactivar o eliminar la directiva para que los usuarios ya no reciban sugerencias de directiva ni notificaciones por correo electrónico.
  
![Directiva DLP denominada Directiva DLP predeterminada](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Cuando el widget aparece y no aparece

El widget denominado Protección adicional  del contenido **compartido** aparece en la sección Recomendado para usted de la página **principal** del Centro de &amp; cumplimiento de seguridad. 
  
Este widget solo aparece cuando:
  
- No hay directivas de prevención de pérdida de datos en el Centro de cumplimiento de &amp; seguridad o en el Centro de administración de Exchange. Este widget está pensado para ayudarle a empezar a usar DLP, por lo que no aparece si ya tiene directivas DLP.
    
- El contenido que contiene al menos una tarjeta de crédito se ha compartido con alguien de fuera de su organización en los últimos 30 días.
    
Tenga en cuenta que las coincidencias de reglas pueden tardar hasta 48 horas en estar disponibles para el widget, por lo que después de que se detecte información confidencial compartida externamente, la recomendación puede tardar hasta dos días en aparecer.
  
Por último, después de usar el widget para refinar la directiva DLP predeterminada, el widget desaparece de la **página** principal. 
  

