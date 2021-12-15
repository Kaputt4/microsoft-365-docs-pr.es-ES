---
title: Aumentar la protección contra amenazas para Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
ms.openlocfilehash: 69960c4f158a30d9d47d749ed1e7eb2d2d74f430
ms.sourcegitcommit: b6ab10ba95e4b986065c51179ead3810cc1e2a85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61521047"
---
# <a name="set-up-compliance-features"></a>Configurar las características de cumplimiento

Su Microsoft 365 Empresa Premium incluye características para proteger sus datos y dispositivos y ayudarle a mantener la información confidencial de sus clientes y sus clientes seguros.

## <a name="watch-set-up-dlp-features"></a>Ver: Configurar características de DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

Las directivas de prevención de pérdida de datos ayudan a identificar y proteger la información confidencial de su empresa, como números de seguridad social o registros médicos.

1. Para empezar, vaya al Centro [de administración](https://admin.microsoft.com)y seleccione **Configurar**.
1. Desplácese hacia abajo **hasta Configurar la prevención de pérdida de datos** y, a continuación, seleccione **Ver** y, a continuación, **Administrar**.
1. Para editar una directiva, selecciónelo, elija **Editar directiva** y, a continuación, seleccione qué cambiar. Por ejemplo, seleccione **Ubicaciones** para cambiar lo que se examina.
1. Para crear una nueva directiva, seleccione **Crear una directiva**.
1. Puede crear una directiva personalizada o empezar con una plantilla. Por ejemplo, para crear una directiva HIPAA, seleccione la **plantilla** Médica y de salud y, a continuación, seleccione Ley de seguros de salud **(HIPAA)** de Estados Unidos . Seleccione **Siguiente**.
1. Revise la configuración y seleccione **Crear**. Después de que la directiva entre en vigor, el correo electrónico que contiene la información confidencial descrita se bloquea y el remitente que intentó enviar esa información ve un mensaje de advertencia.

Vea [Crear una directiva DLP a partir](../../compliance/create-a-dlp-policy-from-a-template.md) de una plantilla para obtener un ejemplo sobre cómo configurar una directiva para proteger contra la pérdida de datos personales. 
  
DLP viene con muchas plantillas de directiva listas para usar para muchas configuraciones regionales diferentes. Por ejemplo, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, y así sucesivamente. Consulta [Qué incluyen las plantillas de directiva DLP](../../compliance/what-the-dlp-policy-templates-include.md) para obtener una lista completa. Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla pii.
 
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar la retención de correo electrónico con Archivado de Exchange Online

 **Archivado de Exchange Online** características de licencia ayudan a mantener el cumplimiento y los estándares normativos al conservar el contenido de correo electrónico para la exhibición de documentos electrónicos. También ayuda a reducir el riesgo si hay una demanda y proporciona una forma de recuperar datos después de una infracción de seguridad o cuando necesita recuperar elementos eliminados. Puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para personalizar lo que desea conservar.
  
**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, poniendo todo el buzón de un usuario en retención por juicio. 
    
Para colocar un buzón en retención por juicio, en el Centro de administración:
    
1. En la navegación izquierda, vaya a **Usuarios** \> **usuarios activos**.
    
2. Seleccione un usuario cuyo buzón desea colocar en retención por juicio. En el panel de usuario, expanda **Configuración de correo** y, junto a Más **opciones,** elija **Editar Exchange propiedades**.
    
3. En la página buzón del usuario, elija ** características de buzón ** en la navegación izquierda y, a continuación, elija el vínculo Habilitar **en** Retención **por juicio**.
    
4. En el **cuadro de diálogo** Retención por juicio, puede especificar la duración de retención por juicio en el campo **Duración de retención por** juicio. Deje el campo vacío si desea colocar una retención infinita. También puede agregar notas y dirigir al propietario del buzón a un sitio web que quizás tenga que explicar más acerca de la retención por juicio. \>**Guardar**.
    
**Retención:** Puede habilitar directivas de retención personalizadas, por ejemplo, para conservar durante un período de tiempo específico o eliminar contenido de forma permanente al final del período de retención. Para obtener más información, vea [Overview of retention policies](../../compliance/retention.md).

## <a name="watch-set-up-sensitivity-labels"></a>Ver: Configurar etiquetas de confidencialidad

Las etiquetas de confidencialidad vienen con el Plan 1 de Azure Information Protection (AIP) y le ayudan a clasificar y, opcionalmente, proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas. Los administradores que definen reglas y condiciones pueden aplicar automáticamente las etiquetas, manualmente por los usuarios o mediante una combinación en la que se les dan recomendaciones a los usuarios.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

1. En el [Centro de administración,](https://admin.microsoft.com)seleccione el **Centro de administración** de cumplimiento.
1. Seleccione **Clasificación** y, a continuación, **Etiquetas de confidencialidad.**
1. Seleccione **Crear una etiqueta** y, cuando aparezca la advertencia, seleccione **Sí**.
1. Revise la configuración y seleccione **Crear**. Se ha creado la etiqueta. Repita este proceso para las etiquetas adicionales que desee.
1. De forma predeterminada, las etiquetas aparecen Office aplicaciones en este orden: **Confidencial**, **Interna** y **Pública**. Para cambiar el orden, para cada etiqueta, seleccione los tres puntos (más acciones) y, a continuación, mueva la etiqueta hacia arriba o hacia abajo. Normalmente, los permisos se enumeran del nivel más bajo al más alto de permisos.
1. Revise la configuración y, a continuación, **seleccione Publicar**.

Para que las etiquetas funcionen, cada usuario debe descargar el cliente de etiquetado unificado de Azure Information Protection. Busque en la **webAzinfoProtection_UL.exe** y, a continuación, descárbala desde el Centro de descarga de Microsoft y la ejecute en los equipos de los usuarios.

La próxima vez que abra un Aplicación de Office como Word, verá las etiquetas de confidencialidad que se crearon. Para cambiar o aplicar una etiqueta, seleccione Confidencialidad y elija una etiqueta.

### <a name="install-the-azure-information-protection-client-manually"></a>Instalar el cliente de Azure Information Protection manualmente

Para instalar manualmente el cliente AIP:

1. Descargue **AzinfoProtection_UL.exe** desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Puede comprobar que la instalación ha funcionado viendo  un documento de Word y asegurándose de que la opción Confidencialidad esté disponible en la **pestaña** Inicio.
<br/>![Menú desplegable de la pestaña Protección en un documento de Word.](../../media/word-sensitivity.png)

Para obtener más información, vea [Install the client](/azure/information-protection/infoprotect-tutorial-step3).