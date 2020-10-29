---
title: Buscar en el registro de auditoría para solucionar escenarios comunes
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar la herramienta de búsqueda de registros de auditoría de Microsoft 365 para ayudar a solucionar problemas de compatibilidad comunes para las cuentas de correo electrónico.
ms.openlocfilehash: a32633d401156e00a45d15e4b38622b13bcb87cf
ms.sourcegitcommit: 21c3e44862854c74e4008cfb661840f069c6b709
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787596"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Buscar en el registro de auditoría para investigar problemas de compatibilidad comunes

En este artículo se describe cómo usar la herramienta de búsqueda de registros de auditoría para ayudarle a investigar problemas comunes de soporte técnico. Esto incluye el uso del registro de auditoría para:

- Buscar la dirección IP del equipo que se usa para obtener acceso a una cuenta en peligro
- Determinar quién ha configurado el reenvío de correo electrónico para un buzón
- Determinar si un usuario eliminó los elementos de correo electrónico de su buzón
- Determinar si un usuario creó una regla de bandeja de entrada
- Investigue por qué ha habido un inicio de sesión correcto por un usuario externo a la organización.
- Buscar actividades de buzón de correo realizadas por usuarios con licencias que no sean E5
- Buscar actividades de buzón de correo realizadas por usuarios delegados

## <a name="using-the-audit-log-search-tool"></a>Uso de la herramienta de búsqueda de registros de auditoría

Cada uno de los escenarios de solución de problemas descritos en este artículo se basa en el uso de la herramienta de búsqueda de registros de auditoría del centro de seguridad & cumplimiento. En esta sección se enumeran los permisos necesarios para buscar en el registro de auditoría y se describen los pasos para obtener acceso y ejecutar las búsquedas de registros de auditoría. En cada sección de escenario se explica cómo configurar una consulta de búsqueda de registros de auditoría y qué buscar en la información detallada de los registros de auditoría que coinciden con los criterios de búsqueda.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Permisos necesarios para usar la herramienta de búsqueda de registros de auditoría

Debe tener asignado el rol View-Only registros de auditoría o registros de auditoría en Exchange Online para buscar en el registro de auditoría. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página de **permisos** del centro de administración de Exchange. Los administradores globales de Office 365 y Microsoft 365 se agregan automáticamente como miembros del grupo de funciones de administración de la organización en Exchange Online. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Ejecución de búsquedas de registro de auditoría

En esta sección se describen los conceptos básicos para crear y ejecutar búsquedas de registros de auditoría. Siga estas instrucciones como punto de partida para cada escenario de solución de problemas de este artículo. Para obtener instrucciones detalladas paso a paso, consulte [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Vaya a [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) e inicie sesión con su cuenta profesional o educativa.
    
    La página del **registro de auditoría de búsqueda** será mostrada. 
    
    ![Configure los criterios y, a continuación, seleccione Buscar para ejecutar la búsqueda](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Puede configurar los siguientes criterios de búsqueda. Cada escenario de solución de problemas de este artículo recomienda una guía específica para configurar estos campos.
    
    a. **Actividades:** Seleccione la lista desplegable para mostrar las actividades que puede buscar. Después de ejecutar la búsqueda, solo se muestran los registros de auditoría de las actividades seleccionadas. Al seleccionar **Mostrar resultados para todas las actividades** , se muestran los resultados de todas las actividades que cumplen los otros criterios de búsqueda. También tendrá que dejar este campo en blanco en algunos de los escenarios de solución de problemas.
    
    b. Fecha de **Inicio** y **fecha de finalización:** Seleccione un intervalo de fechas y horas para mostrar los eventos que se produjeron dentro de ese período. Los últimos siete días están seleccionados de forma predeterminada. La fecha y la hora se presentan en formato de Hora universal coordinada (UTC). El intervalo máximo de fecha que puede especificar es 90 días.

    c. **Usuarios:** Haga clic en este cuadro y, a continuación, seleccione uno o más usuarios para los que mostrar los resultados de la búsqueda. Los registros de auditoría para la actividad seleccionada realizada por los usuarios que seleccione en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas de todos los usuarios (y cuentas de servicio) de su organización.
    
    d. **Archivo, carpeta o sitio:** Escriba todo o parte del nombre de un archivo o una carpeta para buscar actividades relacionadas con el archivo de la carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o carpeta. Si usa una dirección URL, asegúrese de escribir la ruta de acceso completa de la dirección URL o, si solo escribe una parte de la dirección URL, no incluya ningún carácter o espacio especial. Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas de la organización. Este campo se deja en blanco en todos los escenarios de solución de problemas de este artículo.
    
5. Seleccione **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 
    
    Los resultados de la búsqueda se cargan y, después de unos segundos, se muestran en **resultados** en la página de **búsqueda de registros de auditoría** . En cada una de las secciones de este artículo se proporcionan instrucciones sobre los elementos que se deben buscar en el contexto del escenario de solución de problemas específico.

    Para obtener más información acerca de cómo ver, filtrar o exportar los resultados de la búsqueda de registros de auditoría, vea:

    - [Ver los resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrar resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportar resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Buscar la dirección IP del equipo que se usa para obtener acceso a una cuenta en peligro

La dirección IP correspondiente a una actividad realizada por cualquier usuario se incluye en la mayoría de los registros de auditoría. La información sobre el cliente usado también se incluye en el registro de auditoría.

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** Si es relevante para su caso, seleccione una actividad específica que desee buscar. Para solucionar problemas de cuentas comprometidas, considere la posibilidad de seleccionar la actividad **usuario de sesión iniciada** en el buzón en **actividades de buzón de Exchange** . Esto devuelve registros de auditoría que muestran la dirección IP que se utilizó al iniciar sesión en el buzón. De lo contrario, deje este campo en blanco para devolver los registros de auditoría de todas las actividades. 

> [!TIP]
> Si deja este campo en blanco, se devolverá **UserLoggedIn** actividades, que es una actividad de Azure Active Directory que indica que alguien ha iniciado sesión en una cuenta de usuario. Use el filtrado en los resultados de la búsqueda para mostrar los registros de auditoría de **UserLoggedIn** .

**Fecha de inicio** y **fecha de finalización:** Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios:** Si está investigando una cuenta en peligro, seleccione el usuario cuya cuenta se ha puesto en peligro. Esto devuelve registros de auditoría para actividades realizadas por esa cuenta de usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, la dirección IP de cada actividad se muestra en la columna **dirección IP** de los resultados de la búsqueda. Seleccione el registro en los resultados de la búsqueda para ver información más detallada en la página de flotante.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Determinar quién ha configurado el reenvío de correo electrónico para un buzón

Cuando se configura el reenvío de correo electrónico para un buzón, los mensajes de correo electrónico que se envían al buzón se reenvían a otro buzón. Los mensajes se pueden desviar a los usuarios dentro o fuera de la organización. Cuando se configura el reenvío de correo electrónico en un buzón, el cmdlet de Exchange Online subyacente que se usa es **set-Mailbox** .

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** Deje este campo en blanco para que la búsqueda devuelva registros de auditoría para todas las actividades. Esto es necesario para devolver los registros de auditoría relacionados con el cmdlet **set-Mailbox** .

**Fecha de inicio** y **fecha de finalización:** Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios:** A menos que esté investigando un problema de reenvío de correo para un usuario específico, deje este campo en blanco. Esto le ayuda a identificar si el reenvío de correo electrónico se ha configurado para cualquier usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, seleccione **filtrar resultados** en la página de resultados de búsqueda. En el cuadro en encabezado de columna **actividad** , escriba **set-Mailbox** para que solo se muestren los registros de auditoría relacionados con el cmdlet **set-Mailbox** .

![Filtrado de los resultados de una búsqueda de registros de auditoría](../media/emailforwarding1.png)

En este punto, tiene que mirar los detalles de cada registro de auditoría para determinar si la actividad está relacionada con el reenvío de correo electrónico. Seleccione el registro de auditoría para mostrar la página flotante de **detalles** y, a continuación, seleccione **más información** . La siguiente captura de pantalla y las descripciones resaltan la información que indica el reenvío de correo electrónico que se estableció en el buzón.

![Información detallada del registro de auditoría](../media/emailforwarding2.png)

a. En el campo **objectId** , se muestra el alias del buzón de correo en el que se ha configurado el reenvío de correo electrónico. Este buzón también se muestra en la columna de **elementos** de la página de resultados de búsqueda.

b. En el campo **parámetros** , el valor *ForwardingSmtpAddress* indica que el reenvío de correo electrónico se estableció en el buzón. En este ejemplo, el correo se envía a la dirección de correo electrónico mike@contoso.com, que está fuera de la organización alpinehouse.onmicrosoft.com.

c. El valor *true* del parámetro *DeliverToMailboxAndForward* indica que una copia del mensaje se entrega a SARAD@alpinehouse.onmicrosoft.com *y* se reenvía a la dirección de correo electrónico especificada por el parámetro *ForwardingSmtpAddress* , que en este ejemplo es Mike@contoso.com. Si el valor del parámetro *DeliverToMailboxAndForward* está establecido en *false* , el correo electrónico sólo se reenvía a la dirección especificada por el parámetro *ForwardingSmtpAddress* . No se entrega al buzón especificado en el campo **objectId** .

d. El campo **userid** indica el usuario que ha configurado el reenvío de correo electrónico en el buzón especificado en el campo **objectId** . Este usuario también se muestra en la columna **usuario** de la página de resultados de búsqueda. En este caso, parece que el propietario del buzón estableció el reenvío de correo electrónico en su buzón.

Si determina que no se debe establecer el reenvío de correo electrónico en el buzón, puede quitarlo ejecutando el siguiente comando en Exchange Online PowerShell:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Para obtener más información acerca de los parámetros relacionados con el reenvío de correo electrónico, consulte el artículo [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) .

## <a name="determine-if-a-user-deleted-email-items"></a>Determinar si un usuario eliminó elementos de correo electrónico

A partir de enero de 2019, Microsoft activa el registro de auditoría de buzones de correo de forma predeterminada para todas las organizaciones de Office 365 y Microsoft. Esto significa que determinadas acciones realizadas por los propietarios de los buzones de correo se registran automáticamente y que los registros de auditoría de buzón correspondientes están disponibles cuando se buscan en el registro de auditoría de buzones de correo. Antes de que se activara la auditoría de buzones de correo de forma predeterminada, tenía que habilitarla manualmente para cada buzón de usuario de la organización. 

Las acciones de buzón de correo registradas de forma predeterminada incluyen las acciones de buzón SoftDelete y HardDelete realizadas por los propietarios de buzones. Esto significa que puede usar los pasos siguientes para buscar en el registro de auditoría eventos relacionados con elementos de correo electrónico eliminados. Para obtener más información acerca de la auditoría de buzones de correo en de forma predeterminada, consulte [Manage Mailbox Auditing](enable-mailbox-auditing.md).

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** En **actividades de buzón de Exchange** , seleccione una o las dos actividades siguientes:

- **Mensajes eliminados de la carpeta elementos eliminados:** Esta actividad corresponde a la acción de auditoría del buzón de **SoftDelete** . Esta actividad también se registra cuando un usuario elimina permanentemente un elemento seleccionándolo y presionando **Mayús + Supr** . Una vez que un elemento se elimina de forma permanente, el usuario puede recuperarlo hasta que expire el período de retención de elementos eliminados.

- **Mensajes purgados del buzón:** Esta actividad corresponde a la acción de auditoría del buzón de **HardDelete** . Este registro se registra cuando un usuario purga un elemento de la carpeta elementos recuperables. Los administradores pueden usar la herramienta de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar y recuperar los elementos purgados hasta que expire el período de retención de elementos eliminados si el buzón de correo del usuario está en suspensión.

**Fecha de inicio** y **fecha de finalización:** Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios:** Si selecciona un usuario en este campo, la herramienta de búsqueda de registros de auditoría devuelve registros de auditoría para los elementos de correo electrónico que el usuario ha eliminado (SoftDeleted o HardDeleted). A veces, es posible que el usuario que elimine un correo electrónico no sea el propietario del buzón.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, puede filtrar los resultados de la búsqueda para mostrar los registros de auditoría de los elementos eliminados temporalmente o de los elementos eliminados permanentemente. Seleccione el registro de auditoría para mostrar la página flotante de **detalles** y, a continuación, seleccione **más información** . La información adicional sobre el elemento eliminado, como la línea de asunto y la ubicación del elemento cuando se elimina, se muestra en el campo **AffectedItems** . En las siguientes capturas de pantalla se muestra un ejemplo del campo **AffectedItems** de un elemento eliminado temporalmente y un elemento eliminado permanentemente.

**Ejemplo de campo AffectedItems para un elemento eliminado temporalmente**

![Registro de auditoría para elemento eliminado temporalmente](../media/softdeleteditem.png)

**Ejemplo de campo AffectedItems para un elemento eliminado permanentemente**

![Registro de auditoría para elemento de correo electrónico eliminado permanentemente](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Recuperar elementos de correo electrónico eliminados

Los usuarios pueden recuperar elementos eliminados temporalmente si no ha expirado el período de retención de elementos eliminados. En Exchange Online, el período de retención predeterminado de elementos eliminados es de 14 días, pero los administradores pueden aumentar esta configuración a un máximo de 30 días. Apunte a los usuarios al artículo [recuperar elementos eliminados o correo electrónico en Outlook en la web](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) para obtener instrucciones sobre cómo recuperar elementos eliminados.

Como se ha explicado anteriormente, los administradores pueden recuperar los elementos eliminados permanentemente si el período de retención de elementos eliminados no ha expirado o si el buzón está en retención, en cuyo caso los elementos se conservan hasta que expira la duración de retención. Cuando se ejecuta una búsqueda de contenido, los elementos eliminados temporalmente y eliminados permanentemente de la carpeta elementos recuperables se devuelven en los resultados de la búsqueda si coinciden con la consulta de búsqueda. Para obtener más información sobre cómo ejecutar búsquedas de contenido, vea [búsqueda de contenido en Office 365](content-search.md).

> [!TIP]
> Para buscar los elementos de correo electrónico eliminados, busque la línea de asunto parcial o la que aparece en el campo **AffectedItems** en el registro de auditoría.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Determinar si un usuario creó una regla de bandeja de entrada

Cuando los usuarios crean una regla de bandeja de entrada para su buzón de Exchange Online, se guarda un registro de auditoría correspondiente en el registro de auditoría. Para obtener más información acerca de las reglas de la bandeja de entrada, consulte:

- [Usar reglas de la bandeja de entrada en Outlook en la web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Administrar mensajes de correo electrónico en Outlook mediante reglas](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** En **actividades de buzón de Exchange** , seleccione **nueva-InboxRule crear/modificar/habilitar/deshabilitar la regla de bandeja de entrada** .

**Fecha de inicio** y **fecha de finalización:** Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios:** A menos que esté investigando a un usuario específico, deje este campo en blanco. Esto le ayuda a identificar nuevas reglas de la bandeja de entrada configuradas por cualquier usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, se muestran todos los registros de auditoría de esta actividad en los resultados de la búsqueda. Seleccione un registro de auditoría para mostrar la página flotante de **detalles** y, a continuación, seleccione **más información** . La información sobre la configuración de las reglas de la bandeja de entrada se muestra en el campo **parámetros** . La siguiente captura de pantalla y descripciones resaltan la información sobre las reglas de la bandeja de entrada

![Registro de auditoría para nueva regla de bandeja de entrada](../media/NewInboxRuleRecord.png)

a. En el campo **objectId** , se muestra el nombre completo de la regla de bandeja de entrada. Este nombre incluye el alias del buzón de correo del usuario (por ejemplo, Sara) y el nombre de la regla de bandeja de entrada (por ejemplo, "mover mensajes desde el administrador").

b. En el campo **parámetros** , se muestra la condición de la regla de la bandeja de entrada. En este ejemplo, la condición se especifica mediante el parámetro *from* . El valor definido para el parámetro *from* indica que la regla de la bandeja de entrada actúa en el correo electrónico enviado por admin@alpinehouse.onmicrosoft.com. Para obtener una lista completa de los parámetros que se pueden usar para definir las condiciones de las reglas de la bandeja de entrada, consulte el artículo [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule) .

c. El parámetro *MoveToFolder* especifica la acción para la regla de bandeja de entrada. En este ejemplo, los mensajes recibidos desde admin@alpinehouse.onmicrosoft.com se mueven a la carpeta denominada *AdminSearch* . Consulte también el artículo [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule) para obtener una lista completa de los parámetros que se pueden usar para definir la acción de una regla de bandeja de entrada.

d. El campo **userid** indica el usuario que creó la regla de bandeja de entrada especificada en el campo **objectId** . Este usuario también se muestra en la columna **usuario** de la página de resultados de búsqueda.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Investigue por qué ha habido un inicio de sesión correcto por un usuario externo a la organización.

Al revisar los registros de auditoría en el registro de auditoría, es posible que vea registros que indican que Azure Active Directory ha autenticado a un usuario externo y que ha iniciado sesión correctamente en su organización. Por ejemplo, un administrador de contoso.onmicrosoft.com puede ver un registro de auditoría que muestra que un usuario de una organización diferente (por ejemplo, fabrikam.onmicrosoft.com) inició sesión correctamente en contoso.onmicrosoft.com. De forma similar, es posible que vea registros de auditoría que indican a los usuarios con una cuenta de Microsoft (MSA), como un Outlook.com o Live.com, han iniciado sesión correctamente en su organización. En estos casos, la actividad auditada es el **usuario que ha iniciado sesión** . 

Este comportamiento es una característica del diseño de la aplicación. Azure Active Directory (Azure AD), el servicio de directorio, permite una *autenticación de paso a través* denominada cuando un usuario externo intenta acceder a un sitio de SharePoint o a una ubicación de OneDrive en la organización. Cuando el usuario externo intente hacerlo, se le pedirá que escriba sus credenciales. Azure AD usa las credenciales para autenticar al usuario, lo que significa que solo Azure AD comprueba que el usuario es quien dice ser. La indicación del inicio de sesión correcto en el registro de auditoría es el resultado de que Azure AD autentique al usuario. El inicio de sesión correcto no significa que el usuario haya podido obtener acceso a ningún recurso o realizar otras acciones en su organización. Solo indica que Azure AD ha autenticado al usuario. Para que un usuario de paso a través obtenga acceso a los recursos de SharePoint o de OneDrive, un usuario de la organización tendría que compartir explícitamente un recurso con el usuario externo enviándoles una invitación de uso compartido o un vínculo de uso compartido anónimo. 

> [!NOTE]
> Azure AD permite la autenticación de paso a través solo para *aplicaciones de origen* , como SharePoint Online y OneDrive para la empresa. No está permitido para otras aplicaciones de terceros.

Este es un ejemplo y descripciones de propiedades relevantes en un registro de auditoría para un **usuario registrado en** un evento que es el resultado de la autenticación de paso a través. Seleccione el registro de auditoría para mostrar la página flotante de **detalles** y, a continuación, seleccione **más información** .

![Ejemplo de registro de auditoría para la autenticación de paso a través correcta](../media/PassThroughAuth1.png)

   a. Este campo indica que el usuario que intentó tener acceso a un recurso de la organización no se encontró en el Azure AD de la organización.

   b. Este campo muestra el UPN del usuario externo que intentó tener acceso a un recurso de su organización. Este identificador de usuario también se identifica en las propiedades **User** y **userid** del registro de auditoría.

   c. La propiedad **ApplicationID** identifica la aplicación que desencadenó la solicitud de inicio de sesión. El valor de es 00000003-0000-0ff1-ce00-000000000000 que se muestra en la propiedad ApplicationId de este registro de auditoría indica SharePoint Online. OneDrive para la empresa también tiene este mismo ApplicationId.

   d. Esto indica que la autenticación de paso a través se realizó correctamente. En otras palabras, Azure AD ha autenticado correctamente a los usuarios. 

   e. El valor de **RecordType** es **15** indica que la actividad auditada (UserLoggedIn) es un evento de inicio de sesión del servicio de token seguro (STS) en Azure ad.

Para obtener más información acerca de otras propiedades mostradas en un registro de auditoría de UserLoggedIn, vea la información de esquema relacionado con Azure AD en el esquema de la [API de actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema).

A continuación se muestran dos escenarios de ejemplo que darían como resultado que un **usuario que ha iniciado sesión correctamente en** la actividad de auditoría debido a la autenticación de paso a través: 

  - Un usuario con una cuenta de Microsoft (como SaraD@outlook.com) intentó tener acceso a un documento en una cuenta de OneDrive para la empresa en fourthcoffee.onmicrosoft.com y no hay una cuenta de usuario invitado correspondiente para SaraD@outlook.com en fourthcoffee.onmicrosoft.com.

  - Un usuario con una cuenta profesional o educativa en una organización (como pilarp@fabrikam.onmicrosoft.com) ha tratado de tener acceso a un sitio de SharePoint en contoso.onmicrosoft.com y no hay una cuenta de usuario invitado correspondiente para pilarp@fabrikam.com en contoso.onmicrosoft.com.

### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Sugerencias para investigar los inicios de sesión correctos como resultado de la autenticación de paso a través

- Busque en el registro de auditoría actividades realizadas por el usuario externo identificado en el registro **de auditoría registrado del usuario** . Escriba el UPN del usuario externo en el cuadro **usuarios** y use un intervalo de fechas si es relevante para su escenario. Por ejemplo, puede crear una búsqueda con los siguientes criterios de búsqueda:

   ![Buscar todas las actividades realizadas por el usuario externo](../media/PassThroughAuth2.png)

    Además de las actividades **de inicio de sesión del usuario** , se pueden devolver otros registros de auditoría, tales que indican que un usuario de la organización compartió recursos con el usuario externo y si el usuario externo obtuvo acceso, modificó o descargó un documento compartido con ellos.

- Buscar actividades de uso compartido de SharePoint que indiquen que un archivo se ha compartido con el usuario externo identificado por un registro **de auditoría registrado** por un usuario. Para obtener más información, consulte [Usar la auditoría de uso compartido en el registro de auditoría](use-sharing-auditing.md).

- Exporte los resultados de la búsqueda de registros de auditoría que contengan registros relevantes para la investigación, de modo que pueda usar Excel para buscar otras actividades relacionadas con el usuario externo. Para obtener más información, vea  [exportar, configurar y ver registros de registro de auditoría](export-view-audit-log-records.md).

## <a name="search-for-mailbox-activities-performed-by-users-with-non-e5-licenses"></a>Buscar actividades de buzón de correo realizadas por usuarios con licencias que no sean E5

Incluso cuando la [Auditoría de buzones de correo](enable-mailbox-auditing.md) está activada de forma predeterminada para su organización, es posible que observe que los eventos de auditoría de buzones de correo de algunos usuarios no se encuentran en búsquedas de registro de auditoría mediante el centro de cumplimiento, el cmdlet **Search-UNIFIEDAUDITLOG** o la API de actividad de administración 365 de Office. El motivo es que solo se devolverán los eventos de auditoría de buzones de correo de los usuarios con licencias de E5 cuando uno de los métodos anteriores busque en el registro de auditoría unificado.

Para recuperar los registros de registro de auditoría de buzones de correo de usuarios que no son E5, puede realizar una de las siguientes soluciones:

- Habilite manualmente la auditoría de buzones de correo en buzones individuales (ejecute el `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` comando en Exchange Online PowerShell). Después de hacerlo, busque actividades de auditoría de buzones de correo mediante el centro de cumplimiento, el cmdlet **Search-UnifiedAuditLog** o la API de actividad de administración de Office 365.
  
  > [!NOTE]
  > Si la auditoría de buzones de correo ya está habilitada en el buzón de correo, pero las búsquedas no devuelven resultados, cambie el valor del parámetro _AuditEnabled_ a `$false` y, a continuación, otra vez a `$true` .
  
- Use los cmdlets siguientes en Exchange Online PowerShell:

  - [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) para buscar en el registro de auditoría de buzones de correo de determinados usuarios.

  - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) para buscar en el registro de auditoría de buzones de correo los usuarios específicos y para enviar los resultados por correo electrónico a los destinatarios especificados.

## <a name="search-for-mailbox-activities-performed-in-a-specific-mailbox-including-shared-mailboxes"></a>Buscar actividades de buzón de correo realizadas en un buzón específico (incluidos los buzones compartidos)

Cuando usa la lista desplegable **usuarios** en la herramienta de búsqueda de registros de auditoría en el centro de cumplimiento o el comando **Search-UnifiedAuditLog-userid** en Exchange Online PowerShell, puede buscar actividades realizadas por un usuario específico. Para las actividades de auditoría de buzones de correo, este tipo de búsqueda buscará actividades realizadas por el usuario especificado. No garantiza que todas las actividades realizadas en el mismo buzón de correo se devuelvan en los resultados de la búsqueda. Por ejemplo, una búsqueda de registros de auditoría no devolverá registros de auditoría para las actividades realizadas por un usuario delegado porque la búsqueda de actividades de buzón realizadas por un usuario específico no devolverá actividades realizadas por un usuario delegado al que se hayan asignado permisos para obtener acceso al buzón de otro usuario. (Un usuario delegado es alguien al que se le ha asignado el permiso enviaras, SendOnBehalf o FullAccess al buzón de otro usuario).

Además, el uso de la lista desplegable de **usuario** en la herramienta de búsqueda de registros de auditoría o la **búsqueda-UnifiedAuditLog-userids** no devolverá resultados para las actividades realizadas en un buzón compartido.

Para buscar las actividades realizadas en un buzón específico o para buscar actividades realizadas en un buzón compartido, use la siguiente sintaxis al ejecutar el cmdlet **Search-UnifiedAuditLog** :

```powershell
Search-UnifiedAuditLog  -StartDate <date> -EndDate <date> -FreeText (Get-Mailbox <mailbox identity).ExchangeGuid
```

Por ejemplo, el siguiente comando devuelve registros de auditoría para actividades realizadas en el buzón compartido del equipo de cumplimiento de Contoso entre el 2020 de agosto y el 2020 de octubre:

```powershell
Search-UnifiedAuditLog  -StartDate 08/01/2020 -EndDate 10/31/2020 -FreeText (Get-Mailbox complianceteam@contoso.onmicrosoft.com).ExchangeGuid
```

Como alternativa, puede usar el cmdlet **Search-MailboxAuditLog** para buscar registros de auditoría para la actividad realizada en un buzón específico. Esto incluye la búsqueda de actividades realizadas en un buzón compartido.

En el siguiente ejemplo se devuelven las entradas del registro de auditoría de buzones para actividades realizadas en el buzón compartido del equipo de cumplimiento de Contoso:

```powershell
Search-MailboxAuditLog -Identity complianceteam@contoso.onmicrosoft.com -StartDate 08/01/2020 -EndDate 10/31/2020 -ShowDetails
```

En el siguiente ejemplo, se devuelven las entradas del registro de auditoría de buzones para las actividades realizadas en el buzón especificado por usuarios delegados:

```powershell
Search-MailboxAuditLog -Identity <mailbox identity> -StartDate <date> -EndDate <date> -LogonTypes Delegate -ShowDetails
```

También puede usar el cmdlet **New-MailboxAuditLogSearch** para buscar en el registro de auditoría un buzón específico y enviar los resultados por correo electrónico a los destinatarios especificados.