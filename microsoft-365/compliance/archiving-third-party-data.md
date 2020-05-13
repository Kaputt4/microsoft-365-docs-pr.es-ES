---
title: Archivar datos de terceros
f1.keywords:
- NOCSH
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
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo importar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a buzones de correo de Microsoft 365.
ms.openlocfilehash: 2d011fcb63e0ec9804ade62f9fdcd1dd95fbf798
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210551"
---
# <a name="archive-third-party-data"></a>Archivar datos de terceros

Microsoft 365 permite a los administradores importar y archivar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a los buzones de la organización 365 de Microsoft. Algunos ejemplos de orígenes de datos de terceros que puede importar a Microsoft 365 incluyen los siguientes servicios: 
  
- **Social:** Facebook, LinkedIn, Twitter y Yammer

- **Mensajería instantánea:** Yahoo Messenger y GoogleTalk

- **Colaboración en documentos:** Box y DropBox

- **Sectores verticales:** Administración de relaciones con el cliente (como Salesforce chatter) y servicios financieros (como Bloomberg y Thomson Reuters)

- **SMS/mensajería de texto:** BlackBerry

Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la exhibición de documentos electrónicos, el archivado local, la auditoría, el cumplimiento de comunicaciones y las directivas de retención a estos datos. Por ejemplo, cuando un buzón de correo se coloca en retención por juicio, se conservan los datos de terceros. Puede buscar datos de terceros mediante las herramientas de exhibición de documentos electrónicos de Microsoft. O bien, puede aplicar directivas de archivado y retención a datos de terceros, como lo haría con los datos de Microsoft. En Resumen, el archivado de datos de terceros en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

Hay dos formas de importar y archivar datos de terceros en Microsoft 365:

- **Use un conector de datos de terceros en el centro de seguridad & cumplimiento:** Usar un conector de datos personalizado que está disponible en el centro de cumplimiento de Microsoft 365. Una vez que haya configurado y configurado el conector, se conecta al origen de datos de terceros, convierte el contenido de un elemento a un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón en Microsoft 365. Actualmente, puede implementar conectores para importar y archivar datos de páginas empresariales de Facebook, cuentas corporativas de Twitter, LinkedIn, Bloomberg y los datos de recursos humanos (HR) de la organización. Para obtener instrucciones paso a paso para configurar uno de estos conectores, consulte:

   - **Facebook:** [usar un conector para archivar datos de Facebook (versión preliminar)](archive-facebook-data-with-sample-connector.md)

   - **Twitter:** [usar un conector para archivar datos de Twitter (versión preliminar)](archive-twitter-data-with-sample-connector.md)

   - **LinkedIn:** [configurar un conector para archivar datos de LinkedIn](archive-linkedin-data.md)

   - **Bloomberg instantáneo:** [configurar un conector para archivar datos Instant Bloomberg](archive-instant-bloomberg-data.md)

   - **Datos de recursos humanos:** [configurar un conector para importar datos de recursos humanos (versión preliminar)](import-hr-data.md)

- **Trabajar con un socio de Microsoft:** Su organización trabaja con un socio de Microsoft que proporcionará un conector personalizado que se configurará para extraer elementos del origen de datos de terceros de forma periódica y, a continuación, conectarse a la nube de Microsoft mediante una API de terceros e importar dichos elementos a Microsoft 365. El conector de asociados también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, lo importa a un buzón en Microsoft 365. Para obtener una lista de los socios con los que puede trabajar y el proceso paso a paso para este método, vea [trabajar con un partner para archivar datos de terceros en Microsoft 365](work-with-partner-to-archive-third-party-data.md).
