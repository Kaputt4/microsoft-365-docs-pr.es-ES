---
title: Funcionamiento de DLP con security & Compliance Center & Exchange centro de administración
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en el Centro de cumplimiento de seguridad & funciona con las reglas dlp y de flujo de correo (reglas de transporte) en el centro de administración de Exchange.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 0c5c6288ed9e3c1f536e7a221a270bad9663cf6b
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753416"
---
# <a name="how-dlp-works-between-the-compliance-center-and-exchange-admin-center"></a>Funcionamiento de DLP entre el Centro de cumplimiento y Exchange centro de administración

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En Microsoft Purview, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:
  
- En el **portal de cumplimiento Microsoft Purview**, puede crear una sola directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive, Exchange, Teams y ahora dispositivos de punto de conexión. Se recomienda crear una directiva DLP aquí. Para obtener más información, vea [Referencia de prevención de pérdida de datos](data-loss-prevention-policies.md).
    
- En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>, puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange. Esta directiva puede usar Exchange reglas de flujo de correo (también conocidas como reglas de transporte), por lo que tiene más opciones específicas para controlar el correo electrónico. Para obtener más información, vea [DLP en el centro de administración de Exchange](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).
    
Las directivas DLP creadas en estos centros de administración funcionan en paralelo: en este artículo se explica cómo hacerlo.
  
![Páginas DLP en el Centro de seguridad y cumplimiento y Exchange centro de administración.](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funcionamiento de DLP en el Centro de cumplimiento de & seguridad con las reglas DLP y de flujo de correo en el Centro de administración de Exchange

Después de crear una directiva DLP en el Centro de cumplimiento de seguridad &, la directiva se implementa en todas las ubicaciones incluidas en la directiva. Si la directiva incluye Exchange Online, la directiva se sincroniza allí y se aplica exactamente de la misma manera que una directiva DLP creada en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>. 
  
Si ha creado directivas DLP en el centro de administración de Exchange, esas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el Centro de cumplimiento de seguridad &. Pero tenga en cuenta que las reglas creadas en el centro de administración de Exchange tienen prioridad. Todas las reglas de flujo de correo Exchange se procesan primero y, a continuación, se procesan las reglas DLP del Centro de cumplimiento de seguridad &.
  
Significa:
  
- Los mensajes bloqueados por Exchange reglas de flujo de correo no se examinarán mediante las reglas DLP creadas en el Centro de cumplimiento de seguridad &.
- Los mensajes que se ponen en cuarentena por Exchange reglas de flujo de correo o cualquier otro filtro se ejecutan antes de que DLP no los analice. 
- Si una regla de flujo de correo Exchange modifica un mensaje de forma que hace que coincida con una directiva DLP en el Centro de cumplimiento de seguridad &, como agregar usuarios externos, las reglas DLP lo detectarán y aplicarán la directiva según sea necesario.
    
Tenga en cuenta también que Exchange las reglas de flujo de correo que usan la acción "detener el procesamiento" no afectan al procesamiento de reglas DLP en el Centro de cumplimiento de seguridad &, todavía se procesarán.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Sugerencias de directiva en el Centro de cumplimiento de seguridad & frente al centro de administración de Exchange

Las sugerencias de directivas pueden funcionar con directivas DLP y reglas de flujo de correo creadas en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>, o bien con directivas DLP creadas en el Centro de cumplimiento de seguridad &, pero no con ambas. Se debe a que estas directivas se almacenan en ubicaciones diferentes, pero las sugerencias de directivas solo pueden extraerse de una sola ubicación.
  
Si ha configurado sugerencias de directiva en el centro de administración de Exchange, las sugerencias de directivas que configure en el Centro de cumplimiento de seguridad & no aparecerán a los usuarios en Outlook en la Web y Outlook 2013 y versiones posteriores hasta que desactive las sugerencias en el centro de administración de Exchange. Esto garantiza que las reglas de flujo de correo de Exchange actuales seguirán funcionando hasta que elija cambiar al Centro de cumplimiento de seguridad &.
  
>[!Note]
>Aunque las sugerencias de directiva solo se pueden dibujar desde una sola ubicación, siempre se envían notificaciones por correo electrónico, incluso si usa directivas DLP en el Centro de cumplimiento de seguridad & y el centro de administración de Exchange.
