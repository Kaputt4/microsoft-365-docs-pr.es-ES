---
title: Aumentar la protección contra amenazas para Microsoft 365 empresa Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
description: Configure las características de cumplimiento para evitar la pérdida de datos y ayude a mantener segura la información confidencial de sus clientes.
ms.openlocfilehash: 523d020587bcf16e46263b88ee7654b9c786e7a2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048073"
---
# <a name="set-up-compliance-features"></a>Configurar las características de cumplimiento

Su Microsoft 365 empresa Premium incluye características para proteger sus datos y dispositivos y ayudarle a mantener segura la información confidencial de sus clientes.

## <a name="set-up-dlp-features"></a>Configurar las características de DLP

Consulte [crear una directiva DLP a partir de una plantilla](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) para obtener un ejemplo sobre cómo configurar una directiva para protegerla contra información de identificación personal (PII). 
  
DLP incluye varias plantillas de directiva listas para usarse para muchas configuraciones regionales diferentes. Por ejemplo, datos financieros de Australia, Act de información personal de Canadá, datos financieros de Estados Unidos, etc. Vea [Qué incluyen las plantillas de directiva de DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) para obtener una lista completa. Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar la retención de correo electrónico con el archivado de Exchange Online

 Las características de licencia de **archivado de Exchange Online** ayudan a mantener el cumplimiento normativo y preservar el contenido de correo electrónico para eDiscovery. También ayuda a reducir el riesgo si existe un litigio y proporciona una forma de recuperar datos después de una infracción de seguridad o cuando se necesitan recuperar elementos eliminados. Puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para personalizar lo que desea conservar.
  
**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, al poner el buzón completo de un usuario en retención por juicio. 
    
Para poner un buzón de correo en retención por juicio, en el centro de administración:
    
1. En el panel de navegación izquierdo, **vaya a** \> usuarios **activos**.
    
2. Seleccione un usuario cuyo buzón quiera poner en retención por juicio. En el panel de usuario, expanda **configuración de correo**y, junto a **más configuraciones**, elija **Editar propiedades de Exchange**.
    
3. En la página buzón del usuario, elija * * características de buzón * * en el panel de navegación izquierdo y, a continuación, elija el vínculo **Habilitar** en **retención por juicio**.
    
4. En el cuadro de diálogo **retención por juicio** , puede especificar la duración de retención por juicio en el campo **duración** de retención por juicio. Deje el campo vacío si desea realizar una suspensión infinita. También puede agregar notas y dirigir al propietario del buzón a un sitio web que tenga que explicar más sobre la retención por juicio. \>**Guardar**.
    
**Retención:** Puede habilitar las directivas de retención personalizadas, por ejemplo, para conservarlas durante un período de tiempo determinado o eliminar el contenido de forma permanente al final del período de retención. Para obtener más información, vea [información general sobre las directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).

## <a name="set-up-sensitivity-labels"></a>Configurar las etiquetas de confidencialidad

Las etiquetas de confidencialidad incluyen el plan 1 de Azure Information Protection (AIP) y le ayudan a clasificar y, de manera opcional, a proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas. Las etiquetas pueden ser aplicadas automáticamente por los administradores que definen las reglas y condiciones, manualmente por los usuarios o mediante una combinación en la que los usuarios obtienen recomendaciones.

Para configurar las etiquetas de confidencialidad, vea [crear y administrar las etiquetas de confidencialidad](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) de vídeo.



### <a name="install-the-azure-information-protection-client-manually"></a>Instalar el cliente de Azure Information Protection de forma manual

Para instalar manualmente el cliente de AIP:

1. Descargue **AzinfoProtection_UL. exe** desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Puede comprobar que la instalación se ha realizado viendo un documento de Word y asegurándose de que la opción de **sensibilidad** esté disponible en la pestaña **Inicio** .
<br/>![Cuadro desplegable de la pestaña protección en un documento de Word.](../media/word-sensitivity.png)

Para obtener más información, vea [Install the Client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
