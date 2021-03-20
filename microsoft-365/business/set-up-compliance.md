---
title: Aumentar la protección contra amenazas para Microsoft 365 Empresa Premium
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configure las características de cumplimiento para evitar la pérdida de datos y ayudar a proteger la información confidencial de sus clientes y sus clientes.
ms.openlocfilehash: e210787718025c5df29af8d4a2283291dcecc2a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912538"
---
# <a name="set-up-compliance-features"></a>Configurar las características de cumplimiento

Su Microsoft 365 Empresa Premium incluye características para proteger sus datos y dispositivos y ayudarle a proteger la información confidencial de sus clientes y sus clientes.

## <a name="set-up-dlp-features"></a>Configurar características de DLP

Vea [Crear una directiva DLP a partir](../compliance/create-a-dlp-policy-from-a-template.md) de una plantilla para obtener un ejemplo sobre cómo configurar una directiva para proteger contra la pérdida de datos personales. 
  
DLP viene con muchas plantillas de directiva listas para usar para muchas configuraciones regionales diferentes. Por ejemplo, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, y así sucesivamente. Consulta [Qué incluyen las plantillas de directiva DLP](../compliance/what-the-dlp-policy-templates-include.md) para obtener una lista completa. Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla pii. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar la retención de correo electrónico con Archivado de Exchange Online

 **Archivado de Exchange Online** de licencia ayudan a mantener el cumplimiento y los estándares normativos al conservar el contenido de correo electrónico para la exhibición de documentos electrónicos. También ayuda a reducir el riesgo si hay una demanda y proporciona una forma de recuperar datos después de una infracción de seguridad o cuando necesita recuperar elementos eliminados. Puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para personalizar lo que desea conservar.
  
**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, poniendo todo el buzón de un usuario en retención por juicio. 
    
Para colocar un buzón en retención por juicio, en el Centro de administración:
    
1. En la navegación izquierda, vaya a **Usuarios** \> **usuarios activos**.
    
2. Seleccione un usuario cuyo buzón desea colocar en retención por juicio. En el panel de usuario, expanda **Configuración de correo** y, junto a Más **opciones,** elija **Editar propiedades de Exchange**.
    
3. En la página buzón del usuario, elija ** características de buzón ** en la navegación izquierda y, a continuación, elija el vínculo Habilitar **en** Retención **por juicio**.
    
4. En el **cuadro de diálogo** Retención por juicio, puede especificar la duración de retención por juicio en el campo **Duración de retención por** juicio. Deje el campo vacío si desea colocar una retención infinita. También puede agregar notas y dirigir al propietario del buzón a un sitio web que quizás tenga que explicar más acerca de la retención por juicio. \>**Guardar**.
    
**Retención:** Puede habilitar directivas de retención personalizadas, por ejemplo, para conservar durante un período de tiempo específico o eliminar contenido de forma permanente al final del período de retención. Para obtener más información, vea [Overview of retention policies](../compliance/retention.md).

## <a name="set-up-sensitivity-labels"></a>Configurar etiquetas de confidencialidad

Las etiquetas de confidencialidad vienen con el Plan 1 de Azure Information Protection (AIP) y le ayudan a clasificar y, opcionalmente, proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas. Los administradores que definen reglas y condiciones pueden aplicar automáticamente las etiquetas, manualmente por los usuarios o mediante una combinación en la que se les dan recomendaciones a los usuarios.

Para configurar etiquetas de confidencialidad, vea [crear y administrar el vídeo de etiquetas de](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) confidencialidad.



### <a name="install-the-azure-information-protection-client-manually"></a>Instalar el cliente de Azure Information Protection manualmente

Para instalar manualmente el cliente AIP:

1. Descargue **AzinfoProtection_UL.exe** desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Puede comprobar que la instalación ha funcionado viendo  un documento de Word y asegurándose de que la opción Confidencialidad esté disponible en la **pestaña** Inicio.
<br/>![Menú desplegable de la pestaña Protección en un documento de Word.](../media/word-sensitivity.png)

Para obtener más información, vea [Install the client](/azure/information-protection/infoprotect-tutorial-step3).