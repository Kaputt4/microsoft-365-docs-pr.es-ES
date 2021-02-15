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
description: Obtenga información sobre cómo usar la herramienta de búsqueda de registros de auditoría de Microsoft 365 para ayudar a solucionar problemas comunes de soporte técnico para cuentas de correo electrónico.
ms.openlocfilehash: a32633d401156e00a45d15e4b38622b13bcb87cf
ms.sourcegitcommit: 21c3e44862854c74e4008cfb661840f069c6b709
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787596"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Buscar en el registro de auditoría para investigar problemas comunes de soporte técnico

En este artículo se describe cómo usar la herramienta de búsqueda de registros de auditoría para ayudarle a investigar problemas comunes de soporte técnico. Esto incluye el uso del registro de auditoría para:

- Buscar la dirección IP del equipo usado para obtener acceso a una cuenta comprometida
- Determinar quién ha configurado el reenvío de correo electrónico para un buzón
- Determinar si un usuario eliminó elementos de correo electrónico en su buzón
- Determinar si un usuario creó una regla de bandeja de entrada
- Investigar por qué un usuario externo a la organización ha realizado un inicio de sesión correcto
- Buscar actividades de buzón realizadas por usuarios con licencias que no son E5
- Búsqueda de actividades de buzón realizadas por usuarios delegados

## <a name="using-the-audit-log-search-tool"></a>Uso de la herramienta de búsqueda de registros de auditoría

Cada uno de los escenarios de solución de problemas descritos en este artículo se basa en el uso de la herramienta de búsqueda de registros de auditoría en el Centro de & cumplimiento. En esta sección se enumeran los permisos necesarios para buscar en el registro de auditoría y se describen los pasos para tener acceso y ejecutar búsquedas en el registro de auditoría. En cada sección de escenario se explica cómo configurar una consulta de búsqueda de registro de auditoría y qué buscar en la información detallada de los registros de auditoría que coinciden con los criterios de búsqueda.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Permisos necesarios para usar la herramienta de búsqueda de registros de auditoría

Debe tener asignado el rol View-Only registros de auditoría o registros de auditoría en Exchange Online para buscar en el registro de auditoría. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página de **permisos** del centro de administración de Exchange. Los administradores globales de Office 365 y Microsoft 365 se agregan automáticamente como miembros del grupo de roles Administración de la organización en Exchange Online. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Ejecución de búsquedas de registros de auditoría

En esta sección se describen los conceptos básicos para crear y ejecutar búsquedas de registro de auditoría. Use estas instrucciones como punto de partida para cada escenario de solución de problemas de este artículo. Para obtener instrucciones detalladas paso a paso, vea [Buscar en el registro de auditoría.](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)

1. Vaya e [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) inicie sesión con su cuenta de trabajo o escuela.
    
    La página del **registro de auditoría de búsqueda** será mostrada. 
    
    ![Configurar criterios y, a continuación, seleccionar Buscar para ejecutar la búsqueda](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Puede configurar los siguientes criterios de búsqueda. Cada escenario de solución de problemas de este artículo recomienda instrucciones específicas para configurar estos campos.
    
    a. **Actividades:** Seleccione la lista desplegable para mostrar las actividades que puede buscar. Después de ejecutar la búsqueda, solo se muestran los registros de auditoría de las actividades seleccionadas. Si selecciona **Mostrar resultados para todas las actividades,** se mostrarán los resultados de todas las actividades que cumplan los demás criterios de búsqueda. También tendrá que dejar este campo en blanco en algunos de los escenarios de solución de problemas.
    
    b. **Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fecha y hora para mostrar los eventos que se produjeron dentro de ese período. Los últimos siete días están seleccionados de forma predeterminada. La fecha y la hora se presentan en formato de Hora universal coordinada (UTC). El intervalo máximo de fecha que puede especificar es 90 días.

    c. **Usuarios:** Haga clic en este cuadro y, a continuación, seleccione uno o más usuarios para los que mostrar los resultados de la búsqueda. Los registros de auditoría de la actividad seleccionada realizada por los usuarios seleccionados en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas de todos los usuarios (y cuentas de servicio) de su organización.
    
    d. **Archivo, carpeta o sitio:** Escriba algunos o todos los nombres de un archivo o carpeta para buscar actividad relacionada con el archivo de carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o carpeta. Si usa una dirección URL, asegúrese de escribir la ruta de acceso completa de la dirección URL o, si solo escribe una parte de la dirección URL, no incluya ningún carácter o espacio especial. Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas de la organización. Este campo se deja en blanco en todos los escenarios de solución de problemas de este artículo.
    
5. Seleccione **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 
    
    Los resultados de la búsqueda se cargan y, después de un momento, se muestran en **Resultados** en la página de búsqueda **del registro de** auditoría. Cada una de las secciones de este artículo proporciona instrucciones sobre los aspectos que debe buscar en el contexto del escenario de solución de problemas específico.

    Para obtener más información acerca de cómo ver, filtrar o exportar resultados de búsqueda de registros de auditoría, vea:

    - [Ver los resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrar resultados de búsqueda](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportar resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Buscar la dirección IP del equipo usado para obtener acceso a una cuenta comprometida

La dirección IP correspondiente a una actividad realizada por cualquier usuario se incluye en la mayoría de los registros de auditoría. La información sobre el cliente usado también se incluye en el registro de auditoría.

Aquí se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** Si es relevante para su caso, seleccione una actividad específica para buscar. Para solucionar problemas de cuentas comprometidas, considere la posibilidad de seleccionar el usuario que ha **iniciado** sesión en la actividad del buzón en las **actividades de buzón de Exchange.** Esto devuelve registros de auditoría que muestran la dirección IP que se usaba al iniciar sesión en el buzón. De lo contrario, deje este campo en blanco para devolver los registros de auditoría de todas las actividades. 

> [!TIP]
> Si deja este campo en blanco, se devolverán las actividades **UserLoggedIn,** que es una actividad de Azure Active Directory que indica que alguien ha iniciado sesión en una cuenta de usuario. Use el filtrado en los resultados de la búsqueda para mostrar los **registros de auditoría UserLoggedIn.**

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas que sea aplicable a la investigación.

**Usuarios:** Si está investigando una cuenta en peligro, seleccione el usuario cuya cuenta se ha visto comprometida. Esto devuelve los registros de auditoría de las actividades realizadas por esa cuenta de usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, la dirección IP de cada actividad se muestra en la **columna dirección IP** en los resultados de la búsqueda. Seleccione el registro en los resultados de la búsqueda para ver información más detallada en la página desplegable.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Determinar quién ha configurado el reenvío de correo electrónico para un buzón

Cuando se configura el reenvío de correo electrónico para un buzón de correo, los mensajes de correo electrónico que se envían al buzón se reenvía a otro buzón. Los mensajes se pueden reenviar a usuarios dentro o fuera de la organización. Cuando se configura el reenvío de correo electrónico en un buzón, el cmdlet subyacente de Exchange Online que se usa es **Set-Mailbox**.

Aquí se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** Deje este campo en blanco para que la búsqueda devuelva registros de auditoría de todas las actividades. Esto es necesario para devolver los registros de auditoría relacionados con el cmdlet **Set-Mailbox.**

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas que sea aplicable a la investigación.

**Usuarios:** A menos que esté investigando un problema de reenvío de correo electrónico para un usuario específico, deje este campo en blanco. Esto le ayuda a identificar si el reenvío de correo electrónico se ha configurado para cualquier usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, seleccione **Filtrar resultados** en la página de resultados de búsqueda. En el cuadro **de** encabezado de columna Actividad, escriba **Set-Mailbox** para que solo se muestren los registros de auditoría relacionados con el cmdlet **Set-Mailbox.**

![Filtrado de los resultados de una búsqueda de registro de auditoría](../media/emailforwarding1.png)

En este punto, debe ver los detalles de cada registro de auditoría para determinar si la actividad está relacionada con el reenvío de correo electrónico. Seleccione el registro de auditoría para mostrar **la** página desplegable Detalles y, a continuación, seleccione **Más información.** La siguiente captura de pantalla y descripciones resaltan la información que indica que el reenvío de correo electrónico se estableció en el buzón.

![Información detallada del registro de auditoría](../media/emailforwarding2.png)

a. En el **campo ObjectId,** se muestra el alias del buzón en el que se estableció el reenvío de correo electrónico. Este buzón también se muestra en la columna **Elemento** de la página de resultados de búsqueda.

b. En el **campo Parámetros,** el valor *ForwardingSmtpAddress* indica que el reenvío de correo electrónico se estableció en el buzón. En este ejemplo, el correo se reenvía a la dirección de correo electrónico mike@contoso.com, que está fuera de alpinehouse.onmicrosoft.com organización.

c. El valor *True* para el parámetro *DeliverToMailboxAndForward* indica que una copia del mensaje se entrega *a* sarad@alpinehouse.onmicrosoft.com y se reenvía a la dirección de correo electrónico especificada por el parámetro *ForwardingSmtpAddress,* que en este ejemplo es mike@contoso.com. Si el valor del parámetro *DeliverToMailboxAndForward* se establece en *False*, el correo electrónico solo se reenvía a la dirección especificada por el parámetro *ForwardingSmtpAddress.* No se entrega al buzón especificado en el **campo ObjectId.**

d. El **campo UserId** indica el usuario que estableció el reenvío de correo electrónico en el buzón especificado en el **campo ObjectId.** Este usuario también se muestra en la columna **Usuario** de la página de resultados de búsqueda. En este caso, parece que el propietario del buzón estableció el reenvío de correo electrónico en su buzón.

Si determina que el reenvío de correo electrónico no debe establecerse en el buzón, puede quitarlo ejecutando el siguiente comando en Exchange Online PowerShell:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Para obtener más información acerca de los parámetros relacionados con el reenvío de correo electrónico, consulte el artículo [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)

## <a name="determine-if-a-user-deleted-email-items"></a>Determinar si un usuario eliminó elementos de correo electrónico

A partir de enero de 2019, Microsoft activará el registro de auditoría de buzones de forma predeterminada para todas las organizaciones de Office 365 y Microsoft. Esto significa que determinadas acciones realizadas por los propietarios de buzones de correo se registran automáticamente y los registros de auditoría de buzones correspondientes están disponibles cuando se buscan en el registro de auditoría de buzones. Antes de activar la auditoría de buzones de forma predeterminada, tenía que habilitarla manualmente para cada buzón de usuario de la organización. 

Las acciones de buzón registradas de forma predeterminada incluyen las acciones de buzón SoftDelete y HardDelete realizadas por los propietarios de buzones. Esto significa que puede seguir los pasos siguientes para buscar eventos relacionados con los elementos de correo electrónico eliminados en el registro de auditoría. Para obtener más información acerca de la auditoría de buzones de correo de forma predeterminada, vea [Administrar la auditoría de buzones de correo.](enable-mailbox-auditing.md)

Aquí se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** En **Actividades de buzón de Exchange,** seleccione una o ambas de las siguientes actividades:

- **Mensajes eliminados de la carpeta Elementos eliminados:** Esta actividad corresponde a la acción de auditoría del buzón **SoftDelete.** Esta actividad también se registra cuando un usuario elimina permanentemente un elemento seleccionándoselo y presionando **Mayús + Supr**. Después de que un elemento se elimina permanentemente, el usuario puede recuperarlo hasta que expire el período de retención de elementos eliminados.

- **Mensajes purgados del buzón:** Esta actividad corresponde a la acción de auditoría del buzón **HardDelete.** Esto se registra cuando un usuario purga un elemento de la carpeta Elementos recuperables. Los administradores pueden usar la herramienta de búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar y recuperar elementos purgados hasta que expire el período de retención de elementos eliminados o más tiempo si el buzón del usuario está en suspensión.

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas que sea aplicable a la investigación.

**Usuarios:** Si selecciona un usuario en este campo, la herramienta de búsqueda del registro de auditoría devuelve los registros de auditoría de los elementos de correo electrónico eliminados (SoftDeleted o HardDeleted) por el usuario que especifique. A veces, es posible que el usuario que elimina un correo electrónico no sea el propietario del buzón.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, puede filtrar los resultados de la búsqueda para mostrar los registros de auditoría de los elementos eliminados temporalmente o de los elementos eliminados permanentemente. Seleccione el registro de auditoría para mostrar **la** página desplegable Detalles y, a continuación, seleccione **Más información.** Se muestra información adicional sobre el elemento eliminado, como la línea de asunto y la ubicación del elemento cuando se eliminó, en el **campo AffectedItems.** Las capturas de pantalla siguientes muestran un ejemplo del **campo AffectedItems** de un elemento eliminado temporalmente y un elemento eliminado permanentemente.

**Ejemplo del campo AffectedItems para el elemento eliminado temporalmente**

![Registro de auditoría del elemento eliminado temporalmente](../media/softdeleteditem.png)

**Ejemplo del campo AffectedItems para el elemento eliminado permanentemente**

![Registro de auditoría del elemento de correo electrónico eliminado permanentemente](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Recuperar elementos de correo electrónico eliminados

Los usuarios pueden recuperar elementos eliminados temporalmente si el período de retención de elementos eliminados no ha expirado. En Exchange Online, el período de retención de elementos eliminados predeterminado es de 14 días, pero los administradores pueden aumentar esta configuración a un máximo de 30 días. Apunte a los usuarios al artículo [Recuperar elementos eliminados](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) o correo electrónico en Outlook en la web para obtener instrucciones sobre la recuperación de elementos eliminados.

Como se ha explicado anteriormente, los administradores pueden recuperar elementos eliminados permanentemente si el período de retención de elementos eliminados no ha expirado o si el buzón está en suspensión, en cuyo caso los elementos se mantienen hasta que expire la duración de retención. Cuando se ejecuta una búsqueda de contenido, los elementos eliminados temporalmente y eliminados permanentemente en la carpeta Elementos recuperables se devuelven en los resultados de la búsqueda si coinciden con la consulta de búsqueda. Para obtener más información acerca de cómo ejecutar búsquedas de contenido, vea [Búsqueda de contenido en Office 365.](content-search.md)

> [!TIP]
> Para buscar elementos de correo electrónico eliminados, busque todo o parte de la línea de asunto que se muestra en el campo **AffectedItems** en el registro de auditoría.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Determinar si un usuario creó una regla de bandeja de entrada

Cuando los usuarios crean una regla de bandeja de entrada para su buzón de Exchange Online, se guarda un registro de auditoría correspondiente en el registro de auditoría. Para obtener más información acerca de las reglas de bandeja de entrada, vea:

- [Usar reglas de bandeja de entrada en Outlook en la Web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Administrar mensajes de correo electrónico en Outlook mediante reglas](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Aquí se muestra cómo configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades:** En **Actividades de buzón de Exchange**, seleccione Nueva regla de bandeja de entrada **Crear/modificar/habilitar/deshabilitar regla de bandeja de entrada.**

**Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fechas que sea aplicable a la investigación.

**Usuarios:** A menos que esté investigando un usuario específico, deje este campo en blanco. Esto le ayuda a identificar nuevas reglas de bandeja de entrada configuradas por cualquier usuario.

**Archivo, carpeta o sitio:** Deje este campo en blanco.

Después de ejecutar la búsqueda, los registros de auditoría de esta actividad se muestran en los resultados de la búsqueda. Seleccione un registro de auditoría para mostrar **la** página desplegable Detalles y, a continuación, seleccione **Más información.** La información sobre la configuración de la regla de bandeja de entrada se muestra en el **campo Parámetros.** La siguiente captura de pantalla y descripciones resaltan la información sobre las reglas de la bandeja de entrada.

![Registro de auditoría de la nueva regla de bandeja de entrada](../media/NewInboxRuleRecord.png)

a. En el **campo ObjectId,** se muestra el nombre completo de la regla de bandeja de entrada. Este nombre incluye el alias del buzón del usuario (por ejemplo, SaraD) y el nombre de la regla de bandeja de entrada (por ejemplo, "Mover mensajes de administrador").

b. En el **campo Parámetros,** se muestra la condición de la regla de bandeja de entrada. En este ejemplo, la condición se especifica mediante el parámetro *From.* El valor definido para el *parámetro From* indica que la regla de bandeja de entrada actúa en el correo electrónico enviado por admin@alpinehouse.onmicrosoft.com. Para obtener una lista completa de los parámetros que se pueden usar para definir condiciones de reglas de bandeja de entrada, consulte el [artículo New-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule)

c. El *parámetro MoveToFolder* especifica la acción de la regla de bandeja de entrada. En este ejemplo, los mensajes recibidos admin@alpinehouse.onmicrosoft.com se mueven a la carpeta denominada *AdminSearch*. Vea también el [artículo New-InboxRule para](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule) obtener una lista completa de parámetros que se pueden usar para definir la acción de una regla de bandeja de entrada.

d. El **campo UserId** indica el usuario que creó la regla de bandeja de entrada especificada en el **campo ObjectId.** Este usuario también se muestra en la columna **Usuario** de la página de resultados de búsqueda.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Investigar por qué un usuario externo a la organización ha realizado un inicio de sesión correcto

Al revisar los registros de auditoría en el registro de auditoría, es posible que vea registros que indican que Azure Active Directory autenticó a un usuario externo e inició sesión correctamente en su organización. Por ejemplo, un administrador de contoso.onmicrosoft.com puede ver un registro de auditoría que muestra que un usuario de una organización diferente (por ejemplo, fabrikam.onmicrosoft.com) ha iniciado sesión correctamente en contoso.onmicrosoft.com. De forma similar, es posible que vea registros de auditoría que indiquen que los usuarios con una cuenta de Microsoft (MSA), como un Outlook.com o Live.com, iniciaron sesión correctamente en su organización. En estas situaciones, la actividad auditada es **Usuario conectado.** 

Este comportamiento es una característica del diseño de la aplicación. Azure Active Directory (Azure AD), el  servicio de directorio, permite algo llamado autenticación de paso a través cuando un usuario externo intenta obtener acceso a un sitio de SharePoint o a una ubicación de OneDrive en su organización. Cuando el usuario externo intenta hacerlo, se le pide que escriba sus credenciales. Azure AD usa las credenciales para autenticar al usuario, lo que significa que solo Azure AD comprueba que el usuario es quien dice ser. La indicación del inicio de sesión correcto en el registro de auditoría es el resultado de la autenticación de Azure AD del usuario. El inicio de sesión correcto no significa que el usuario haya podido obtener acceso a ningún recurso o realizar otras acciones en la organización. Solo indica que Azure AD autenticó al usuario. Para que un usuario de paso a través tenga acceso a los recursos de SharePoint o OneDrive, un usuario de su organización tendría que compartir explícitamente un recurso con el usuario externo enviándole una invitación para compartir o un vínculo para compartir anónimo. 

> [!NOTE]
> Azure AD solo permite la autenticación de paso a través para aplicaciones de *terceros,* como SharePoint Online y OneDrive para la Empresa. No está permitido para otras aplicaciones de terceros.

Este es un ejemplo y descripciones de propiedades  relevantes en un registro de auditoría para un usuario registrado en el evento que es el resultado de la autenticación de paso a través. Seleccione el registro de auditoría para mostrar **la** página desplegable Detalles y, a continuación, seleccione **Más información.**

![Ejemplo de registro de auditoría para la autenticación correcta de paso a través](../media/PassThroughAuth1.png)

   a. Este campo indica que el usuario que intentó obtener acceso a un recurso de la organización no se encontró en Azure AD de la organización.

   b. Este campo muestra el UPN del usuario externo que intentó obtener acceso a un recurso de la organización. Este identificador de usuario también se identifica en las **propiedades User** y **UserId** en el registro de auditoría.

   c. La **propiedad ApplicationId** identifica la aplicación que desencadenó la solicitud de inicio de sesión. El valor de 000000003-0000-0ff1-ce00-000000000000 mostrado en la propiedad ApplicationId de este registro de auditoría indica SharePoint Online. OneDrive para la Empresa también tiene el mismo ApplicationId.

   d. Esto indica que la autenticación de paso a través se ha realizado correctamente. En otras palabras, Azure AD autenticó correctamente al usuario. 

   e. El **valor RecordType** de **15** indica que la actividad auditada (UserLoggedIn) es un evento de inicio de sesión del Servicio de token seguro (STS) en Azure AD.

Para obtener más información sobre las otras propiedades mostradas en un registro de auditoría UserLoggedIn, vea la información de esquema relacionada con Azure AD en el esquema de la API de actividad de administración de [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema)

Estos son dos escenarios de ejemplo que darían como resultado un usuario **que** inició sesión correctamente en la actividad de auditoría debido a la autenticación de paso a través: 

  - Un usuario con una cuenta de Microsoft (como SaraD@outlook.com) ha intentado obtener acceso a un documento en una cuenta de OneDrive para la Empresa en fourthcoffee.onmicrosoft.com y no hay una cuenta de usuario de invitado correspondiente para SaraD@outlook.com en fourthcoffee.onmicrosoft.com.

  - Un usuario con una cuenta de trabajo o escuela en una organización (como pilarp@fabrikam.onmicrosoft.com) ha intentado tener acceso a un sitio de SharePoint en contoso.onmicrosoft.com y no hay una cuenta de usuario de invitado correspondiente para pilarp@fabrikam.com en contoso.onmicrosoft.com.

### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Sugerencias para investigar inicios de sesión correctos resultantes de la autenticación de paso a través

- Busque en el registro de auditoría las actividades realizadas por el usuario externo identificado en el **registro de** auditoría usuario registrado. Escriba el UPN del usuario  externo en el cuadro Usuarios y use un intervalo de fechas si es relevante para su escenario. Por ejemplo, puede crear una búsqueda con los siguientes criterios de búsqueda:

   ![Buscar todas las actividades realizadas por el usuario externo](../media/PassThroughAuth2.png)

    Además del  usuario que ha iniciado sesión en las actividades, se pueden devolver otros registros de auditoría, como los que indican que un usuario de la organización ha compartido recursos con el usuario externo y si el usuario externo ha accedido, modificado o descargado un documento que se ha compartido con ellos.

- Busque actividades de uso compartido de SharePoint que indiquen que un archivo se compartió con el usuario externo identificado por un usuario registrado **en el registro** de auditoría. Para obtener más información, consulte [Usar la auditoría de uso compartido en el registro de auditoría](use-sharing-auditing.md).

- Exporte los resultados de búsqueda del registro de auditoría que contienen registros relevantes para la investigación, de modo que pueda usar Excel para buscar otras actividades relacionadas con el usuario externo. Para obtener más información, vea [Exportar, configurar y ver registros de registro de auditoría.](export-view-audit-log-records.md)

## <a name="search-for-mailbox-activities-performed-by-users-with-non-e5-licenses"></a>Buscar actividades de buzón realizadas por usuarios con licencias que no son E5

Incluso [](enable-mailbox-auditing.md) cuando la auditoría de buzones está activada de forma predeterminada para su organización, es posible que observe que los eventos de auditoría de buzones de algunos usuarios no se encuentran en las búsquedas del registro de auditoría mediante el Centro de cumplimiento, el cmdlet **Search-UnifiedAuditLog** o la API de actividad de administración de Office 365. El motivo de esto es que los eventos de auditoría de buzones de correo se devolverán solo para los usuarios con licencias E5 cuando uno de los métodos anteriores busque en el registro de auditoría unificado.

Para recuperar registros de registro de auditoría de buzones de correo para usuarios que no son E5, puede realizar una de las siguientes soluciones alternativas:

- Habilite manualmente la auditoría de buzones en buzones individuales (ejecute el `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` comando en Exchange Online PowerShell). Después de hacerlo, busque actividades de auditoría de buzones mediante el Centro de cumplimiento, el cmdlet **Search-UnifiedAuditLog** o la API de actividad de administración de Office 365.
  
  > [!NOTE]
  > Si la auditoría de buzones ya parece estar habilitada en el buzón, pero las búsquedas no devuelven resultados, cambie el valor del parámetro _AuditEnabled_ a y vuelva a `$false` `$true` .
  
- Use los cmdlets siguientes en Exchange Online PowerShell:

  - [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) para buscar usuarios específicos en el registro de auditoría de buzones.

  - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) para buscar en el registro de auditoría de buzones usuarios específicos y para que los resultados se envíen por correo electrónico a los destinatarios especificados.

## <a name="search-for-mailbox-activities-performed-in-a-specific-mailbox-including-shared-mailboxes"></a>Buscar actividades de buzón realizadas en un buzón específico (incluidos los buzones compartidos)

Al usar  la lista desplegable Usuarios en la herramienta de búsqueda de registros de auditoría del Centro de cumplimiento o el comando **Search-UnifiedAuditLog -UserIds** en Exchange Online PowerShell, puede buscar actividades realizadas por un usuario específico. Para las actividades de auditoría de buzones de correo, este tipo de búsqueda buscará las actividades realizadas por el usuario especificado. No garantiza que todas las actividades realizadas en el mismo buzón se devuelvan en los resultados de la búsqueda. Por ejemplo, una búsqueda de registro de auditoría no devolverá registros de auditoría de las actividades realizadas por un usuario delegado porque la búsqueda de actividades de buzón realizadas por un usuario específico no devolverá las actividades realizadas por un usuario delegado al que se le han asignado permisos para acceder al buzón de otro usuario. (Un usuario delegado es alguien al que se le ha asignado el permiso de buzón SendAs, SendOnBehalf o FullAccess en el buzón de otro usuario).

Además, el  uso de la lista desplegable De usuarios en la herramienta de búsqueda de registros de auditoría o **search-UnifiedAuditLog -UserIds** no devolverá resultados para las actividades realizadas en un buzón compartido.

Para buscar las actividades realizadas en un buzón específico o para buscar actividades realizadas en un buzón compartido, use la siguiente sintaxis al ejecutar el cmdlet **Search-UnifiedAuditLog:**

```powershell
Search-UnifiedAuditLog  -StartDate <date> -EndDate <date> -FreeText (Get-Mailbox <mailbox identity).ExchangeGuid
```

Por ejemplo, el siguiente comando devuelve registros de auditoría de las actividades realizadas en el buzón compartido del equipo de cumplimiento de Contoso entre agosto de 2020 y octubre de 2020:

```powershell
Search-UnifiedAuditLog  -StartDate 08/01/2020 -EndDate 10/31/2020 -FreeText (Get-Mailbox complianceteam@contoso.onmicrosoft.com).ExchangeGuid
```

Como alternativa, puede usar el cmdlet **Search-MailboxAuditLog** para buscar registros de auditoría de la actividad realizada en un buzón específico. Esto incluye la búsqueda de actividades realizadas en un buzón compartido.

En el siguiente ejemplo se devuelven los registros de registro de auditoría de buzones de correo para las actividades realizadas en el buzón compartido del equipo de cumplimiento de Contoso:

```powershell
Search-MailboxAuditLog -Identity complianceteam@contoso.onmicrosoft.com -StartDate 08/01/2020 -EndDate 10/31/2020 -ShowDetails
```

En el siguiente ejemplo se devuelven los registros de registro de auditoría de buzones de correo para las actividades realizadas en el buzón especificado por usuarios delegados:

```powershell
Search-MailboxAuditLog -Identity <mailbox identity> -StartDate <date> -EndDate <date> -LogonTypes Delegate -ShowDetails
```

También puede usar el cmdlet **New-MailboxAuditLogSearch** para buscar en el registro de auditoría un buzón específico y para que los resultados se envíen por correo electrónico a los destinatarios especificados.