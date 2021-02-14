---
title: Cómo funciona DLP con el Centro de seguridad & cumplimiento & Centro de administración de Exchange
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en el Centro de seguridad & cumplimiento funciona con DLP y reglas de flujo de correo (reglas de transporte) en el Centro de administración de Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3c6342ab6d57c1f22de96e64a01df5fd15131
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036201"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funcionamiento de DLP entre el Centro de seguridad y cumplimiento y el Centro de administración de Exchange

En Office 365, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:
  
- En el **Centro de & cumplimiento,** puede crear una única directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive, Exchange y ahora Microsoft Teams. Cuando sea posible, se recomienda crear una directiva DLP aquí. Para obtener más información, [vea DLP en el Centro de & cumplimiento.](data-loss-prevention-policies.md)
    
- En el **Centro de administración de Exchange,** puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange. Esta directiva puede usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), por lo que tiene más opciones específicas para controlar el correo electrónico. Para obtener más información, consulte [DLP en el Centro de administración de Exchange.](https://go.microsoft.com/fwlink/?linkid=852311)
    
Las directivas DLP creadas en estos centros de administración funcionan en paralelo: en este tema se explica cómo hacerlo.
  
![Páginas DLP en el Centro de seguridad y cumplimiento y el Centro de administración de Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funcionamiento de DLP en el Centro de & cumplimiento con DLP y reglas de flujo de correo en el Centro de administración de Exchange

Después de crear una directiva DLP en el Centro de seguridad & cumplimiento, la directiva se implementa en todas las ubicaciones incluidas en la directiva. Si la directiva incluye Exchange Online, la directiva se sincroniza allí y se aplica exactamente de la misma manera que una directiva DLP creada en el Centro de administración de Exchange. 
  
Si ha creado directivas DLP en el Centro de administración de Exchange, dichas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el Centro de seguridad & cumplimiento. Pero tenga en cuenta que las reglas creadas en el Centro de administración de Exchange tienen prioridad. Todas las reglas de flujo de correo de Exchange se procesan primero y, a continuación, se procesan las reglas DLP del Centro de & cumplimiento.
  
Esto significa que:
  
- Las reglas DLP creadas en el Centro de seguridad y cumplimiento no examinarán los mensajes bloqueados por las reglas de flujo de correo de & Exchange.
    
- Si una regla de flujo de correo de Exchange modifica un mensaje de forma que hace que coincida con una directiva DLP en el Centro de seguridad & y cumplimiento (como agregar usuarios externos), las reglas DLP lo detectarán y aplicarán la directiva según sea necesario.
    
Tenga en cuenta también que las reglas de flujo de correo de Exchange que usan la acción "detener el procesamiento" no afectan al procesamiento de reglas DLP en el Centro de seguridad & Cumplimiento, sino que se seguirán procesando.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Sugerencias de directiva en el Centro de & cumplimiento frente al Centro de administración de Exchange

Las sugerencias de directiva pueden funcionar con directivas DLP y reglas de flujo de correo creadas en el Centro de administración de Exchange, o con directivas DLP creadas en el Centro de seguridad & Cumplimiento, pero no ambas. Esto se debe a que estas directivas se almacenan en diferentes ubicaciones, pero las sugerencias de directiva solo pueden dibujarse desde una única ubicación.
  
Si ha configurado sugerencias de directiva en el Centro de administración de Exchange, las sugerencias de directiva que configure en el Centro de seguridad & y cumplimiento no se mostrarán a los usuarios de Outlook en la Web y Outlook 2013 y versiones posteriores hasta que desactive las sugerencias en el Centro de administración de Exchange. Esto garantiza que las reglas de flujo de correo de Exchange actuales seguirán funcionando hasta que elija cambiar al Centro de seguridad & cumplimiento.
  
Tenga en cuenta que aunque las sugerencias de directiva solo pueden dibujar desde una única ubicación, siempre se envían notificaciones por correo electrónico, incluso si usa directivas DLP en el Centro de seguridad & Cumplimiento y en el Centro de administración de Exchange.
  

