---
title: Búsqueda en el registro de auditoría para solucionar problemas de escenarios comunes
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Obtenga información sobre cómo usar la herramienta de búsqueda de registros de auditoría de Microsoft 365 para ayudar a solucionar problemas comunes de soporte técnico para las cuentas de correo electrónico.
ms.openlocfilehash: 57d8cfd1cbb07300b7cd69fb78ff6a0b33b302f5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097192"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Búsqueda en el registro de auditoría para investigar problemas comunes de soporte técnico

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En este artículo se describe cómo usar la herramienta de búsqueda de registros de auditoría para ayudarle a investigar problemas comunes de soporte técnico. Esto incluye el uso del registro de auditoría para:

- Búsqueda de la dirección IP del equipo usado para acceder a una cuenta en peligro
- Determinar quién configuró el reenvío de correo electrónico para un buzón
- Determinar si un usuario eliminó elementos de correo electrónico en su buzón
- Determinar si un usuario creó una regla de bandeja de entrada
- Investigar por qué un usuario fuera de la organización ha iniciado sesión correctamente
- Búsqueda de actividades de buzón realizadas por usuarios con licencias que no son de E5
- Búsqueda de actividades de buzón realizadas por usuarios delegados

## <a name="using-the-audit-log-search-tool"></a>Uso de la herramienta de búsqueda de registros de auditoría

Cada uno de los escenarios de solución de problemas descritos en este artículo se basa en el uso de la herramienta de búsqueda de registros de auditoría en el portal de cumplimiento de Microsoft Purview. En esta sección se enumeran los permisos necesarios para buscar en el registro de auditoría y se describen los pasos para acceder a las búsquedas de registros de auditoría y ejecutarlas. En cada sección de escenario se explica cómo configurar una consulta de búsqueda de registros de auditoría y qué buscar en la información detallada de los registros de auditoría que coinciden con los criterios de búsqueda.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Permisos necesarios para usar la herramienta de búsqueda de registros de auditoría

Debe tener asignado el rol registros de auditoría de View-Only o registros de auditoría en Exchange Online para buscar en el registro de auditoría. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página de **Permisos** del <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>. Los administradores globales de Office 365 y Microsoft 365 se agregan automáticamente como miembros del grupo de roles de administración de la organización en Exchange Online. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](/Exchange/permissions-exo/role-groups).

### <a name="running-audit-log-searches"></a>Ejecución de búsquedas de registros de auditoría

En esta sección se describen los conceptos básicos para crear y ejecutar búsquedas de registros de auditoría. Use estas instrucciones como punto de partida para cada escenario de solución de problemas de este artículo. Para obtener instrucciones paso a paso más detalladas, consulte [Búsqueda en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Vaya a <https://compliance.microsoft.com/auditlogsearch> e inicie sesión con su cuenta profesional o educativa.
  
    Aparecerá la página **Auditoría**.
  
    ![Configure los criterios y, a continuación, seleccione Buscar para ejecutar la búsqueda.](../media/AuditLogSearchPage1.png)
  
2. Puede configurar los siguientes criterios de búsqueda. Cada escenario de solución de problemas de este artículo recomienda instrucciones específicas para configurar estos campos.
  
   a. **Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fecha y hora para mostrar los eventos que se produjeron dentro de ese período. Los últimos siete días se seleccionan de forma predeterminada. La fecha y la hora se presentan en formato de Hora universal coordinada (UTC). El intervalo máximo de fecha que puede especificar es 90 días.

   b. **Actividades:** Seleccione la lista desplegable para mostrar las actividades que puede buscar. Después de que ejecute la búsqueda, solo se muestran las entradas seleccionadas del registro de auditoría de las actividades. Al seleccionar **Mostrar resultados para todas las actividades** , se muestran los resultados de todas las actividades que cumplen los demás criterios de búsqueda. También tendrá que dejar este campo en blanco en algunos de los escenarios de solución de problemas.
  
    c. **Usuarios:** Haga clic en este cuadro y seleccione uno o varios usuarios para mostrar los resultados de la búsqueda. Los registros de auditoría de la actividad seleccionada realizada por los usuarios seleccionados en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas de todos los usuarios (y cuentas de servicio) de su organización.
  
    d. **Archivo, carpeta o sitio:** Escriba algunos o todos los nombres de archivo o carpeta para buscar la actividad relacionada con el archivo de carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o carpeta. Si usa una dirección URL, asegúrese de escribir la ruta de acceso de dirección URL completa o, si solo escribe una parte de la dirección URL, no incluya ningún carácter o espacio especial. Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas de la organización. Este campo se deja en blanco en todos los escenarios de solución de problemas de este artículo.
  
3. Seleccione **Buscar** para ejecutar la búsqueda con los criterios de búsqueda.
  
    Los resultados de la búsqueda se cargan y, después de unos instantes, se muestran en una página de la herramienta de búsqueda de registros de auditoría. Cada una de las secciones de este artículo proporciona instrucciones sobre las cosas que se van a buscar en el contexto del escenario de solución de problemas específico.

    Para obtener más información sobre cómo ver y exportar resultados de búsqueda de registros de auditoría, consulte:

    - [Visualización de los resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
  
    - [Exportar resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-3-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Búsqueda de la dirección IP del equipo usado para acceder a una cuenta en peligro

La dirección IP correspondiente a una actividad realizada por cualquier usuario se incluye en la mayoría de los registros de auditoría. La información sobre el cliente usado también se incluye en el registro de auditoría.

A continuación se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** Si es relevante para su caso, seleccione una actividad específica para buscar. Para solucionar problemas de cuentas en peligro, considere la posibilidad de seleccionar la actividad **Usuario que inició sesión en el buzón en** **Exchange actividades de buzón**. Esto devuelve registros de auditoría que muestran la dirección IP que se usó al iniciar sesión en el buzón. De lo contrario, deje este campo en blanco para devolver los registros de auditoría de todas las actividades. 

> [!TIP]
> Si deja este campo en blanco, se devolverán las actividades **UserLoggedIn**, que es una actividad Azure Active Directory que indica que alguien ha iniciado sesión en una cuenta de usuario. Use el filtrado en los resultados de la búsqueda para mostrar los registros de auditoría **UserLoggedIn** .

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas aplicable a la investigación.

**Usuarios:** Si va a investigar una cuenta en peligro, seleccione el usuario cuya cuenta se ha puesto en peligro. Esto devuelve registros de auditoría de las actividades realizadas por esa cuenta de usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, la dirección IP de cada actividad se muestra en la columna **Dirección IP** de los resultados de la búsqueda. Seleccione el registro en los resultados de la búsqueda para ver información más detallada en la página de control flotante.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Determinar quién configuró el reenvío de correo electrónico para un buzón

Cuando se configura el reenvío de correo electrónico para un buzón, los mensajes de correo electrónico que se envían al buzón se reenvía a otro buzón. Los mensajes se pueden reenviar a los usuarios dentro o fuera de la organización. Cuando se configura el reenvío de correo electrónico en un buzón de correo, el cmdlet de Exchange Online subyacente que se usa es **Set-Mailbox**.

A continuación se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** Deje este campo en blanco para que la búsqueda devuelva registros de auditoría para todas las actividades. Esto es necesario para devolver los registros de auditoría relacionados con el cmdlet **Set-Mailbox** .

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas aplicable a la investigación.

**Usuarios:** A menos que investigue un problema de reenvío de correo electrónico para un usuario específico, deje este campo en blanco. Esto le ayuda a identificar si se configuró el reenvío de correo electrónico para cualquier usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, seleccione **Filtrar resultados** en la página de resultados de la búsqueda. En el cuadro del encabezado **de columna Actividad** , escriba **Set-Mailbox** para que solo se muestren los registros de auditoría relacionados con el cmdlet **Set-Mailbox** .

![Filtrado de los resultados de una búsqueda de registros de auditoría.](../media/emailforwarding1.png)

En este punto, debe examinar los detalles de cada registro de auditoría para determinar si la actividad está relacionada con el reenvío de correo electrónico. Seleccione el registro de auditoría para mostrar la página desplegable **Detalles** y, a continuación, seleccione **Más información**. En la captura de pantalla y las descripciones siguientes se resalta la información que indica que el reenvío de correo electrónico se estableció en el buzón.

![Información detallada del registro de auditoría.](../media/emailforwarding2.png)

a. En el campo **ObjectId** , se muestra el alias del buzón en el que se estableció el reenvío de correo electrónico. Este buzón también se muestra en la columna **Elemento** de la página de resultados de búsqueda.

b. En el campo **Parámetros** , el valor *ForwardingSmtpAddress* indica que el reenvío de correo electrónico se estableció en el buzón. En este ejemplo, el correo se reenvía a la dirección de correo electrónico mike@contoso.com, que está fuera de la organización alpinehouse.onmicrosoft.com.

c. El valor *True* del parámetro *DeliverToMailboxAndForward* indica que se entrega una copia del mensaje a sarad@alpinehouse.onmicrosoft.com *y* se reenvía a la dirección de correo electrónico especificada por el parámetro *ForwardingSmtpAddress* , que en este ejemplo es mike@contoso.com. Si el valor del parámetro *DeliverToMailboxAndForward* se establece en *False*, el correo electrónico solo se reenvía a la dirección especificada por el parámetro *ForwardingSmtpAddress* . No se entrega al buzón especificado en el campo **ObjectId** .

d. El campo **UserId** indica el usuario que estableció el reenvío de correo electrónico en el buzón especificado en el campo **ObjectId** . Este usuario también se muestra en la columna **Usuario** de la página de resultados de búsqueda. En este caso, parece que el propietario del buzón estableció el reenvío de correo electrónico en su buzón.

Si determina que no se debe establecer el reenvío de correo electrónico en el buzón de correo, puede quitarlo ejecutando el siguiente comando en Exchange Online PowerShell:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Para obtener más información sobre los parámetros relacionados con el reenvío de correo electrónico, consulte el artículo [Set-Mailbox](/powershell/module/exchange/set-mailbox) .

## <a name="determine-if-a-user-deleted-email-items"></a>Determinar si un usuario eliminó elementos de correo electrónico

A partir de enero de 2019, Microsoft activa el registro de auditoría de buzones de correo de forma predeterminada para todas las organizaciones de Office 365 y Microsoft. Esto significa que ciertas acciones realizadas por los propietarios de buzones de correo se registran automáticamente y los registros de auditoría de buzón correspondientes están disponibles al buscarlos en el registro de auditoría del buzón. Antes de que la auditoría de buzones se activara de forma predeterminada, tenía que habilitarla manualmente para cada buzón de correo de usuario de la organización. 

Las acciones de buzón registradas de forma predeterminada incluyen las acciones de buzón SoftDelete y HardDelete realizadas por los propietarios del buzón. Esto significa que puede usar los pasos siguientes para buscar en el registro de auditoría eventos relacionados con elementos de correo electrónico eliminados. Para obtener más información sobre la auditoría de buzones de correo en de forma predeterminada, vea [Administrar la auditoría de buzones](enable-mailbox-auditing.md).

A continuación se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** En **Exchange actividades de buzón de correo**, seleccione una o ambas de las siguientes actividades:

- **Mensajes eliminados de la carpeta Elementos eliminados:** Esta actividad corresponde a la acción de auditoría del buzón **softDelete** . Esta actividad también se registra cuando un usuario elimina permanentemente un elemento seleccionándolo y presionando **Mayús+Eliminar**. Una vez que un elemento se elimina de forma permanente, el usuario puede recuperarlo hasta que expire el período de retención de elementos eliminados.

- **Mensajes purgados del buzón de correo:** Esta actividad corresponde a la acción de auditoría del buzón **HardDelete** . Esto se registra cuando un usuario purga un elemento de la carpeta Elementos recuperables. Los administradores pueden usar la herramienta Búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar y recuperar elementos purgados hasta que expire el período de retención de elementos eliminados o más tiempo si el buzón del usuario está en espera.

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas aplicable a la investigación.

**Usuarios:** Si selecciona un usuario en este campo, la herramienta de búsqueda de registros de auditoría devuelve los registros de auditoría de los elementos de correo electrónico eliminados (SoftDeleted o HardDeleted) por el usuario especificado. A veces, es posible que el usuario que elimina un correo electrónico no sea el propietario del buzón.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, puede filtrar los resultados de la búsqueda para mostrar los registros de auditoría de los elementos eliminados temporalmente o de los elementos eliminados de forma rígida. Seleccione el registro de auditoría para mostrar la página desplegable **Detalles** y, a continuación, seleccione **Más información**. En el campo **AffectedItems** se muestra información adicional sobre el elemento eliminado, como la línea de asunto y la ubicación del elemento cuando se eliminó. En las capturas de pantalla siguientes se muestra un ejemplo del campo **AffectedItems** de un elemento eliminado temporalmente y un elemento eliminado de forma rígida.

**Ejemplo de campo AffectedItems para elemento eliminado temporalmente**

![Registro de auditoría del elemento eliminado temporalmente.](../media/softdeleteditem.png)

**Ejemplo de campo AffectedItems para elemento eliminado de forma rígida**

![Registro de auditoría del elemento de correo electrónico eliminado de forma rígida.](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Recuperación de elementos de correo electrónico eliminados

Los usuarios pueden recuperar elementos eliminados temporalmente si el período de retención de elementos eliminados no ha expirado. En Exchange Online, el período de retención de elementos eliminados predeterminado es de 14 días, pero los administradores pueden aumentar esta configuración a un máximo de 30 días. Apunte a los usuarios al [artículo Recuperar elementos eliminados o correo electrónico en Outlook en la Web](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) para obtener instrucciones sobre cómo recuperar elementos eliminados.

Como se explicó anteriormente, es posible que los administradores puedan recuperar elementos eliminados de forma rígida si el período de retención de elementos eliminados no ha expirado o si el buzón está en espera, en cuyo caso los elementos se conservan hasta que expire la duración de la suspensión. Al ejecutar una búsqueda de contenido, los elementos eliminados temporalmente y eliminados de forma rígida en la carpeta Elementos recuperables se devuelven en los resultados de la búsqueda si coinciden con la consulta de búsqueda. Para obtener más información sobre cómo ejecutar búsquedas de contenido, consulte [Búsqueda de contenido en Office 365](content-search.md).

> [!TIP]
> Para buscar elementos de correo electrónico eliminados, busque la totalidad o parte de la línea de asunto que se muestra en el campo **AffectedItems** del registro de auditoría.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Determinar si un usuario creó una regla de bandeja de entrada

Cuando los usuarios crean una regla de bandeja de entrada para su buzón de Exchange Online, se guarda un registro de auditoría correspondiente en el registro de auditoría. Para obtener más información sobre las reglas de bandeja de entrada, consulte:

- [Uso de reglas de bandeja de entrada en Outlook en la Web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Administración de mensajes de correo electrónico en Outlook mediante reglas](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

A continuación se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** En **Exchange actividades de buzón de correo**, seleccione una o ambas de las siguientes actividades:

- **New-InboxRule Cree una nueva regla de bandeja de entrada a partir de Outlook Web App**. Esta actividad devuelve registros de auditoría cuando se crean reglas de bandeja de entrada mediante Outlook aplicación web o Exchange Online PowerShell.

- **Se han actualizado las reglas de bandeja de entrada de Outlook cliente**. Esta actividad devuelve registros de auditoría cuando se crean, modifican o quitan reglas de bandeja de entrada mediante el cliente de escritorio de Outlook.

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas aplicable a la investigación.

**Usuarios:** A menos que investigue a un usuario específico, deje este campo en blanco. Esto le ayuda a identificar las nuevas reglas de bandeja de entrada configuradas por cualquier usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, los registros de auditoría de esta actividad se muestran en los resultados de la búsqueda. Seleccione un registro de auditoría para mostrar la página desplegable **Detalles** y, a continuación, seleccione **Más información**. La información sobre la configuración de la regla de bandeja de entrada se muestra en el campo **Parámetros** . En la captura de pantalla y las descripciones siguientes se resalta la información sobre las reglas de bandeja de entrada.

![Registro de auditoría para la nueva regla de bandeja de entrada.](../media/NewInboxRuleRecord.png)

a. En el campo **ObjectId** , se muestra el nombre completo de la regla de bandeja de entrada. Este nombre incluye el alias del buzón del usuario (por ejemplo, SaraD) y el nombre de la regla de bandeja de entrada (por ejemplo, "Mover mensajes del administrador").

b. En el campo **Parámetros** , se muestra la condición de la regla de bandeja de entrada. En este ejemplo, el parámetro *From* especifica la condición. El valor definido para el parámetro *From* indica que la regla de bandeja de entrada actúa en el correo electrónico enviado por admin@alpinehouse.onmicrosoft.com. Para obtener una lista completa de los parámetros que se pueden usar para definir condiciones de reglas de bandeja de entrada, consulte el artículo [New-InboxRule](/powershell/module/exchange/new-inboxrule) .

c. El parámetro *MoveToFolder* especifica la acción de la regla de bandeja de entrada. En este ejemplo, los mensajes recibidos de admin@alpinehouse.onmicrosoft.com se mueven a la carpeta denominada *AdminSearch*. Consulte también el artículo [New-InboxRule](/powershell/module/exchange/new-inboxrule) para obtener una lista completa de los parámetros que se pueden usar para definir la acción de una regla de bandeja de entrada.

d. El campo **UserId** indica el usuario que creó la regla de bandeja de entrada especificada en el campo **ObjectId** . Este usuario también se muestra en la columna **Usuario** de la página de resultados de búsqueda.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Investigar por qué un usuario fuera de la organización ha iniciado sesión correctamente

Al revisar los registros de auditoría en el registro de auditoría, es posible que vea registros que indican que Azure Active Directory ha autenticado un usuario externo y que ha iniciado sesión correctamente en su organización. Por ejemplo, un administrador de contoso.onmicrosoft.com puede ver un registro de auditoría que muestra que un usuario de otra organización (por ejemplo, fabrikam.onmicrosoft.com) ha iniciado sesión correctamente en contoso.onmicrosoft.com. Del mismo modo, puede ver registros de auditoría que indican que los usuarios con una cuenta microsoft (MSA), como una Outlook.com o Live.com, han iniciado sesión correctamente en su organización. En estas situaciones, la actividad auditada es **El usuario ha iniciado sesión**. 

Este comportamiento es una característica del diseño de la aplicación. Azure Active Directory (Azure AD), el servicio de directorio, permite algo denominado *autenticación de paso a través* cuando un usuario externo intenta acceder a un sitio de SharePoint o a una ubicación de OneDrive de su organización. Cuando el usuario externo intenta hacerlo, se le pide que escriba sus credenciales. Azure AD usa las credenciales para autenticar al usuario, lo que significa que solo Azure AD comprueba que el usuario es quien dice ser. La indicación del inicio de sesión correcto en el registro de auditoría es el resultado de Azure AD autenticar al usuario. El inicio de sesión correcto no significa que el usuario haya podido acceder a ningún recurso ni realizar ninguna otra acción en su organización. Solo indica que el usuario se autenticó mediante Azure AD. Para que un usuario de paso a través acceda a SharePoint o OneDrive recursos, un usuario de su organización tendría que compartir explícitamente un recurso con el usuario externo enviándole una invitación para compartir o un vínculo de uso compartido anónimo. 

> [!NOTE]
> Azure AD solo permite la autenticación de paso a través para *aplicaciones propias*, como SharePoint Online y OneDrive para la Empresa. No se permite para otras aplicaciones de terceros.

Este es un ejemplo y descripciones de las propiedades pertinentes en un registro de auditoría para un **usuario que ha iniciado sesión en** un evento que es el resultado de la autenticación de paso a través. Seleccione el registro de auditoría para mostrar la página desplegable **Detalles** y, a continuación, seleccione **Más información**.

![Ejemplo de registro de auditoría para la autenticación de paso a través correcta.](../media/PassThroughAuth1.png)

   a. Este campo indica que el usuario que intentó acceder a un recurso de su organización no se encontró en la Azure AD de la organización.

   b. Este campo muestra el UPN del usuario externo que intentó acceder a un recurso de su organización. Este identificador de usuario también se identifica en las propiedades **User** y **UserId** del registro de auditoría.

   c. La propiedad **ApplicationId** identifica la aplicación que desencadenó la solicitud de inicio de sesión. El valor de 000000003-0000-0ff1-ce00-000000000000 en la propiedad ApplicationId de este registro de auditoría indica SharePoint Online. OneDrive para la Empresa también tiene este mismo ApplicationId.

   d. Esto indica que la autenticación de paso a través se realizó correctamente. En otras palabras, Azure AD ha autenticado correctamente al usuario. 

   e. El valor **RecordType** de **15** indica que la actividad auditada (UserLoggedIn) es un evento de inicio de sesión de Secure Token Service (STS) en Azure AD.

Para obtener más información sobre las otras propiedades que se muestran en un registro de auditoría UserLoggedIn, consulte la información de esquema relacionada con Azure AD en [Office 365 esquema de api de actividad de administración](/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema).

Estos son dos ejemplos de escenarios que darían lugar a una actividad de auditoría correcta **iniciada por el usuario** debido a la autenticación de paso a través: 

  - Un usuario con una cuenta microsoft (por ejemplo, SaraD@outlook.com) ha intentado acceder a un documento de una cuenta de OneDrive para la Empresa en fourthcoffee.onmicrosoft.com y no hay una cuenta de usuario invitado correspondiente para SaraD@outlook.com en fourthcoffee.onmicrosoft.com.

  - Un usuario con una cuenta profesional o educativa en una organización (por ejemplo, pilarp@fabrikam.onmicrosoft.com) ha intentado acceder a un sitio de SharePoint en contoso.onmicrosoft.com y no hay una cuenta de usuario invitado correspondiente para pilarp@fabrikam.com en contoso.onmicrosoft.com.

### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Sugerencias para investigar inicios de sesión correctos resultantes de la autenticación de paso a través

- Busque en el registro de auditoría las actividades realizadas por el usuario externo identificado en el registro **de auditoría Usuario que ha iniciado sesión** . Escriba el UPN para el usuario externo en el cuadro **Usuarios** y use un intervalo de fechas si es relevante para su escenario. Por ejemplo, puede crear una búsqueda con los siguientes criterios de búsqueda:

   ![Busque todas las actividades realizadas por el usuario externo.](../media/PassThroughAuth2.png)

    Además de las actividades **del usuario que ha iniciado sesión** , se pueden devolver otros registros de auditoría, como los que indican que un usuario de su organización ha compartido recursos con el usuario externo y si el usuario externo ha accedido, modificado o descargado un documento compartido con él.

- Busque SharePoint actividades de uso compartido que indiquen que se ha compartido un archivo con el usuario externo identificado por un **usuario que ha iniciado sesión en** el registro de auditoría. Para obtener más información, consulte [Usar la auditoría de uso compartido en el registro de auditoría](use-sharing-auditing.md).

- Exporte los resultados de la búsqueda de registros de auditoría que contienen registros relevantes para la investigación para que pueda usar Excel para buscar otras actividades relacionadas con el usuario externo. Para obtener más información, consulte  [Exportación, configuración y visualización de registros de auditoría](export-view-audit-log-records.md).

## <a name="search-for-mailbox-activities-performed-by-users-with-non-e5-licenses"></a>Búsqueda de actividades de buzón realizadas por usuarios con licencias que no son de E5

Incluso cuando la [auditoría de buzones activada de forma predeterminada](enable-mailbox-auditing.md) está activada para su organización, es posible que observe que los eventos de auditoría de buzones de algunos usuarios no se encuentran en las búsquedas de registros de auditoría mediante el centro de cumplimiento, el cmdlet **Search-UnifiedAuditLog** o la API de actividad de administración de Office 365. El motivo es que los eventos de auditoría de buzón solo se devolverán para los usuarios con licencias E5 cuando uno de los métodos anteriores busque en el registro de auditoría unificado.

Para recuperar registros de auditoría de buzones de correo para usuarios que no sean E5, puede realizar una de las siguientes soluciones alternativas:

- Habilite manualmente la auditoría de buzones en buzones individuales (ejecute el `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` comando en Exchange Online PowerShell). Después de hacerlo, busque actividades de auditoría de buzones mediante el centro de cumplimiento, el cmdlet **Search-UnifiedAuditLog** o la API de actividad de administración de Office 365.
  
  > [!NOTE]
  > Si la auditoría de buzones ya parece estar habilitada en el buzón de correo, pero las búsquedas no devuelven resultados, cambie el valor del parámetro _AuditEnabled_ a `$false` y vuelva a `$true`.
  
- Use los siguientes cmdlets en Exchange Online PowerShell:

  - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) para buscar usuarios específicos en el registro de auditoría del buzón.

  - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) para buscar usuarios específicos en el registro de auditoría del buzón y enviar los resultados por correo electrónico a los destinatarios especificados.

## <a name="search-for-mailbox-activities-performed-in-a-specific-mailbox-including-shared-mailboxes"></a>Buscar actividades de buzón realizadas en un buzón específico (incluidos los buzones compartidos)

Al usar la lista desplegable **Usuarios** en la herramienta de búsqueda de registros de auditoría en el centro de cumplimiento o el comando **Search-UnifiedAuditLog -UserIds** en Exchange Online PowerShell, puede buscar actividades realizadas por un usuario específico. Para las actividades de auditoría de buzones de correo, este tipo de búsqueda buscará las actividades realizadas por el usuario especificado. No garantiza que todas las actividades realizadas en el mismo buzón se devuelvan en los resultados de la búsqueda. Por ejemplo, una búsqueda de registros de auditoría no devolverá registros de auditoría para las actividades realizadas por un usuario delegado porque la búsqueda de actividades de buzón realizadas por un usuario específico no devolverá las actividades realizadas por un usuario delegado al que se le hayan asignado permisos para acceder al buzón de otro usuario. (Un usuario delegado es alguien al que se le ha asignado el permiso de buzón SendAs, SendOnBehalf o FullAccess al buzón de otro usuario).

Además, el uso de la lista desplegable **Usuario** en la herramienta de búsqueda de registros de auditoría o **Search-UnifiedAuditLog -UserIds** no devolverá resultados para las actividades realizadas en un buzón compartido.

Para buscar las actividades realizadas en un buzón específico o para buscar actividades realizadas en un buzón compartido, use la sintaxis siguiente al ejecutar el cmdlet **Search-UnifiedAuditLog** :

```powershell
Search-UnifiedAuditLog  -StartDate <date> -EndDate <date> -FreeText (Get-Mailbox <mailbox identity).ExchangeGuid
```

Por ejemplo, el siguiente comando devuelve registros de auditoría para las actividades realizadas en el buzón compartido del equipo de cumplimiento de Contoso entre agosto de 2020 y octubre de 2020:

```powershell
Search-UnifiedAuditLog  -StartDate 08/01/2020 -EndDate 10/31/2020 -FreeText (Get-Mailbox complianceteam@contoso.onmicrosoft.com).ExchangeGuid
```

Como alternativa, puede usar el cmdlet **Search-MailboxAuditLog** para buscar registros de auditoría para la actividad realizada en un buzón específico. Esto incluye la búsqueda de actividades realizadas en un buzón compartido.

En el ejemplo siguiente se devuelven registros de auditoría de buzón de correo para las actividades realizadas en el buzón compartido del equipo de cumplimiento de Contoso:

```powershell
Search-MailboxAuditLog -Identity complianceteam@contoso.onmicrosoft.com -StartDate 08/01/2020 -EndDate 10/31/2020 -ShowDetails
```

En el ejemplo siguiente se devuelven registros de auditoría del buzón de correo para las actividades realizadas en el buzón especificado por los usuarios delegados:

```powershell
Search-MailboxAuditLog -Identity <mailbox identity> -StartDate <date> -EndDate <date> -LogonTypes Delegate -ShowDetails
```

También puede usar el cmdlet **New-MailboxAuditLogSearch** para buscar en el registro de auditoría un buzón específico y enviar los resultados por correo electrónico a los destinatarios especificados.