---
title: Colaboración de correo electrónico
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Adm_O365
ms.custom:
- VSBFY23
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- MOW150
- OWE150
- OWP150
- SPO160
- BSA160
- SPB160
ms.assetid: eb3e840f-ed60-4461-81f5-12381c132b89
description: Obtenga información sobre los distintos tipos de grupos y cómo usarlos con las distintas características de colaboración de Microsoft 365.
ms.openlocfilehash: a9f98076ec304216ecdde3126e22a155232c9aa6
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67854169"
---
# <a name="email-collaboration-in-microsoft-365"></a>colaboración Email en Microsoft 365

Microsoft 365 fomenta la colaboración a través de grupos en Outlook, listas de distribución (también denominadas grupos de distribución), buzones compartidos y carpetas públicas. Cada una de estas opciones presenta un propósito, una experiencia de usuario y un conjunto de características diferentes. Lo que se utilice dependerá de lo que tenga que hacer el usuario y de las herramientas que proporcione la organización.
  
## <a name="summary-of-collaboration-options"></a>Resumen de las opciones de colaboración

En esta tabla se explican las distintas opciones de colaboración disponibles.

|**Herramienta de colaboración**|**Descripción**|
|:-----|:-----|
|Grupos en Outlook  <br/> |Un área de trabajo compartida que funciona en todas las aplicaciones de Microsoft 365. Incluye una bandeja de entrada compartida, un calendario y un sitio de OneDrive para la Empresa para almacenar los archivos. Los usuarios pueden crear, buscar y unirse a grupos en Outlook directamente desde su correo electrónico o calendario. Los usuarios nuevos y existentes con una Exchange Online o una suscripción de Microsoft 365 pueden usar grupos en Outlook.  <br/> |
|Buzón compartido  <br/> |A mailbox for select users to read and send email messages and share a common calendar. Shared mailboxes also can serve as a generic email address (such as info@contoso.com or sales@contoso.com) that customers can use to inquire about your company. When the Send As permission is enabled on the shared mailbox, email sent from the mailbox will use the generic address (e.g., sales@contoso.com).  <br/> |
|Lista de distribución (también denominada "grupo de distribución")  <br/> |Used to distribute email messages to two or more people at the same time. Distribution groups are also known as mail-enabled distribution groups. A variant of the distribution group, called the dynamic distribution group, is a mail-enabled Active Directory group object used to send email to a large and evolving group of recipients. The exact recipients are determined by filters and conditions that you specify, such as all members of a particular locale or all full-time employees.   <br/><br/> Grupos de Microsoft 365 en Outlook ofrecen una solución más eficaz para la colaboración que los grupos de distribución. Para obtener más información, vea [Por qué debe actualizar las listas de distribución a grupos en Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) y [Migrar listas de distribución a Grupos de Microsoft 365](../manage/upgrade-distribution-lists.md).  <br/> |
|Carpeta pública  <br/> |Diseñadas para el acceso compartido, las carpetas públicas proporcionan una manera fácil y eficaz de recopilar, organizar y compartir información con otras personas de su organización. Las carpetas públicas organizan el contenido en una jerarquía profunda fácil de examinar y siempre visible en la vista de carpetas de Outlook. Una carpeta pública puede estar habilitada para correo y agregarse como un miembro del grupo de distribución. El correo electrónico enviado al grupo de distribución se agrega automáticamente a la carpeta pública para su archivado o para referencia futura. Las carpetas públicas también proporcionan funciones sencillas para el uso compartido de documentos cuando no se tenga una suscripción a SharePoint Online.  <br/> |
   
## <a name="which-collaboration-tool-to-use"></a>¿Qué herramienta de colaboración debo usar?

En la tabla siguiente se ofrece un vistazo rápido a los distintos tipos de grupos y se explica cuándo y cómo usarlos con las distintas características de colaboración.
  

||**Grupos en Outlook**|**Listas de distribución**|**Buzones compartidos**|**Carpetas públicas**|
|:-----|:-----|:-----|:-----|:-----|
|**¿Quién las usa?** <br/> |Usuarios que desean un área de trabajo de colaboración para sus mensajes de grupo, archivos y calendario que se integran con los servicios que ya usan (Outlook Web App, OneDrive para la Empresa)  <br/> |Usuarios que necesitan enviar un correo electrónico a un grupo de destinatarios con una característica o interés común.  <br/> |Los buzones compartidos son una excelente manera de controlar las preguntas de correo electrónico del cliente, ya que varias personas de su organización pueden compartir la responsabilidad de supervisar el buzón y responder a las consultas. Las preguntas de los clientes obtienen respuestas más rápidas y los correos electrónicos relacionados se almacenan en un buzón.  <br/><br/> Delegados que trabajan en nombre de una identidad virtual, por ejemplo, asistencia@contoso.com. Los delegados pueden responder al correo electrónico en nombre de esta identidad de buzón de correo de uso compartido.  <br/> |With the proper permissions, everyone in your organization can access and search public folders. They are ideal for email archiving or for sharing documents.  <br/> |
|**Tamaño de grupo ideal** <br/> |Cualquiera  <br/> |Grande  <br/> |Pequeño  <br/> |Organización de  <br/> |
|**Access** <br/> |Exchange Online y usuarios  <br/> |Para los grupos de distribución, los miembros deben agregarse manualmente. Para los grupos de distribución dinámica, los miembros se agregan sobre la base de criterios de filtrado.  <br/> |Users can be granted Full Access and/or Send As permissions. If granted Full Access permissions, users must also add the shared mailbox to their Outlook profile to access the shared mailbox.  <br/> |Accesible para cualquier miembro de su organización  <br/> |
|**¿Calendario compartido?** <br/> |Sí  <br/> |No  <br/> |Sí  <br/> |Sí  <br/> |
|**¿El correo electrónico llega a la bandeja de entrada?** <br/> |No. Users can subscribe to a group and then forward all Group messages to their inbox  <br/> |Sí. Los correos electrónicos llegan a la bandeja de entrada de todos los miembros del grupo de distribución.  <br/> |No. El correo electrónico llega a la bandeja de entrada del buzón compartido.  <br/> |No. Email arrives in the public folder.  <br/> |
|**Clientes soportados** <br/> | Outlook 2016  <br/>  Outlook 2013 (reenvío después de suscribirse)  <br/>  Outlook Web App  <br/>  Outlook 2010 (reenvío después de suscribirse)  <br/>  Outlook 2007 (reenvío después de suscribirse)  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> |

## <a name="related-content"></a>Contenido relacionado

[Administrar grupos de distribución](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
    
[Usar Grupos de Microsoft 365 en lugar de buzones de sitio](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)
    
[Creación de buzones compartidos en Microsoft 365](create-a-shared-mailbox.md)
    
[Carpetas públicas en Microsoft 365 y Exchange Online](/exchange/collaboration-exo/public-folders/public-folders)
