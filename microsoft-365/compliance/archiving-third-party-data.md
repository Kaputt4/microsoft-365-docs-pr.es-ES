---
title: Archivado de datos de terceros en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Los administradores pueden importar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a los buzones de la organización de Office 365. Esto le permite archivar datos de Facebook, Twitter y otros orígenes de datos de terceros en Office 365. A continuación, puede usar y aplicar las características de cumplimiento de Office 365 (por ejemplo, retenciones legales, exhibición de documentos electrónicos, archivado local y directivas de retención) para los datos de terceros.
ms.openlocfilehash: 084cacf1c2bef8b5786e6dba804f9a1e87001338
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615590"
---
# <a name="archive-third-party-data-in-office-365"></a>Archivado de datos de terceros en Office 365

Office 365 permite a los administradores importar y archivar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, a los buzones de la organización de Office 365. Entre los ejemplos de orígenes de datos de terceros que puede importar a Office 365 se incluyen los siguientes servicios: 
  
- **Social:** Facebook, LinkedIn, Twitter y Yammer 
    
- **Mensajería instantánea:** Yahoo Messenger, GoogleTalk y Cisco Jabber 
    
- **Colaboración en documentos:** Box y DropBox 
    
- **Sectores verticales:** Administración de relaciones con el cliente (como Salesforce chatter) y servicios financieros (como Bloomberg y Thomson Reuters) 
    
- **SMS/mensajería de texto:** BlackBerry 
    
Una vez importados los datos de terceros, puede aplicar las características&mdash;de cumplimiento de Office 365 como, por ejemplo, la retención por juicio, el archivado local, la auditoría, el cumplimiento de [comunicaciones](communication-compliance.md)y&mdash;las directivas de retención de Office 365 a estos datos. Por ejemplo, cuando un buzón de correo se coloca en retención por juicio, se conservan los datos de terceros. Puede buscar datos de terceros mediante las herramientas de exhibición de documentos electrónicos de Microsoft. O bien, puede aplicar directivas de archivado y retención a datos de terceros, como lo haría con los datos de Microsoft. En Resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

Hay dos formas de importar y archivar datos de terceros en Office 365:

- **Use un conector de datos de terceros en el centro de seguridad & cumplimiento:** Use un conector de datos personalizado que esté disponible en el centro de seguridad & cumplimiento en Office 365. Una vez que haya configurado y configurado el conector, se conecta al origen de datos de terceros, convierte el contenido de un elemento a un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón de correo en Office 365. Actualmente, puede implementar conectores para importar y archivar datos de páginas empresariales de Facebook, cuentas corporativas de Twitter, Bloomberg instantáneo y LinkedIn. Para obtener instrucciones paso a paso para configurar un conector, consulte:
   
   - **Facebook:** [usar un conector de ejemplo para archivar datos de Facebook en Office 365](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter:** [use un conector de ejemplo para archivar datos de Twitter en Office 365](archive-twitter-data-with-sample-connector.md)
    
   - **LinkedIn:** [configurar un conector para archivar datos de LinkedIn en Office 365](archive-linkedin-data.md)

   - **Bloomberg instantáneo:** [configurar un conector para archivar datos instantáneos de bloomberg en Office 365](archive-instant-bloomberg-data.md)

- **Trabajar con un socio de Microsoft:** Su organización trabaja con un socio de Microsoft que proporcionará un conector personalizado que se configurará para extraer elementos del origen de datos de terceros de manera periódica y, a continuación, conectarse a la nube de Microsoft mediante una API de terceros e importar dichos elementos a Office 365. El conector de asociados también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, lo importa a un buzón en Office 365. Para obtener una lista de los socios con los que puede trabajar y el proceso paso a paso para este método, vea [trabajar con un partner para archivar datos de terceros en Office 365](work-with-partner-to-archive-third-party-data.md).
