---
title: Buscar e investigar correo electrónico malintencionado que se entregó en Office 365, corrección, solución, corrección, protección contra amenazas, explorador de amenazas, protección
keywords: TIMailData-en línea, incidente de seguridad, incidente, ATP PowerShell, malware de correo electrónico, usuarios comprometidos, phishing de correo electrónico, malware de correo electrónico, leer encabezados de correo electrónico, leer encabezados, abrir encabezados de correo electrónico
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo usar la investigación de amenazas y las capacidades de respuesta para buscar y investigar correo electrónico malintencionado.
ms.openlocfilehash: ec70bc585d4067357c9871cffc7475357fbfb5bb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634139"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a>Investigar y corregir el correo electrónico malintencionado que se entregó en Office 365

La [protección contra amenazas avanzada de Office 365](office-365-atp.md) le permite investigar las actividades que ponen en riesgo a las personas de su organización y emprender acciones para proteger a su organización. Por ejemplo, si forma parte del equipo de seguridad de su organización, puede encontrar e investigar los mensajes de correo electrónico sospechosos que se entregaron. Para ello, puede usar el [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Antes de empezar...

Asegúrese de que se cumplen los siguientes requisitos:
  
- Su organización tiene [Office 365 de protección contra amenazas avanzada](office-365-atp.md) y [se asignan licencias a los usuarios](../../admin/manage/assign-licenses-to-users.md).
    
- el [registro de auditoría](../../compliance/turn-audit-log-search-on-or-off.md) está activado para su organización. 
    
- Su organización tiene directivas definidas para protección contra correo electrónico no deseado, antimalware, antiphishing, etc. Consulte [proteger contra amenazas en Office 365](protect-against-threats.md).
    
- Es un administrador global o bien tiene el rol de administrador de seguridad o de la búsqueda y depuración asignado en &amp; el centro de seguridad y cumplimiento. Consulte [permisos en el centro &amp; de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md). Para algunas acciones, también debe tener asignado un nuevo rol de vista previa. 

#### <a name="preview-role-permissions"></a>Vista previa de permisos de roles

Para llevar a cabo determinadas acciones, como ver los encabezados de mensajes o descargar el contenido de los mensajes de correo electrónico, debe tener un nuevo rol denominado *vista previa* agregado a otro grupo de funciones apropiado. La siguiente tabla clarifica los permisos y las funciones necesarias.

|Actividad  |Grupo de funciones |¿Se requiere un rol de vista previa?  |
|---------|---------|---------|
|Usar el explorador de amenazas (y detecciones en tiempo real) para analizar las amenazas     |Administrador global <br> Administrador de seguridad <br> Lector de seguridad     | No   |
|Usar el explorador de amenazas (y detecciones en tiempo real) para ver los encabezados de los mensajes de correo electrónico, así como para obtener una vista previa y descargar los mensajes de correo electrónico en cuarentena    |Administrador global <br> Administrador de seguridad <br>Lector de seguridad   |       No  |
|Usar el explorador de amenazas para ver los encabezados y descargar los mensajes de correo electrónico que se entregan a los buzones     |Administrador global <br>Administrador de seguridad <br> Lector de seguridad <br> Preview   |   Sí      |

> [!NOTE]
> La *vista previa* es un rol y no un grupo de roles; el rol de vista previa debe agregarse a un grupo de roles existente para Office 365. La función de administrador global se asigna al centro de administración de[https://admin.microsoft.com](https://admin.microsoft.com)Microsoft 365 () y el administrador de seguridad y los roles de lector de seguridad se asignan[https://protection.office.com](https://protection.office.com)en el centro de seguridad & cumplimiento (). Para obtener más información acerca de los roles y los permisos, consulte [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Buscar y eliminar correo electrónico sospechoso que se entregó

El explorador de amenazas es un informe eficaz que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una mayor investigación. El siguiente procedimiento se centra en usar el explorador para buscar y eliminar correo electrónico malintencionado de los buzones de los destinatarios.

> [!NOTE]
> Las búsquedas predeterminadas en el explorador no incluyen elementos zapped en este momento.  Esto se aplica a todas las vistas, por ejemplo, las vistas de malware o phish. Para incluir elementos de zapped, debe agregar una "acción de entrega" establecida en incluir "eliminado por ZAP". Si incluye todas las opciones, verá todos los resultados de las acciones de entrega, incluidos los elementos zapped.

1. **Vaya a Threat Explorer**: vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. Esto le llevará al centro de &amp; seguridad y cumplimiento.

2. En el inicio rápido de navegación izquierdo, elija **Threat Management** \> **Explorer**.

    ![Explorador con los campos acción de entrega y ubicación de entrega.](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. **Vistas en el explorador de amenazas**: en el menú **Ver** , elija **todo el correo electrónico**.

    ![Menú Ver del explorador de amenazas y correo electrónico: malware, phish, envíos y todas las opciones de correo electrónico, también malware de contenido.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    La vista de *malware* es actualmente la predeterminada y captura mensajes de correo electrónico donde se detecta una amenaza de malware. La vista *phish* funciona de la misma manera, para phish.

    Sin embargo, en todas las vistas de *correo electrónico* se muestra cada correo recibido por la organización, independientemente de si se han detectado o no amenazas. Como puede imaginar, esta es una gran cantidad de datos, por lo que esta vista muestra un marcador de posición que le pide que se aplique un filtro. (Esta vista solo está disponible para los clientes P2 de ATP).

    La vista *envíos* muestra todos los correos enviados por el administrador o el usuario que se notificaron a Microsoft.

4. **Buscar y filtrar en el explorador de amenazas**: los filtros aparecen en la parte superior de la página en la barra de búsqueda para ayudar a los administradores en sus investigaciones. Tenga en cuenta que se pueden aplicar varios filtros a la vez y que se agregan varios valores separados por comas a un filtro para acotar la búsqueda. Recuerde:
    - Los filtros realizan una coincidencia exacta en la mayoría de las condiciones de filtrado.
    - El filtro de asunto usa una consulta Contains.
    - Los filtros de dirección URL funcionan con o sin protocolos (p. ej. https).
    - El dominio de dirección URL, la ruta de dirección URL y los filtros de dominio y ruta de acceso de dirección URL no requieren un protocolo para filtrar.
    - Debe hacer clic en el icono actualizar cada vez que cambie los valores de filtro para obtener resultados relevantes.

5. **Filtros avanzados**: con estos filtros, puede crear consultas complejas y filtrar el conjunto de datos. Al hacer clic en *filtros avanzados* , se abre un control flotante con opciones.

   El filtrado avanzado es una gran adición a las capacidades de búsqueda. Se ha agregado un valor booleano **no** Filter en el *destinatario*, el *remitente* y el *dominio del remitente* para permitir que los administradores investiguen mediante la exclusión de valores. Esta opción aparece en el parámetro Selection no *contiene ninguno de*. **No** permitirá a los administradores excluir los buzones de correo de alertas, los buzones de respuesta predeterminados de sus investigaciones y es útil para los casos en los que los administradores buscan un asunto específico (Subject = "atención") donde el destinatario se puede establecer en *ninguno de defaultMail@contoso.com*. Se trata de una búsqueda de valor exacta.

   ![Los destinatarios-' no contiene ningún filtro avanzado.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Filtrar por horas* ayudará a que el equipo de seguridad de su organización se despliega rápidamente. La duración de tiempo más corta permitida es de 30 minutos. Si puede restringir la acción sospechosa por período de tiempo (por ejemplo, ha pasado hace 3 horas), esto limitará el contexto y determinará con precisión el problema.

  ![La opción de filtrado por horas para restringir la cantidad de datos que los equipos de seguridad deben procesar y cuya duración más corta es de 30 minutos.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Campos en el explorador de amenazas**: el explorador de amenazas expone mucha más información de correo relacionada con la seguridad, como la *acción de entrega*, la *Ubicación de entrega*, la *acción especial*, la *direccionalidad*, las *invalidaciones*y la *amenaza de URL*. También permite que el equipo de seguridad de su organización investigue con una mayor certeza. 

    La *acción de entrega* es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:
    - **Delivered** : el correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él directamente.
    - Correo electrónico **no deseado** (entregado a correo no deseado): el correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los mensajes de correo electrónico en su carpeta de correo no deseado o eliminado.
    - **Bloqueado** : todos los mensajes de correo electrónico que se hayan puesto en cuarentena, que hayan fallado o que se hayan quitado. (El usuario no tiene acceso completamente a esto).
    - **Reemplazado** : todos los correos electrónicos en los que los datos adjuntos malintencionados se reemplazan por archivos. txt que indican que el archivo adjunto era malintencionado

    **Ubicación de entrega**: el filtro de ubicación de entrega está disponible para ayudar a los administradores a comprender dónde se ha finalizado el correo malintencionado sospechoso y qué acciones se han realizado en él. Los datos resultantes se pueden exportar a la hoja de cálculo. Las ubicaciones de entrega posibles son:
    - **Bandeja de entrada o carpeta** : el correo electrónico está en la bandeja de entrada o en una carpeta específica, de acuerdo con las reglas de correo electrónico.
    - Local **o externa** : el buzón de correo no existe en la nube, pero es local.
    - **Carpeta de correo no deseado** : el correo electrónico se encuentra en la carpeta de correo no deseado de un usuario.
    - **Carpeta elementos eliminados** : el correo electrónico se encuentra en la carpeta elementos eliminados del usuario.
    - **Cuarentena** : el correo electrónico que se encuentra en cuarentena y no en el buzón de un usuario.
    - **Failed** – el correo electrónico no pudo llegar al buzón.
    - **Perdido: el** correo electrónico se perdió en algún lugar del flujo de correo.

    **Direccionalidad**: esta opción permite al equipo de operaciones de seguridad filtrar por la ' dirección ' a la que procede un correo o se dirige. Los valores de direccionalción son *entrante*, *saliente*e interno de la *organización* (correspondiente al correo que entra en su organización desde fuera, se envía fuera de su organización o se envía internamente a su organización, respectivamente). Esta información puede ayudar a los equipos de operaciones de seguridad a entanar la suplantación y la suplantación, ya que no coinciden entre el valor de la direccionalidad (por ejemplo, *Entrante*) y el dominio del remitente (que *parece* ser un dominio interno) será evidente. El valor de direccionalidad es independiente y puede ser diferente del seguimiento de mensajes. Los resultados se pueden exportar a la hoja de cálculo.

    **Invalidaciones**: este filtro recibe información que aparece en la ficha de detalles del correo y la usa para exponer dónde se han *invalidado*las directivas de usuario o de la organización, así como para permitir y bloquear el bloqueo de correo. Lo más importante de este filtro es que ayuda al equipo de seguridad de su organización a ver cuántos correos electrónicos sospechosos se han entregado debido a la configuración. Esto les da la oportunidad de modificar los bloques de permitidos y los bloques según sea necesario. Este conjunto de resultados de este filtro se puede exportar a hoja de cálculo.

|Invalidaciones del explorador de amenazas  | Significado  |
|---------|---------|
|Permitido por la Directiva de la organización     |   Se permitió el correo al buzón tal y como lo indicó la Directiva de la organización.       |
|Bloqueado por la Directiva de la organización      |  Se ha bloqueado el correo para que no se entregue en el buzón como se indicó en la Directiva de la organización.    |
|Extensión de archivo bloqueada por la Directiva de la organización     | El archivo se bloqueó para que no se entregue en el buzón de correo según lo indicó la Directiva de la organización.        |
|Permitido por la Directiva de usuario     | El correo se permitía en el buzón tal como lo indicó la Directiva de usuario.        |
|Bloqueado por la Directiva de usuario     | Se ha bloqueado el correo para que no se entregue en el buzón tal como lo indicó la Directiva de usuario.        |

**Amenaza de dirección URL**: el campo de la amenaza URL se incluye en la pestaña de *detalles* de un correo electrónico para indicar la amenaza que presenta una dirección URL. Las amenazas que presenta una dirección URL pueden incluir *malware*, *phish*o *correo no deseado*, y una dirección URL *sin amenazas no* dirá *ninguna* en la sección amenazas.

7. **Vista escala de tiempo del correo electrónico**: es posible que el equipo de operaciones de seguridad necesite profundizar en los detalles del correo electrónico para investigar más. La escala de tiempo de correo electrónico permite a los administradores ver las acciones realizadas en un correo electrónico desde la entrega hasta la entrega posterior. Para ver una escala de tiempo de correo electrónico, haga clic en el asunto de un mensaje de correo electrónico y, a continuación, en correo electrónico escala de tiempo. (Aparece entre otros títulos en el panel, como resumen o detalles). Estos resultados se pueden exportar a la hoja de cálculo.

    La escala de tiempo de correo electrónico se abrirá en una tabla que muestra todos los eventos de entrega y posterior a la entrega del correo electrónico. Si no hay más acciones en el correo electrónico, debería ver un solo evento para la entrega original que indique un resultado, como *bloqueado*, con un veredicto como *phish*. Los administradores pueden exportar toda la escala de tiempo de correo electrónico, incluidos todos los detalles de la pestaña y el correo electrónico (como el asunto, el remitente, el destinatario, la red y el identificador del mensaje). La escala de tiempo del correo electrónico reduce la aleatoriedad porque hay menos tiempo dedicado a comprobar las distintas ubicaciones para tratar de comprender los eventos que han sucedido desde que llegó el correo electrónico. Cuando se producen varios eventos en, o cerca de, al mismo tiempo en un correo electrónico, esos eventos se muestran en una vista de escala de tiempo.

8. **Vista previa/descarga**: el explorador de amenazas proporciona al equipo de operaciones de seguridad los detalles que necesitan para investigar el correo electrónico sospechoso. El equipo de operaciones de seguridad puede:

    - [Compruebe la acción y la ubicación de entrega](#check-the-delivery-action-and-location).

    - [Vea la escala de tiempo del correo electrónico](#view-the-timeline-of-your-email).

    ##### <a name="check-the-delivery-action-and-location"></a>Comprobar la acción y la ubicación de la entrega

    En el [Explorador de amenazas (y en detección en tiempo real)](threat-explorer.md), ahora tiene columnas de **acción de entrega** y ubicación de **entrega** en lugar de la columna de **Estado de entrega** anterior. Esto da como resultado una imagen más completa de la ubicación de los mensajes de correo electrónico. Una parte del objetivo de este cambio es facilitar las investigaciones para los equipos de operaciones de seguridad, pero el resultado neto es conocer la ubicación de los mensajes de correo electrónico con problemas de un vistazo.

    El estado de entrega ahora se divide en dos columnas:

    - **Acción de entrega** : ¿Cuál es el estado de este correo electrónico?

    - **Ubicación de entrega** : ¿Dónde se distribuyó este correo electrónico como resultado?

    La acción de entrega es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:

    - **Delivered** : el correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él directamente.

    - Correo electrónico **no deseado** : el correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los mensajes de correo electrónico en su carpeta de correo no deseado o eliminado.

    - **Bloqueado** : todos los mensajes de correo electrónico que se hayan puesto en cuarentena, que hayan fallado o que se hayan quitado. (El usuario no tiene acceso completamente a esto).

    - **Reemplazado** : cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por archivos. txt que indican que los datos adjuntos eran malintencionados.
 
    Ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a una acción de entrega. Este campo se agregó para proporcionar información sobre la acción tomada cuando se encuentra un mensaje problemático. Estos son los valores posibles de la ubicación de entrega:

    - **Bandeja de entrada o carpeta** : el correo electrónico está en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).

    - Local **o externa** : el buzón de correo no existe en la nube pero es local.

    - **Carpeta de correo no deseado** : el correo electrónico se encuentra en la carpeta de correo no deseado del usuario.

    - **Carpeta elementos eliminados** : el correo electrónico se encuentra en la carpeta elementos eliminados del usuario.

    - **Cuarentena** : el correo electrónico que se encuentra en cuarentena y no en el buzón de un usuario.

    - **Failed** – el correo electrónico no pudo llegar al buzón.

    - **Descartado** : el correo electrónico se pierde en algún lugar del flujo de correo.

     ##### <a name="view-the-timeline-of-your-email"></a>Ver la escala de tiempo del correo electrónico
  
     La **escala de tiempo de correo electrónico** es un campo en el explorador de amenazas que facilita la búsqueda del equipo de operaciones de seguridad. Cuando se producen varios eventos en o cerca de la misma hora en un correo electrónico, esos eventos se muestran en una vista de escala de tiempo. Algunos de los eventos que se producen después de la entrega en el correo electrónico se capturan en la columna **acciones especiales** . La combinación de información de la escala de tiempo de un mensaje de correo electrónico con cualquier acción especial realizada tras la entrega proporciona a los administradores información sobre las directivas y el tratamiento de las amenazas (por ejemplo, dónde se enrutó el correo y, en algunos casos, qué es la evaluación final).

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view. 
    
    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was. 

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body) 

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps: 

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 
    
2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table. 

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
