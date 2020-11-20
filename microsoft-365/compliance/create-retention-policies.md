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
description: Use una directiva de retención para controlar de forma eficaz el contenido que los usuarios generan con el correo electrónico, los documentos y las conversaciones. Conserve lo que quiera y elimine lo que no.
ms.openlocfilehash: 83f438b6a32ad56f1f239858d2f3fad61875c460
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357345"
---
# <a name="create-and-configure-retention-policies"></a>Crear y configurar directivas de retención

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Utilice una directiva de retención para decidir de forma pro activa si desea retener el contenido, eliminarlo o ambas cosas, retener y luego eliminar el contenido.

Una directiva de retención le permite hacer esto de manera muy eficaz al asignar la misma configuración de retención para el contenido por ubicación, en un nivel de sitio o de buzón. Si no está seguro de si debe usar una directiva de retención o una etiqueta de retención, consulte [Directivas de retención y etiquetas de retención](retention.md#retention-policies-and-retention-labels).

Para obtener más información sobre las directivas de retención y cómo funciona la retención, vea [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md).

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de su organización tiene permisos totales para crear y editar directivas de retención. Si no va a iniciar sesión como administrador global, consulte [Permisos necesarios para crear y administrar las directivas de retención y las etiquetas de retención](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="create-and-configure-a-retention-policy"></a>Crear y configurar una directiva de retención

Si bien una directiva de retención es compatible con varias ubicaciones, no se puede crear una única directiva de retención que incluya todas las ubicaciones compatibles:

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

Si selecciona las ubicaciones de Teams o de Yammer al crear una directiva de retención, las demás ubicaciones se excluirán automáticamente. Por lo tanto, las instrucciones que debe seguir dependen de si necesita incluir las ubicaciones de Teams o de Yammer:

- [Instrucciones para crear una directiva de retención para ubicaciones de Teams](#retention-policy-for-teams-locations)
- [Instrucciones para crear una directiva de retención para ubicaciones de Yammer](#retention-policy-for-yammer-locations)
- [Instrucciones para crear una directiva de retención para otras ubicaciones fuera de Teams y Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)

Si tiene más de una directiva de retención y, además, utiliza etiquetas de retención, consulte [Los principios de la retención o qué tiene prioridad](retention.md#the-principles-of-retention-or-what-takes-precedence) para entender qué resultado se obtiene cuando varias configuraciones de retención se aplican al mismo contenido.

### <a name="retention-policy-for-teams-locations"></a>Directiva de retención para ubicaciones de Teams

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva Directiva de retención** para iniciar el Asistente para crear directivas de retención y asignar un nombre a su nueva Directiva de retención.

3. Para la página **Elegir ubicaciones para aplicar la directiva**, seleccione una o ambas ubicaciones para Teams: **mensaje de canal de Teams** y **chats de Teams**.

   Para los **mensajes del canal Teams**, se incluyen mensajes de canales estándar, pero no de [canales privados](https://docs.microsoft.com/microsoftteams/private-channels). En estos momentos, los canales privados no son compatibles con las directivas de retención.

   De forma predeterminada, [se seleccionan todos los equipos y todos los usuarios](#a-policy-that-applies-to-entire-locations), pero puede refinar esto al seleccionar la [**Elegir** y **Excluir** opciones](#a-policy-with-specific-inclusions-or-exclusions).

4. En la página del asistente **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.

   Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para retener y eliminar contenido](#settings-for-retaining-and-deleting-content) en esta página.

5. Finalice el asistente para guardar la configuración.

Para más información sobre las directivas de retención para Teams, consulte [Directivas de retención en Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) en la documentación de Teams.

#### <a name="additional-retention-policy-needed-to-support-teams"></a>Directivas de retención adicionales que se necesitan para Teams

Teams ofrece elementos que van más allá de los chats y los mensajes de canal. Si tiene equipos creados a partir de un grupo de Microsoft 365 (anteriormente "grupo de Office 365"), debe configurar una directiva de retención que incluya el grupo de Microsoft 365 mediante la ubicación de **Grupos de Microsoft 365**. Esta directiva de retención se aplica al contenido en el buzón de correo, sitio y archivos del grupo.

Si tiene sitios de equipo que no estén conectados con un grupo de Microsoft 365, necesitará una directiva de retención que incluya las ubicaciones de los **sitios de SharePoint** o de las **cuentas de OneDrive** para conservar y eliminar archivos en Teams:

- Los archivos que se comparten en el chat se almacenan en la cuenta de OneDrive del usuario que compartió el archivo.

- Los archivos que se suben a los canales se almacenan en el sitio de SharePoint del equipo.

> [!TIP]
> Puede aplicar una directiva de retención a los archivos de un solo equipo específico cuando no está conectado a un grupo de Microsoft 365. Para ello, seleccione el sitio de SharePoint del equipo y las cuentas de OneDrive de los usuarios del mismo.

Puede que una directiva de retención aplicada a los grupos de Microsoft 365, a los sitios de SharePoint o a las cuentas de OneDrive elimine un archivo al que se haga referencia en un chat o en un mensaje de canal de Teams antes de que se eliminen dichos mensajes. Si esto sucede, el archivo se seguirá mostrando en el mensaje de Teams, pero, cuando los usuarios seleccionen el archivo, recibirán un error de "No se encuentra el archivo". Este comportamiento no es específico de las directivas de retención y también puede darse si un usuario elimina manualmente un archivo de SharePoint o OneDrive.

### <a name="retention-policy-for-yammer-locations"></a>Directiva de retención para ubicaciones de Yammer

> [!NOTE]
> Las directivas de retención de Yammer se están implementando en versión preliminar. Si aún no ve las nuevas ubicaciones de Yammer, inténtelo de nuevo en unos días.
>
> Para usar esta característica, la red de Yammer debe estar en [Modo nativo](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode), en lugar de en Modo híbrido.

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva directiva de retención** para crear una nueva directiva de retención.

3. En la página del asistente **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido. 
    
    Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para retener y eliminar contenido](#settings-for-retaining-and-deleting-content) en esta página.
    
    No seleccione **Usar la configuración de retención avanzada**, ya que esta opción no es compatible con las ubicaciones de Yammer. 

4. Para la página **Elegir ubicaciones**, seleccione **Permitirme elegir ubicaciones específicas**. A continuación, alterne entre una o ambas ubicaciones de Yammer: **Mensaje de la comunidad de Yammer** y **Mensajes privados de Yammer**.
    
    De forma predeterminada, todas las comunidades y usuarios están seleccionados, pero puede restringir los resultados al especificar qué comunidades y usuarios desea incluir o excluir.
    
    Para los mensajes privados de Yammer: 
    - Si deja la opción predeterminada en **Todos**, no se incluirá a los usuarios invitados de Azure B2B. 
    - Si selecciona **Elegir usuario**, puede aplicar una directiva de retención a los usuarios externos si ya sabe cuál es su cuenta.

5. Finalice el asistente para guardar la configuración.

Para obtener más información sobre cómo funcionan las directivas de retención de Yammer, consulte [Obtener información sobre la retención para Yammer](retention-policies-yammer.md).

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Directivas de retención adicionales que se necesitan para admitir Yammer

Yammer ofrece elementos que van más allá de los mensajes de comunidad y los mensajes privados. Para conservar y eliminar los mensajes de correo electrónico de su red de Yammer, configure una directiva de retención adicional que incluya a los grupos de Microsoft 365 que se usan para Yammer, mediante la ubicación de los **Grupos de Microsoft 365**. 

Para conservar y eliminar los archivos almacenados en Yammer, necesitará una directiva de retención que incluya las ubicaciones de los **sitios de SharePoint** o de las **cuentas de OneDrive**:

- Los archivos compartidos en los mensajes privados se almacenan en la cuenta de OneDrive del usuario que compartió el archivo. 

- Los archivos que se cargan en las comunidades se almacenan en el sitio de SharePoint de la comunidad de Yammer.

Puede que una directiva de retención aplicada a los sitios de SharePoint o a las cuentas de OneDrive elimine un archivo al que se haga referencia en un mensaje de Yammer antes de que se eliminen dichos mensajes. Si esto sucede, el archivo se seguirá mostrando en el mensaje de Yammer, pero, cuando los usuarios seleccionen el archivo, recibirán un error de "No se encuentra el archivo". Este comportamiento no es específico de las directivas de retención y también puede darse si un usuario elimina manualmente un archivo de SharePoint o OneDrive.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Directivas de retención para otras ubicaciones fuera de Teams y Yammer

Use las siguientes instrucciones para crear directivas de retención que apliquen a cualquiera de estos servicios:

- Correo electrónico y carpetas públicas de Exchange
- Sitios de SharePoint
- Cuentas de OneDrive
- Grupos de Microsoft 365
- Skype Empresarial

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), seleccione **Directivas de** > **retención**.

2. Seleccione **Nueva directiva de retención** para iniciar el Asistente para crear directivas de retención y asignar un nombre a su nueva directiva de retención.

3. Para la página **Elegir ubicaciones**, alterne entre cualquier ubicación, excepto las de Teams. Para cada ubicación, puede dejarla de forma predeterminada para [aplicar la directiva a toda la ubicación](#a-policy-that-applies-to-entire-locations) o [especificar cuáles incluir y cuáles no](#a-policy-with-specific-inclusions-or-exclusions).

    Información específica de las ubicaciones:
    - [Correo electrónico de Exchange y carpetas públicas de Exchange](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [Sitios de SharePoint y cuentas de OneDrive](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Grupos de Microsoft 365](#configuration-information-for-microsoft-365-groups)
    - [Skype Empresarial](#configuration-information-for-skype-for-business)

4. En la página del asistente **Decidir si quiere conservar el contenido, eliminarlo, o ambos**, especifique las opciones de configuración para conservar y eliminar el contenido.

    Puede crear una directiva de retención que sólo retenga el contenido sin eliminarlo, que retenga y luego elimine después de un período de tiempo determinado, o que sólo elimine el contenido después de un período de tiempo determinado. Para más información, consulte [Configuración para retener y eliminar contenido](#settings-for-retaining-and-deleting-content) en esta página.

5. Finalice el asistente para guardar la configuración.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Información de configuración para el correo electrónico de Exchange y las carpetas públicas de Exchange

La ubicación del **correo electrónico de Exchange** admite la retención para el correo electrónico, el calendario y otros elementos del buzón de correo del usuario al aplicar la configuración de retención en el nivel de buzón de correo.

Para obtener información detallada sobre los elementos que se incluyen y excluyen al configurar las opciones de retención para Exchange, consulte [¿Qué se incluye para la retención y eliminación?](retention-policies-exchange.md#whats-included-for-retention-and-deletion)

Tenga en cuenta que, incluso si un grupo de Microsoft 365 tiene un buzón de Exchange, una directiva de retención que incluya la ubicación completa del **correo electrónico de Exchange** no incluirá contenido en buzones de grupo de Microsoft 365. Para retener contenido en estos buzones, seleccione la ubicación de **Grupos de Microsoft 365**.

La ubicación de las **carpetas públicas de Exchange** aplica la configuración de retención a todas las carpetas públicas y no se puede aplicar en el nivel de carpeta o de buzón de correo.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Información de configuración para los sitios de SharePoint y las cuentas de OneDrive

Cuando elige la ubicación de los **sitios de SharePoint**, la directiva de retención puede conservar y eliminar documentos en los sitios de comunicación de SharePoint, en los sitios de equipo que no estén conectados por grupos de Microsoft 365 y en sitios clásicos. Los sitios de equipo conectados por grupos de Microsoft 365 no son compatibles con esta opción. En su lugar, utilizan la ubicación de **Grupos de Microsoft 365** que se aplica al contenido del buzón, del sitio y de los archivos del grupo.

Si bien la directiva de retención se aplica a nivel del sitio, solo se aplican configuraciones de retención a los documentos. Para obtener información detallada sobre lo que se incluye y excluye al configurar las opciones de retención para SharePoint y OneDrive, consulte [¿Qué se incluye para la retención y eliminación?](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion) 

Cuando especifica las ubicaciones para los sitios de SharePoint o cuentas de OneDrive, no necesita permisos para obtener acceso a los sitios y no se lleva a cabo ninguna validación en el momento de especificcar la dirección URL en la página **Editar ubicaciones**. Sin embargo, al final del asistente se comprueba que existan los sitios de SharePoint que especifica. Si se produce un error en esta comprobación, verá un mensaje que indica que no se pudo realizar la validación de la dirección URL que ha indicado, y el asistente no creará la directiva de retención hasta que la comprobación para la validación sea correcta. Si ve este mensaje, vuelva al asistente para cambiar la dirección URL o quitar el sitio de la directiva de retención.

Para especificar cuentas individuales de OneDrive que quiera incluir o excluir, la dirección URL tiene el siguiente formato: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

Por ejemplo, para un usuario en el espacio empresarial de Contoso con un nombre de usuario "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

Para comprobar la sintaxis de su espacio empresarial e identificar las direcciones URL de los usuarios, consulte [Obtener una lista de todas las URL de OneDrive de usuario en su organización](https://docs.microsoft.com/onedrive/list-onedrive-urls).

### <a name="configuration-information-for-microsoft-365-groups"></a>Información de configuración para los Grupos de Microsoft 365

Para conservar o eliminar el contenido de un grupo de Microsoft 365 (anteriormente denominado grupo de Office 365), use la ubicación de **Grupos de Microsoft 365**. Si bien un grupo de Microsoft 365 tiene un buzón de Exchange, una directiva de retención que incluya toda la ubicación del **Correo electrónico de Exchange** no incluirá contenido en los buzones de grupo de Microsoft 365. Además, aunque la **ubicación de correo electrónico de Exchange** permite inicialmente especificar un buzón de grupo que quiere incluir o excluir, al intentar guardar la directiva de retención, recibirá un error que indica que "RemoteGroupMailbox" no es una selección válida para la ubicación de Exchange.

Una directiva de retención aplicada a un grupo de Microsoft 365 incluye el buzón del grupo y el sitio de los equipos de SharePoint. Los archivos guardados en el sitios de equipos de SharePoint están cubiertos por esta ubicación, pero no lo están los chats de Teams o los mensajes de canal de Teams, que cuentan con sus propias ubicaciones de directiva de retención.

### <a name="configuration-information-for-skype-for-business"></a>Información de configuración de Skype Empresarial

A diferencia del correo electrónico de Exchange, no puede activar el estado de ubicación de Skype para incluir automáticamente a todos los usuarios, pero cuando active esta ubicación, debe elegir manualmente los usuarios cuyas conversaciones desea conservar:

![Elegir la ubicación de Skype para las directivas de retención](../media/skype-location-retention-policies.png)

Cuando selecciona **Elegir usuario**, puede incluir rápidamente todos los usuarios si selecciona el cuadro **Seleccionar todo**. Sin embargo, es importante entender que cada usuario cuenta como una inclusión específica en la Directiva. Por lo tanto, si incluye 1 000 usuarios al seleccionar el cuadro **Seleccionar todos**, equivaldrá a seleccionar manualmente a 1 000 usuarios para incluir. Este es el número máximo compatible con Skype Empresarial.

Tenga en cuenta que **Historial de conversaciones**, una carpeta de Outlook, es una característica que no tiene nada que ver con el archivado de Skype. El usuario final puede desactivar **Historial de conversaciones**, pero el archivado para Skype se realiza almacenando una copia de las conversaciones de Skype en una carpeta oculta que está disponible para eDiscovery, pero inaccesible para el usuario.

## <a name="settings-for-retaining-and-deleting-content"></a>Configuración para retener y borrar el contenido

Al elegir las configuraciones para retener y eliminar contenido en su directiva de retención, ésta tendrá una de las siguientes configuraciones durante un período de tiempo determinado:

- Sólo para retención

    Para esta configuración, elija **Conservar elementos durante un período específico** y **Al final del período de retención: no haga nada**. O bien, seleccione **Retener elementos para siempre**.

- Retener y luego eliminar

    Para esta configuración, elija **conservar elementos durante un período específico** y **al final del período de retención: eliminar elementos automáticamente**.

- Solo eliminar

    Para esta configuración, elija **Solo eliminar elementos cuando alcancen una antigüedad determinada**.

### <a name="retaining-content-for-a-specific-period-of-time"></a>Retención del contenido durante un período de tiempo determinado

Cuando se configura una directiva de retención, puede elegir retener los elementos durante un número determinado de días, meses o años. Como alternativa, puede retener los elementos para siempre.

Al configurar una directiva de retención, puede elegir retener contenido de forma indefinida o durante un número específico de días, meses o años. El período de retención no se calcula desde el momento en el que se aplica la directiva de retención, sino en función de la antigüedad del contenido.

Para iniciar el período de retención, también puede elegir cuándo se creó el contenido o, solo en el caso de los archivos y las ubicaciones de SharePoint, OneDrive y Office 365, cuándo se modificó el contenido por última vez.

Ejemplos:

- SharePoint: si desea retener los elementos de la colección de un sitio durante siete años a partir de la última modificación del contenido, y un documento de ese sitio no se ha modificado en seis años, el documento se retendrá solo durante un año más, a no ser que se modifique. Si el documento se edita de nuevo, la antigüedad de dicho documento se calculará a partir de la fecha de la última modificación y se retendrá durante otros siete años.

- Exchange: si desea retener los elementos de un buzón durante siete años y hay un mensaje que se envió hace seis, este se retendrá solo durante un año. Para elementos de Exchange, la antigüedad se basa en la fecha de recepción (en el caso de correos electrónicos recibidos) o de envío (para correos electrónicos enviados). Conservar el contenido en función de cuándo se modificó por última vez solo se aplica a contenido de sitio de OneDrive y SharePoint.

Al final del período de retención, usted elige si desea que el contenido se elimine de forma permanente:

![Página de configuración de retenciones](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>Eliminar el contenido que supera una antigüedad determinada

Una directiva de retención puede retener y, a continuación, eliminar elementos o eliminar elementos antiguos sin retenerlos.

En ambos casos, si su directiva de retención elimina elementos, es importante entender que el período de tiempo especificado para una directiva de retención se calcula a partir del momento en que se ha creado o modificado el elemento, y no a partir del momento en que fue asignado a la directiva.

Por lo tanto, antes de asignar una directiva de retención por primera vez (especialmente si la directiva en cuestión elimina elementos), considere primero la antigüedad del contenido existente y cuál será el impacto de la directiva. También es recomendable comunicar la nueva directiva a los usuarios antes de asignarla, para que tengan tiempo de evaluar el posible impacto.

### <a name="a-policy-that-applies-to-entire-locations"></a>Una directiva que se aplica a todas las ubicaciones

Al elegir las ubicaciones, con la excepción de Skype Empresarial, la configuración predeterminada es **Todo** cuando el estado de la ubicación está **Activado**.

Cuando una directiva de retención se aplica a cualquier combinación de todas las ubicaciones, no hay ningún límite en el número de destinatarios, sitios, cuentas, grupos, etc. que la directiva pueda incluir.

Por ejemplo, si una directiva incluye todo el correo electrónico de Exchange y todos los sitios de SharePoint, se incluirán todos los sitios y destinatarios, independientemente de cuántos sean. En el caso de Exchange, todos los buzones que se creen después de aplicar la directiva heredarán automáticamente la directiva.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Una directiva con inclusiones o exclusiones específicas

Deben tenerse en cuenta ciertos límites únicamente si utiliza la configuración opcional para definir el ámbito de la configuración de retención para usuarios específicos, grupos específicos de Microsoft 365 o determinados sitios: 

- Números máximos para una directiva de retención:
  - 1 000 buzones de usuario
  - Grupos de Microsoft 365 1 000.
  - 1 000 usuarios para chats privados de Teams
  - 100 sitios (OneDrive o SharePoint)

Hay también un número máximo de directivas que se admiten para un inquilino: 10 000. Estos elementos incluyen las directivas de retención, directivas de etiquetas de retención y directivas de retención de aplicación automática.

Si cree probable que sus directivas de retención estén sujetas a estas limitaciones, utilice la configuración predeterminada que se aplica a toda la ubicación, ya que estas directivas no tienen ninguna limitación.

Para usar la configuración opcional para definir el ámbito de la configuración de retención, asegúrese de que el **Estado** de esa ubicación esté **Activado** y, a continuación, use los vínculos para incluir o excluir determinados usuarios, grupos de Microsoft 365 o sitios.

> [!WARNING]
> Si configura lo que incluir y, a continuación, quita el último, la configuración se revertirá a **Todos** para la ubicación.  Asegúrese de que esta sea la configuración que desea antes de guardar la directiva.
>
> Por ejemplo, si especifica un sitio de SharePoint para incluirlo en su directiva de retención que está configurada para eliminar datos y, a continuación, quita el sitio en concreto, todos los sitios de SharePoint quedarán sujetos de forma predeterminada a la directiva de retención que elimina de forma permanente los datos. Lo mismo se aplica a destinatarios de Exchange, cuentas de OneDrive, usuarios de chat de Teams, etc.
>
> En este escenario, deshabilite la ubicación si no quiere que la opción **Todos** de la ubicación esté sujeta a la directiva de retención. Como alternativa, especifique lo que se debe excluir de la aplicación de la directiva.

## <a name="updating-retention-policies"></a>Actualización de las directivas de retención

Si edita una directiva de retención y el contenido ya está sujeto a la configuración original de su directiva de retención, la configuración actualizada se aplicará automáticamente a estos elementos, además de los elementos identificados recientemente.

Normalmente, esta actualización es bastante rápida, pero puede llevar varios días. Cuando la replicación de la directiva en todas las ubicaciones de Microsoft 365 se haya completado, verá que el estado de la directiva de retención en el Centro de cumplimiento de Microsoft 365 cambia de **Activado (Pendiente)** a **Activado (Éxito)**.

## <a name="locking-the-policy-to-prevent-changes"></a>Bloquear la directiva para impedir que se realicen cambios

Si necesita asegurarse de que nadie pueda desactivar, eliminar, o hacer que la directiva sea menos restrictiva, consulte [Usar el Bloqueo de conservación para restringir los cambios en directivas de retención y directivas de etiquetas de retención](retention-preservation-lock.md).
