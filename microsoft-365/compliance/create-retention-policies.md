---
title: Cree y configure directivas de retención para retener o eliminar automáticamente el contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Use una directiva de retención para controlar de forma eficaz el contenido que los usuarios generan con el correo electrónico, los documentos y las conversaciones. Conserve lo que desee y libérese de lo que no quiere.
ms.openlocfilehash: 2b2ce9670e9f297c89ed70e1b37c17aa59b80844
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687276"
---
# <a name="create-and-configure-retention-policies"></a>Crear y configurar directivas de retención

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use una directiva de retención con el fin de administrar los datos de su organización. Para ello, decida proactivamente si se retiene el contenido, se elimina o si primero se retiene y después se elimina.

Una directiva de retención le permite hacerlo de manera muy eficaz. Solo tiene que asignar la misma configuración de retención a nivel del contenedor al contenido de ese contenedor, que lo hereda de forma automática. Por ejemplo, todos los elementos de los sitios de SharePoint, todos los mensajes de correo electrónico de los buzones de Exchange de los usuarios, todos los mensajes de canal de los equipos que se usan con Microsoft Teams. Si no está seguro sobre si debe usar una directiva de retención o una etiqueta de retención, consulte [Directivas de retención y etiquetas de retención](retention.md#retention-policies-and-retention-labels).

Para obtener más información sobre las directivas de retención y cómo funciona la retención en Microsoft 365, vea [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md).

> [!NOTE]
> La información de esta página es para los administradores de cumplimiento normativo. Si no es administrador y quiere entender cómo se configuraron las directivas de retención para las aplicaciones que usa, póngase en contacto con el departamento de soporte técnico, el departamento de TI o el administrador. Si ve mensajes sobre directivas de retención en los chats de Teams y en los mensajes de canal, puede serle útil revisar [Mensajes de Teams sobre directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de su organización tiene permisos totales para crear y modificar directivas de retención. Si no va a iniciar sesión como administrador global, consulte [Permisos necesarios para crear y administrar directivas de retención y etiquetas de retención](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="create-and-configure-a-retention-policy"></a>Crear y configurar una directiva de retención

Aunque una directiva de retención puede admitir varios servicios identificados como "ubicaciones" en la directiva de retención, no puede crear una sola directiva de retención que incluya todas las ubicaciones compatibles:

- Correo electrónico de Exchange
- Sitio de SharePoint
- Cuentas de OneDrive
- Grupos de Microsoft 365
- Skype Empresarial
- Carpetas públicas de Exchange
- Mensajes de canal de Teams
- Chats de Teams
- Mensajes de la comunidad de Yammer
- Mensajes privados de Yammer

Cuando selecciona una de las ubicaciones de Teams o Yammer durante la creación de una directiva de retención, las demás ubicaciones quedan excluidas automáticamente. Por lo tanto, las instrucciones que debe seguir dependerán de si necesita incluir las ubicaciones de Teams o de Yammer:

- [Instrucciones para crear una directiva de retención para ubicaciones de Teams](#retention-policy-for-teams-locations)
- [Instrucciones para crear una directiva de retención para ubicaciones de Yammer](#retention-policy-for-yammer-locations)
- [Instrucciones para crear una directiva de retención para otras ubicaciones fuera de Teams y Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)

Si tiene más de una directiva de retención y, además, utiliza etiquetas de retención, consulte [Los principios de la retención o qué tiene prioridad](retention.md#the-principles-of-retention-or-what-takes-precedence) para entender qué resultado se obtiene cuando varias configuraciones de retención se aplican al mismo contenido.

### <a name="retention-policy-for-teams-locations"></a>Directiva de retención para ubicaciones de Teams

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva Directiva de retención** para iniciar el Asistente para crear directivas de retención y asignar un nombre a su nueva Directiva de retención.

3. Para la página **Elegir ubicaciones para aplicar la directiva**, seleccione una o ambas ubicaciones para Teams: **mensaje de canal de Teams** y **chats de Teams**.

   En **los mensajes de canal de Teams**, se incluyen los mensajes de los canales estándar, pero no los de [canales privados](/microsoftteams/private-channels). Actualmente, los canales privados no son compatibles con las directivas de retención.

   De forma predeterminada, [se seleccionan todos los equipos y todos los usuarios](#a-policy-that-applies-to-entire-locations), pero puede refinar esto al seleccionar la [**Elegir** y **Excluir** opciones](#a-policy-with-specific-inclusions-or-exclusions).

4. En la página del asistente **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.

   Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para conservar y eliminar contenido](#settings-for-retaining-and-deleting-content) en esta página.

5. Finalice el asistente para guardar la configuración.

Para más información sobre las directivas de retención para Teams, consulte [Directivas de retención en Microsoft Teams](/microsoftteams/retention-policies) en la documentación de Teams.

#### <a name="known-configuration-issues"></a>Problemas de configuración conocidos

- Aunque puede seleccionar la opción para iniciar el período de retención en el que se modificaron los elementos por última vez, siempre se usa el valor **Cuando se crearon los elementos**. Para los mensajes que se editan, se guarda una copia del mensaje original con la marca de tiempo original para identificar cuándo se creó este mensaje antes de editar, y el mensaje después de editar tiene una marca de tiempo más reciente.

- Al seleccionar **Elegir equipos** para la ubicación de los **mensajes del canal Teams** es posible que vea grupos de Office 365 que no son también equipos. No seleccione estos equipos

- Al seleccionar la ubicación **Elegir usuarios para los chats de Teams**, puede que vea invitados y no usuarios del buzón. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.


#### <a name="additional-retention-policy-needed-to-support-teams"></a>Directivas de retención adicionales que se necesitan para Teams

Teams es mucho más que solo chats y mensajes de canal. Si tiene equipos creados a partir de un grupo de Microsoft 365 (anteriormente "grupo de Office 365"), debe configurar una directiva de retención que incluya el grupo de Microsoft 365 mediante la ubicación de **Grupos de Microsoft 365**. La directiva de retención se aplica al contenido del buzón, del sitio y de los archivos del grupo.

Si tiene sitios de equipo que no estén conectados con un grupo de Microsoft 365, necesitará una directiva de retención que incluya las ubicaciones de los **sitios de SharePoint** o de las **cuentas de OneDrive** para conservar y eliminar archivos en Teams:

- Los archivos que se comparten en el chat se almacenan en la cuenta de OneDrive del usuario que compartió el archivo.

- Los archivos que se suben a los canales se almacenan en el sitio de SharePoint del equipo.

> [!TIP]
> Puede aplicar una directiva de retención a los archivos de un solo equipo específico cuando no está conectado a un grupo de Microsoft 365. Para ello, seleccione el sitio de SharePoint del equipo y las cuentas de OneDrive de los usuarios del mismo.

Es posible que una directiva de retención que se aplique a los grupos de Microsoft 365, los sitios de SharePoint o las cuentas de OneDrive pueda eliminar un archivo al que se hace referencia en un mensaje de canal o chat de Teams antes de que se eliminen esos mensajes. En este caso, el archivo seguirá apareciendo en el mensaje de Teams, pero cuando los usuarios lo seleccionen, obtendrán un error de "Archivo no encontrado". Este comportamiento no es específico de las directivas de retención y también podría ocurrir si un usuario elimina manualmente un archivo de SharePoint o OneDrive.

### <a name="retention-policy-for-yammer-locations"></a>Directiva de retención para ubicaciones de Yammer

> [!NOTE]
> Las directivas de retención de Yammer se implementan en versión preliminar. Si aún no ve las nuevas ubicaciones de Yammer, inténtelo de nuevo en unas semanas.
>
> Para usar esta característica, la red de Yammer debe estar en [Modo nativo](/yammer/configure-your-yammer-network/overview-native-mode), en lugar de en Modo híbrido.

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva directiva de retención** para crear una nueva directiva de retención.

3. En la página del asistente **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido. 
    
    Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para conservar y eliminar contenido](#settings-for-retaining-and-deleting-content) en esta página.
    
    No seleccione **Usar la configuración de retención avanzada**, ya que esta opción no es compatible con las ubicaciones de Yammer. 

4. Para acceder a la página **Elegir ubicaciones**, seleccione **Quiero elegir ubicaciones concretas**. A continuación, alterne entre una o ambas ubicaciones de Yammer: **Mensaje de la comunidad de Yammer** y **Mensajes privados de Yammer**.
    
    De forma predeterminada, todas las comunidades y usuarios están seleccionados, pero puede restringir los resultados al especificar qué comunidades y usuarios desea incluir o excluir.
    
    Para los mensajes privados de Yammer: 
    - Si deja la opción predeterminada en **Todos**, no se incluirá a los usuarios invitados de Azure B2B. 
    - Si selecciona **Elegir usuario**, puede aplicar una directiva de retención a los usuarios externos si ya sabe cuál es su cuenta.

5. Finalice el asistente para guardar la configuración.

Para obtener más información sobre cómo funcionan las directivas de retención de Yammer, consulte [Obtener información sobre la retención para Yammer](retention-policies-yammer.md).

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Directivas de retención adicionales que se necesitan para admitir Yammer

Yammer es más que solo mensajes de la comunidad y mensajes privados. Para conservar y eliminar los mensajes de correo electrónico de su red de Yammer, configure una directiva de retención adicional que incluya a los grupos de Microsoft 365 que se usan para Yammer, mediante la ubicación de los **Grupos de Microsoft 365**. 

Para conservar y eliminar los archivos almacenados en Yammer, necesitará una directiva de retención que incluya las ubicaciones de los **sitios de SharePoint** o de las **cuentas de OneDrive**:

- Los archivos compartidos en los mensajes privados se almacenan en la cuenta de OneDrive del usuario que compartió el archivo. 

- Los archivos que se cargan en las comunidades se almacenan en el sitio de SharePoint de la comunidad de Yammer.

Es posible que una directiva de retención que se aplique a los sitios de SharePoint o a las cuentas de OneDrive pueda eliminar un archivo al que se haga referencia en un mensaje de Yammer antes de que dicho mensaje sean eliminado. En este caso, el archivo seguirá mostrándose en el mensaje de Yammer, pero cuando los usuarios lo seleccionen, obtendrán el error "Archivo no encontrado". Este comportamiento no es específico para las directivas de retención y también podría ocurrir si un usuario elimina manualmente un archivo de SharePoint o OneDrive.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Directivas de retención para otras ubicaciones fuera de Teams y Yammer

Use las siguientes instrucciones para crear directivas de retención que apliquen a cualquiera de estos servicios:

- Correo electrónico y carpetas públicas de Exchange
- Sitios de SharePoint
- Cuentas de OneDrive
- Grupos de Microsoft 365
- Skype Empresarial

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva Directiva de retención** para iniciar el Asistente para crear directivas de retención y asignar un nombre a su nueva Directiva de retención.

3. En la página **Elegir ubicaciones**, activar o desactivar cualquiera de las ubicaciones, excepto las ubicaciones de los Teams. Para cada ubicación, puede dejarla de forma predeterminada [aplicar la directiva a toda la ubicación](#a-policy-that-applies-to-entire-locations), o [especificar lo que se incluye y excluye](#a-policy-with-specific-inclusions-or-exclusions).

    Información específica de las ubicaciones:
    - [Correo electrónico de Exchange y carpetas públicas de Exchange](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [Sitios de SharePoint y cuentas de OneDrive](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Grupos de Microsoft 365](#configuration-information-for-microsoft-365-groups)
    - [Skype Empresarial](#configuration-information-for-skype-for-business)

4. En la página del asistente **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.

    Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para conservar y eliminar contenido](#settings-for-retaining-and-deleting-content) en esta página.

5. Finalice el asistente para guardar la configuración.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Información de configuración para el correo electrónico de Exchange y las carpetas públicas de Exchange

La ubicación del **correo electrónico de Exchange** admite la retención para el correo electrónico, el calendario y otros elementos del buzón de correo del usuario al aplicar la configuración de retención en el nivel de buzón.

Para obtener información detallada sobre los elementos que se incluyen y excluyen al configurar las opciones de retención para Exchange, consulte [¿Qué se incluye para la retención y eliminación?](retention-policies-exchange.md#whats-included-for-retention-and-deletion)

Tenga en cuenta que aunque un grupo de Microsoft 365 tenga un buzón de Exchange, una directiva de retención que incluya toda la ubicación de **correo electrónico de Exchange** no incluirá el contenido de los buzones de correo del grupo de Microsoft 365. Para conservar el contenido de estos buzones, seleccione la ubicación de **Grupos de Microsoft 365**.

La ubicación de las **carpetas públicas de Exchange** aplica la configuración de retención a todas las carpetas públicas y no se puede aplicar en el nivel de carpeta o de buzón de correo.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Información de configuración para los sitios de SharePoint y las cuentas de OneDrive

Cuando elige la ubicación de los **sitios de SharePoint**, la directiva de retención puede conservar y eliminar documentos en los sitios de comunicación de SharePoint, en los sitios de equipo no conectados por grupos de Microsoft 365 y en los sitios clásicos. Los sitios de equipos conectados por grupos de Microsoft 365 no son compatibles con esta opción. En su lugar, use la ubicación de **Grupos de Microsoft 365** que corresponda con el contenido del buzón, el sitio y los archivos del grupo.

Si bien la directiva de retención se aplica en el nivel de sitio, la configuración de retención solo se aplica a los documentos. Para obtener información detallada sobre lo que se incluye y excluye al configurar las opciones de retención para SharePoint y OneDrive, consulte [¿Qué se incluye para la retención y eliminación?](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion) 

Cuando especifica sus ubicaciones para los sitios de SharePoint o las cuentas de OneDrive, no necesita permisos para acceder a los sitios y no se lleva a cabo ninguna validación en el momento en el que especifica la dirección URL en la página **Editar ubicaciones**. Sin embargo, los sitios de SharePoint que especifique se deben indexar y al final del asistente se comprueba que existan. Si se produce un error en esta comprobación, verá un mensaje que indica que no se pudo realizar la validación de la dirección URL que ha indicado y el asistente no creará la directiva de retención hasta que se supere la comprobación de validación.  Si ve este mensaje, vuelva al asistente para cambiar la dirección URL o eliminar el sitio de la directiva de retención.

Para especificar cuentas individuales de OneDrive que quiera incluir o excluir, la dirección URL tiene el siguiente formato: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

Por ejemplo, para un usuario en el espacio empresarial de Contoso con un nombre de usuario "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

Para comprobar la sintaxis de su espacio empresarial e identificar las direcciones URL de los usuarios, consulte [Obtener una lista de todas las URL de OneDrive de usuario en su organización](/onedrive/list-onedrive-urls).

### <a name="configuration-information-for-microsoft-365-groups"></a>Información de configuración para los Grupos de Microsoft 365

Para conservar o eliminar el contenido de un grupo de Microsoft 365 (anteriormente llamado "grupo de Office 365"), utilice la ubicación de los **Grupos de Microsoft 365**. Aunque un grupo Microsoft 365 tiene un buzón de Exchange, una directiva de retención que incluya toda la ubicación de **correo electrónico de Exchange** no incluirá el contenido de los buzones del grupo Microsoft 365. Aunque la ubicación del **correo electrónico de Exchange** le permite inicialmente especificar un buzón de grupo para incluirlo o excluirlo, cuando intente guardar la directiva de retención, verá un error que indique que "RemoteGroupMailbox" no es una selección válida para la ubicación de Exchange.

De manera predeterminada, una directiva de retención aplicada a un grupo de Microsoft 365 incluye el buzón de grupo y el sitio de equipos de SharePoint. Los archivos almacenados en el sitio de equipos de SharePoint se tratan en esta ubicación, pero no los mensajes de chats ni canales de Teams que tienen sus propias ubicaciones de directivas de retención.

Para cambiar el valor predeterminado porque quiere que la directiva de retención se aplique solo a los buzones de Microsoft 365 o solo a los sitios de equipos de SharePoint conectados, use el cmdlet de PowerShell [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) con el parámetro *Applications* con uno de los siguientes valores:

- `Group:Exchange` solo para los buzones de Microsoft 365 conectados al grupo.
- `Group:SharePoint` solo para sitios de SharePoint conectados al grupo.

Para volver al valor predeterminado del buzón y del sitio de SharePoint para los grupos de Microsoft 365 seleccionados, especifique `Group:Exchange,SharePoint`.

### <a name="configuration-information-for-skype-for-business"></a>Información de configuración de Skype Empresarial

A diferencia del correo electrónico de Exchange, no puede activar el estado de ubicación de Skype para incluir automáticamente a todos los usuarios, pero cuando active esta ubicación, debe elegir manualmente los usuarios cuyas conversaciones desea conservar:

![Elegir la ubicación de Skype para las directivas de retención](../media/skype-location-retention-policies.png)

Cuando seleccione **Elegir usuario**, puede incluir rápidamente a todos los usuarios seleccionando el cuadro **Seleccionar todo**. Sin embargo, es importante entender que cada usuario tiene que contar con una inclusión específica en la directiva. Por lo tanto, si incluye 1 000 usuarios seleccionando la casilla **Seleccionar todo**, será lo mismo que si selecciona manualmente 1 000 usuarios para incluir, que es el máximo admitido para Skype Empresarial.

Tenga en cuenta que **Historial de conversaciones**, una carpeta en Outlook, es una característica que no tiene nada que ver con el archivado de Skype. El **Historial de conversaciones** puede estar desactivado por el usuario final, pero el archivado para Skype se realiza almacenando una copia de las conversaciones de Skype en una carpeta oculta que está disponible para eDiscovery pero es inaccesible para el usuario.

## <a name="settings-for-retaining-and-deleting-content"></a>Configuración para retener y borrar el contenido

Al elegir las configuraciones para retener y eliminar contenido en su directiva de retención, ésta tendrá una de las siguientes configuraciones durante un período de tiempo determinado:

- Sólo para retención

    Para esta configuración, elija **Conservar elementos durante un período específico** y **Al final del período de retención: no haga nada**. O bien, seleccione **Retener elementos para siempre**.

- Retener y luego eliminar

    Para esta configuración, elija **conservar elementos durante un período específico** y **al final del período de retención: eliminar elementos automáticamente**.

- Solo eliminar

    Para esta configuración, elija **Solo eliminar elementos cuando alcancen una antigüedad determinada**.

### <a name="retaining-content-for-a-specific-period-of-time"></a>Retención del contenido durante un período de tiempo determinado

Cuando se configura una directiva de retención, usted elige si desea retener el contenido de forma indefinida o durante un número determinado de días, meses o años. O como alternativa, conserve siempre los elementos.

Cuando configure una directiva de retención, puede elegir retener contenido de forma indefinida o durante un número específico de días, meses o años. El período de retención se calcula desde la antigüedad del contenido, no desde cuando se aplica la directiva de retención.

Para iniciar el período de retención, también puede elegir cuándo se creó el contenido o, solo en el caso de los archivos y los grupos de SharePoint, OneDrive y Microsoft 365, cuándo se modificó el contenido por última vez.

Ejemplos:

- SharePoint: si desea conservar el contenido de una colección de sitios durante siete años después de que este contenido se modificó por última vez, y un documento de esa colección de sitios no se ha modificado en seis años, el documento se conservará solo durante otro año si no se modifica. Si el documento se edita de nuevo, la edad del documento se calcula a partir de la nueva fecha de la última modificación, y se conservará durante otros siete años.

- Exchange: si desea conservar los elementos en un buzón de correo durante siete años y un mensaje se ha enviado hace seis años, el mensaje se conservará durante solo un año. En el caso de los elementos de Exchange, la edad se basa en la fecha de recepción del correo electrónico entrante o en la fecha de envío del correo electrónico saliente. La conservación de los elementos en función de la última modificación se aplica solo al contenido del sitio en OneDrive y SharePoint.

Al final del período de retención, usted elige si desea que el contenido se elimine de forma permanente:

![Página de configuración de retenciones](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>Eliminar el contenido que supera una antigüedad determinada

Una directiva de retención puede retener y, a continuación, eliminar elementos o eliminar elementos antiguos sin retenerlos.

En ambos casos, si su directiva de retención elimina elementos, es importante entender que el período de tiempo especificado para una directiva de retención se calcula a partir del momento en que se ha creado o modificado el elemento, y no a partir del momento en que fue asignado a la directiva.

Por lo tanto, antes de asignar una directiva de retención por primera vez, especialmente cuando esa directiva elimina elementos, en primer lugar, tenga en cuenta la antigüedad del contenido existente y cómo puede afectar la directiva al contenido. También es posible que desee comunicar la nueva directiva a sus usuarios antes de asignarla, para darles tiempo a evaluar el posible impacto.

### <a name="a-policy-that-applies-to-entire-locations"></a>Una directiva que se aplica a todas las ubicaciones

Al elegir las ubicaciones, con la excepción de Skype Empresarial, la configuración predeterminada es **Todo** cuando el estado de la ubicación está **Activado**.

Cuando una directiva de retención se aplica a cualquier combinación de todas las ubicaciones, no hay ningún límite en el número de destinatarios, sitios, cuentas, grupos, etc. que la directiva pueda incluir.

Por ejemplo, si la directiva incluye todo el correo electrónico de Exchange y todos los sitios de SharePoint, se incluirán todos los sitios y destinatarios, sea cual sea la cantidad. Y para Exchange, todos los buzones que se creen una vez que la directiva se haya aplicado, heredarán automáticamente la directiva.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Una directiva con inclusiones o exclusiones específicas

Deben tenerse en cuenta ciertos límites por directiva si usa la configuración opcional para definir el ámbito de la configuración de retención para usuarios específicos, grupos específicos de Microsoft 365 o determinados sitios. Para obtener más información, vea [Límites de directivas de retención y directivas de etiqueta de retención](retention-limits.md). 

Para usar la configuración opcional para definir el ámbito de la configuración de retención, asegúrese de que el **Estado** de esa ubicación esté **Activado** y, a continuación, use los vínculos para incluir o excluir determinados usuarios, grupos de Microsoft 365 o sitios.

> [!WARNING]
> Si configura inclusiones y, a continuación, quita la última, la configuración de su ubicación se revertirá a **Todos**.  Asegúrese de que esta es la configuración que desea antes de guardar la directiva.
>
> Por ejemplo, si especifica un sitio de SharePoint para incluirlo en su directiva de retención que está configurada para eliminar datos y, a continuación, quita el único sitio, todos los sitios de SharePoint quedarán sujetos de forma predeterminada a la directiva de retención que elimina de forma permanente los datos. Lo mismo se aplica a destinatarios de Exchange, cuentas de OneDrive, usuarios de chat de Teams, etc.
>
> En este escenario, deshabilite la ubicación si no quiere que la opción **Todos** de la ubicación esté sujeta a la directiva de retención. También puede especificar exclusiones para que estén exentas de la directiva.

## <a name="updating-retention-policies"></a>Actualización de las directivas de retención

Después de crear y guardar la directiva de retención, no se pueden cambiar algunas opciones de configuración, entre las que se incluyen:
- El nombre de la directiva de retención y la configuración de retención, excepto el período de retención, y cuándo iniciar el período de retención.

Si edita una directiva de retención y el contenido ya está sujeto a la configuración original de su directiva de retención, la configuración actualizada se aplicará automáticamente a estos elementos, además de los elementos identificados recientemente.

Por lo general, esta actualización es bastante rápida, pero puede tardar varios días. Cuando la replicación de la directiva en todas las ubicaciones de Microsoft 365 se haya completado, verá que el estado de la directiva de retención en el centro de cumplimiento de Microsoft 365 cambia de **Activado (Pendiente)** a **Activado (Éxito)**.

## <a name="locking-the-policy-to-prevent-changes"></a>Bloquear la directiva para impedir que se realicen cambios

Si necesita asegurarse de que nadie pueda desactivar, eliminar, o hacer que la directiva sea menos restrictiva, consulte [Usar el Bloqueo de conservación para restringir los cambios en directivas de retención y directivas de etiquetas de retención](retention-preservation-lock.md).
