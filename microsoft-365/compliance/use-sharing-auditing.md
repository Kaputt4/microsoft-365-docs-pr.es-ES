---
title: Usar el uso compartido de auditoría en el registro de auditoría
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
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: El administrador puede aprender a usar la auditoría de uso compartido en el registro de auditoría Microsoft 365 para identificar los recursos compartidos con usuarios fuera de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819300"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Usar el uso compartido de auditoría en el registro de auditoría

El uso compartido es una actividad clave en SharePoint Online y OneDrive para la Empresa, y se usa ampliamente en organizaciones. Los administradores pueden usar la auditoría de uso compartido en el registro de auditoría para determinar cómo se usa el uso compartido en su organización. 
  
## <a name="the-sharepoint-sharing-schema"></a>Esquema SharePoint uso compartido

Los eventos de uso compartido (sin incluir eventos relacionados con la directiva de uso compartido y los vínculos de uso compartido) son diferentes de los eventos relacionados con archivos y carpetas de una forma principal: un usuario realiza una acción que tiene un efecto en otro usuario. Por ejemplo, cuando un usuario A de un recurso proporciona al usuario B acceso a un archivo. En este ejemplo, el usuario A es el  *usuario que*  actúa y el usuario B es el usuario  *de destino*. En el esquema SharePoint archivo, la acción del usuario que actúa solo afecta al propio archivo. Cuando el usuario A abre un archivo, la única información necesaria en el **evento FileAccessed** es el usuario que actúa. Para solucionar esta diferencia, hay un esquema independiente, denominado *esquema de uso* compartido SharePoint , que captura más información acerca de los eventos de uso compartido. Esto garantiza que los administradores tengan visibilidad sobre quién compartió un recurso y el usuario con el que se compartió el recurso. 
  
El esquema de uso compartido proporciona dos campos adicionales en un registro de auditoría relacionado con eventos de uso compartido: 
  
- **TargetUserOrGroupType:** Identifica si el usuario o grupo de destino es miembro, invitado, SharePointGroup, SecurityGroup o partner.

- **TargetUserOrGroupName:** Almacena el UPN o el nombre del usuario o grupo de destino con el que se compartió un recurso (usuario B en el ejemplo anterior). 

Estos dos campos, además de otras propiedades del esquema del registro de auditoría, como  User,  Operation y Date, pueden contar la historia completa sobre qué usuario compartió qué recurso con quién y *cuándo*.  
  
Hay otra propiedad de esquema que es importante para el artículo de uso compartido. Al exportar los resultados de la búsqueda del registro de auditoría, la columna **AuditData** del archivo CSV exportado almacena información sobre el uso compartido de eventos. Por ejemplo, cuando un usuario comparte un sitio con otro usuario, esto se logra agregando el usuario de destino a un grupo SharePoint usuario. La **columna AuditData** captura esta información para proporcionar contexto a los administradores. Vea [el paso 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) para obtener instrucciones sobre cómo analizar la información en la **columna AuditData.**

## <a name="sharepoint-sharing-events"></a>SharePoint eventos de uso compartido

El uso compartido se define  cuando un usuario (el usuario que actúa) desea compartir un recurso con otro usuario (el *usuario de* destino). Los registros de auditoría relacionados con el uso compartido de un recurso con un usuario externo (un usuario que está fuera de la organización y no tiene una cuenta de invitado en el Azure Active Directory de la organización) se identifican mediante los siguientes eventos, que se registran en el registro de auditoría:

- **SharingInvitationCreated:** Un usuario de la organización intentó compartir un recurso (probablemente un sitio) con un usuario externo. Esto da como resultado una invitación de uso compartido externo enviada al usuario de destino. No se concede acceso al recurso en este momento.

- **SharingInvitationAccepted:** El usuario externo ha aceptado la invitación de uso compartido enviada por el usuario que actúa y ahora tiene acceso al recurso.

- **AnonymousLinkCreated:** Se crea un vínculo anónimo (también denominado vínculo "Cualquiera") para un recurso. Dado que se puede crear y copiar un vínculo anónimo, es razonable suponer que cualquier documento que tenga un vínculo anónimo se ha compartido con un usuario de destino.

- **AnonymousLinkUsed:** Como su nombre indica, este evento se registra cuando se usa un vínculo anónimo para obtener acceso a un recurso. 

- **SecureLinkCreated:** Un usuario ha creado un "vínculo de personas específicas" para compartir un recurso con una persona específica. Este usuario de destino puede ser alguien externo a su organización. La persona con la que se comparte el recurso se identifica en el registro de auditoría del **evento AddedToSecureLink.** Las marcas de tiempo de estos dos eventos son casi idénticas.

- **AddedToSecureLink:** Se agregó un usuario a un vínculo de personas específico. Use el **campo TargetUserOrGroupName** en este evento para identificar el usuario agregado al vínculo de personas específico correspondiente. Este usuario de destino puede ser alguien externo a su organización.

## <a name="sharing-auditing-work-flow"></a>Compartir flujo de trabajo de auditoría
  
Cuando un usuario (el usuario que actúa) desea compartir un recurso con otro usuario (el usuario de destino), SharePoint (o OneDrive para la Empresa) primero comprueba si la dirección de correo electrónico del usuario de destino ya está asociada a una cuenta de usuario en el directorio de la organización. Si el usuario de destino está en el directorio (y tiene una cuenta de usuario invitada correspondiente), SharePoint lo siguiente:
  
-  Asigna inmediatamente los permisos de usuario de destino para tener acceso al recurso agregando el usuario de destino al grupo de SharePoint adecuado y registra un **evento AddedToGroup.** 
    
- Envía una notificación de uso compartido a la dirección de correo electrónico del usuario de destino.
    
- Registra un **evento SharingSet.** Este evento tiene un nombre descriptivo de "Archivo compartido, carpeta o sitio" en **Actividades** de solicitud de uso compartido y acceso en el selector de actividades de la herramienta de búsqueda de registro de auditoría. Consulta la captura de pantalla [en el paso 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file). 
    
Si una cuenta de usuario para el usuario de destino no está en el directorio, SharePoint hace lo siguiente: 
    
   - Registra uno de los siguientes eventos en función de cómo se comparte el recurso:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (este evento se registra solo cuando el recurso compartido es un sitio)
    
   - Cuando el usuario de destino acepta la invitación de uso compartido que se les envía (haciendo clic en el vínculo de la invitación), SharePoint registra un evento **SharingInvitationAccepted** y asigna los permisos de usuario de destino para obtener acceso al recurso. Si se envía un vínculo anónimo al usuario de destino, el evento **AnonymousLinkUsed** se registra después de que el usuario de destino use el vínculo para obtener acceso al recurso. Para vínculos seguros, se **registra un evento FileAccessed** cuando un usuario externo usa el vínculo para obtener acceso al recurso.

También se registra información adicional sobre el usuario de destino, como la identidad del usuario al que es la invitación y el usuario que acepta la invitación. En algún caso, estos usuarios (o direcciones de correo electrónico) pueden ser diferentes. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Cómo identificar recursos compartidos con usuarios externos

Un requisito común para los administradores es crear una lista de todos los recursos que se han compartido con usuarios fuera de la organización. Al usar la auditoría de uso compartido en Office 365, los administradores pueden generar esta lista. Aquí se muestra cómo hacerlo.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Paso 1: Buscar eventos de uso compartido y exportar los resultados a un archivo CSV

El primer paso es buscar eventos de uso compartido en el registro de auditoría. Para obtener más información (incluidos los permisos necesarios) sobre cómo buscar en el registro de auditoría, vea Buscar en el registro de auditoría en el Centro de [seguridad & cumplimiento](search-the-audit-log-in-security-and-compliance.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión con su cuenta profesional o educativa.
    
3. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Buscar**  > **Búsqueda de registros de auditoría**.
    
    La página de **Búsqueda de registros de auditoría** se mostrará. 
    
4. En **Actividades,** haga clic **en Compartir y acceder a** las actividades de solicitud para buscar eventos relacionados con el uso compartido. 
    
    ![En Actividades, seleccione Compartir y obtener acceso a actividades de solicitud](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Seleccione un intervalo de fecha y hora para buscar los eventos de uso compartido que se produjeron en ese período. 
    
6. Haga **clic en** Buscar para ejecutar la búsqueda. 
    
7. Cuando la búsqueda termine de ejecutarse y se muestren los resultados, haga clic **en Exportar** \> **resultados Descargar todos los resultados**.
    
    Después de seleccionar la opción de exportación, un mensaje en la parte inferior de la ventana le pedirá que abra o guarde el archivo CSV.
    
8. Haga **clic en** Guardar como y guarde el archivo CSV en una carpeta del equipo \>  local. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Paso 2: Usar el Editor de PowerQuery para dar formato al registro de auditoría exportado

El siguiente paso es usar la característica de transformación JSON en el Editor de power query de Excel para dividir cada propiedad de la columna **AuditData** (que consta de un objeto JSON de varias propiedades) en su propia columna. Esto le permite filtrar columnas para ver registros relacionados con el uso compartido

Para obtener instrucciones paso a paso, consulte «Paso 2: Dar formato al registro de auditoría exportado mediante el Editor de Power Query» en [Exportar, configurar y ver los archivos de registros de auditoría](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor). 

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Paso 3: Filtrar el archivo CSV para los recursos compartidos con usuarios externos

El siguiente paso es filtrar el CSV para los distintos eventos relacionados con el uso compartido que se describen anteriormente en la [sección SharePoint eventos de uso](#sharepoint-sharing-events) compartido. Como alternativa, puede filtrar la **columna TargetUserOrGroupType** para mostrar todos los registros donde el valor de esta propiedad es **Guest**. 

Después de seguir las instrucciones del paso anterior para preparar el archivo CSV mediante el editor de PowerQuery, haga lo siguiente:
    
1. Abra el Excel que creó en el paso 2. 

2. En la **ficha Inicio,** haga clic **en Ordenar & filtro** y, a continuación, haga clic en **Filtrar**.
    
3. En la lista desplegable Ordenar **&**  filtro de la columna Operaciones, desactive todas las selecciones, seleccione uno o más de los siguientes eventos relacionados con el uso compartido y, a continuación, haga clic en **Aceptar**.
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel muestra las filas de los eventos seleccionados.
    
4. Vaya a la columna **denominada TargetUserOrGroupType** y selecciónelo. 
    
5. En la **lista desplegable Ordenar &** filtro, desactive todas las selecciones, seleccione **TargetUserOrGroupType:Guest** y haga clic en **Aceptar**.
    
    Ahora Excel las filas para compartir eventos Y donde el usuario de destino está fuera de la organización, ya que los usuarios externos se identifican mediante el valor **TargetUserOrGroupType:Guest**. 
  
> [!TIP]
> Para los registros de auditoría que se muestran, la columna **ObjectId** identifica el recurso que se compartió con el usuario de destino; por ejemplo  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .
