---
title: Funcionamiento de DLP con el Centro de cumplimiento de seguridad & & Centro de administración de Exchange
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
description: Obtenga información sobre cómo DLP en el Centro de cumplimiento de seguridad & funciona con las reglas dlp y de flujo de correo (reglas de transporte) en el Centro de administración de Exchange.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: fa77bf84ff8ef2b4f194f45b9a29b49f6b662a70
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66641414"
---
# <a name="how-dlp-works-between-the-compliance-center-and-exchange-admin-center"></a>Funcionamiento de DLP entre el Centro de cumplimiento y el Centro de administración de Exchange

En Microsoft Purview, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:
  
- En el **portal de cumplimiento Microsoft Purview**, puede crear una sola directiva DLP para ayudar a proteger el contenido en SharePoint, OneDrive, Exchange, Teams y ahora dispositivos de punto de conexión. Se recomienda crear una directiva DLP aquí. Para obtener más información, vea [Referencia de prevención de pérdida de datos](data-loss-prevention-policies.md).
    
- En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>, puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange. Esta directiva puede usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), por lo que tiene más opciones específicas para controlar el correo electrónico. Para obtener más información, vea [DLP en el Centro de administración de Exchange](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).
    
Las directivas DLP creadas en estos centros de administración funcionan en paralelo: en este artículo se explica cómo hacerlo.
 
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funcionamiento de DLP en el Centro de cumplimiento de & seguridad con las reglas DLP y de flujo de correo en el Centro de administración de Exchange

Después de crear una directiva DLP en el Centro de cumplimiento de seguridad &, la directiva se implementa en todas las ubicaciones incluidas en la directiva. Si la directiva incluye Exchange Online, la directiva se sincroniza allí y se aplica exactamente de la misma manera que una directiva DLP creada en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>. 
  
Si ha creado directivas DLP en el Centro de administración de Exchange, esas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el Centro de cumplimiento de seguridad &. Pero tenga en cuenta que las reglas creadas en el Centro de administración de Exchange tienen prioridad. Todas las reglas de flujo de correo de Exchange se procesan primero y, a continuación, se procesan las reglas DLP del Centro de cumplimiento de seguridad &.
  
Significa:
  
- Los mensajes bloqueados por las reglas de flujo de correo de Exchange no se examinarán mediante las reglas DLP creadas en el Centro de cumplimiento de seguridad &.
- Los mensajes que están en cuarentena mediante reglas de flujo de correo de Exchange o cualquier otro filtro que se ejecute antes de dlp no se examinarán mediante DLP. 
- Si una regla de flujo de correo de Exchange modifica un mensaje de forma que hace que coincida con una directiva DLP en el Centro de cumplimiento de seguridad &, como agregar usuarios externos, las reglas DLP lo detectarán y aplicarán la directiva según sea necesario.
    
Tenga en cuenta también que las reglas de flujo de correo de Exchange que usan la acción "detener el procesamiento" no afectan al procesamiento de reglas DLP en el Centro de cumplimiento de & de seguridad; seguirán procesándose.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Sugerencias de directiva en el Centro de cumplimiento de seguridad & frente al Centro de administración de Exchange

Las sugerencias de directivas pueden funcionar con directivas DLP y reglas de flujo de correo creadas en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> o con directivas DLP creadas en el Centro de cumplimiento de seguridad &, pero no con ambas. Se debe a que estas directivas se almacenan en ubicaciones diferentes, pero las sugerencias de directivas solo pueden extraerse de una sola ubicación.
  
Si ha configurado sugerencias de directiva en el Centro de administración de Exchange, las sugerencias de directivas que configure en el Centro de cumplimiento de seguridad & no aparecerán a los usuarios en Outlook en la Web y Outlook 2013 y versiones posteriores hasta que desactive las sugerencias en el Centro de administración de Exchange. Esto garantiza que las reglas actuales de flujo de correo de Exchange seguirán funcionando hasta que decida cambiar al Centro de cumplimiento de seguridad &.
  
>[!Note]
>Aunque las sugerencias de directiva solo se pueden dibujar desde una sola ubicación, siempre se envían notificaciones por correo electrónico, incluso si usa directivas DLP tanto en el Centro de cumplimiento de seguridad & como en el Centro de administración de Exchange.
